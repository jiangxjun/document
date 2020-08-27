## ResNet深度残差网络（Deep residual network）

> 参考文献1：[deep residual learning for image recognition](https://arxiv.org/abs/1512.03385)

网络深度增加，可以进行更加复杂的特征模式的提取，但会出现深度网络的**退化问题**（Degradation problem）：网络深度增加时，网络准确度出现饱和，甚至下降。56层网络比20层网络效果要差，这不是过拟合问题，56层网络训练误差同样高。

深层网络存在着梯度消失或者爆炸问题，使得深度学习模型很难训练。

### **残差学习**

现在有一个浅层的网络，想通过向上堆积新层来建立深层网络，一个极端情况是这些新加的层什么都不学习，仅仅复制浅层网络的特征，即这样的新层是恒等映射（identity mapping）。这样，深层网络至少和浅层网络一样，不应该出现退化现象。

Kaiming He提出用残差学习来解决退化问题。对于一个堆积层结构（几层堆积而成），当输入为$x$时其学习到的特征记作$H(x)$。学习残差$F(x) = H(x) -x$，即原始的学习特征为$F(x) +x$。

残差的学习相比原始特征直接学习更加容易，当残差为0时，此时堆积层仅仅做了恒等映射，至少网络的性能不会下降，实际上残差不会为0，这会使得堆积层在输入特征基础上学习新的特征，而拥有 更好的性能。

残差学习的结构如图所示：（类似电路短路，是一种短路连接 （shortcut connection））

![v2-252e6d9979a2a91c2d3033b9b73eb69f_hd](/ResNet and DenseNet网络模型/v2-252e6d9979a2a91c2d3033b9b73eb69f_hd.jpg)

残差学习相对更容易，直观上是残差学习需要学习的内容少，残差一般较小，学习难度小。残差单元可以表示为：
$$
y_l = h(x_l) + F(x_l,W_l)
$$

$$
x_{l+1} = f(y_l)
$$

其中，$x_l$和$x_{l+1}$分别表示的是第$l$个残差单元的输入和输出，每一个残差单元一般包含多层结构。

$F$是残差函数，表示学习到的残差

$h(x_l) = x_l$表示恒等映射

$f$表示ReLU激活函数。

简要推导：

$x_L = x_l + \sum\limits_{i=l}^{L-1} F(x_i,W_i)$，表示从浅层$l$到深层$L$的学习特征。

利用链式规则，可以求得反向过程的梯度：
$$
\frac{\partial Loss}{\partial x_l} = \frac{\partial Loss}{\partial x_L}·\frac{\partial Loss}{\partial x_l}= \frac{\partial Loss}{\partial x_L}·\left( 1+ \frac{\partial}{\partial x_L}\sum\limits_{i=l}^{L-1}F(x_i,W_i)    \right)
$$
式中，$\frac{\partial Loss}{\partial x_L}$表示损失函数到达$L$的梯度，小括号中的1表明短路机制可以无损地传播梯度，另外一项残差梯度则需要经过带有weights的层，梯度不是直接传递过来的。

残差梯度不会那么巧全为-1，而且比较小，有1的存在不会导致梯度消失，残差学习更容易。

### ResNet网络结构

参考的VGG19网络，在其基础上修改，并通过短路机制加入残差单元。

主要变化是在 ResNet直接采用stride=2的卷积做下采样，并用global average pool层替换全连接层。

ResNet的一个重要设计原则：当feature map大小降低一半时，feature map的数量增加一倍，这保持了网络层的复杂度。

![v2-7cb9c03871ab1faa7ca23199ac403bd9_hd](/ResNet and DenseNet网络模型/v2-7cb9c03871ab1faa7ca23199ac403bd9_hd.jpg)

ResNet相比普通网络每两层间增加了短路机制，形成了残差学习，其中虚线表示feature map数量发生了改变。

![v2-1dfd4022d4be28392ff44c49d6b4ed94_hd](/ResNet and DenseNet网络模型/v2-1dfd4022d4be28392ff44c49d6b4ed94_hd.jpg)

从表中可见，18-layer-ResNet和34-layer-ResNet，其进行的是两层间的残差学习，当网络更深时，其进行的三层间的残差学习，三层的卷积核分别是1×1，3×3和1×1。

其中，隐含层的feature map的数量是比较小的，并且是输出feature map数量的1/4。

### 残差单元

ResNet使用的是两种残差单元。

![v2-0892e5423616c30f69ded61111b111c0_r](/ResNet and DenseNet网络模型/v2-0892e5423616c30f69ded61111b111c0_r.jpg)

分别对应浅层网络（左图）和深层网络（右图）。

对于短路连接，当输入和输出维度不一致时，可以直接将输入加到输出上，但是当维度不一致时（对应维度增加一倍），不能直接相加。

有两种策略：
1、采用zero-padding增加维度，此时一般要先做一个downsamp，可以采用stride=2的pooling，这样不会增加参数；

2、采用新的映射（projection shortcut），一般采用1×1的卷积，这样会增加参数，也会增加计算量。

短路连接除了可以直接使用恒等映射，也可以采用projection shortcut。

![v2-0a2c8a209a221817f91c1f1728327beb_hd](/ResNet and DenseNet网络模型/v2-0a2c8a209a221817f91c1f1728327beb_hd.jpg)

### 改进后的残差单元及效果

![v2-4e0bf37ecad2f306fe09d32a2d37d908_hd](/ResNet and DenseNet网络模型/v2-4e0bf37ecad2f306fe09d32a2d37d908_hd.jpg)

改进的前后一个明显变化是采用pre-activation，BN和ReLU都提前了，推荐短路连接采用恒等变换，保证短路连接不会有阻碍。[^参考文献2]

[^参考文献2]:[identity mappings in deep residual networks](https://arxiv.org/abs/1603.05027)

### ResNet的Tensorflow实现

[Github地址](https://github.com/xiaohu2015/DeepLearning_tutorials/)



## DenseNet模型

ResNet可以训练出更深的CNN模型，从而实现更高的准确度，其核心是通过建立前面层与后面层之间的“短路连接”（shortcuts,skip connection），有助于训练过程中梯度的反向传播，从而能训练出更深的CNN网络。

DenseNet的基本思路与ResNet一致，但是建立的是前面所有层与后面层的**密集连接**（dense connection）。

DenseNet的另一特点是：通过特征在channel上的连接来实现**特征重用**（feature reuse）。使得DenseNet在参数和计算成本更少的情形下实现比ResNet更优的性能。

![v2-c81da515c8fa9796601fde82e4d36f61_hd](/ResNet and DenseNet网络模型/v2-c81da515c8fa9796601fde82e4d36f61_hd.jpg)

DenseNet提出的密集连接机制：互相连接所有的层。每个层都会接受其前面的所有层作为其额外的输入。

![v2-862e1c2dcb24f10d264544190ad38142_hd](/ResNet and DenseNet网络模型/v2-862e1c2dcb24f10d264544190ad38142_hd.jpg)

ResNet的短路连接方式是通过元素级相加。每个层与前面的某层（一般2-3层）短路连接在一起。

![v2-2cb01c1c9a217e56c72f4c24096fe3fe_hd](/ResNet and DenseNet网络模型/v2-2cb01c1c9a217e56c72f4c24096fe3fe_hd.jpg)

DenseNet的每个层都会与前面所有层在channel维度上连接（concat）在一起，**各个层的特征图大小是相同的**，并且作为下一层的输入。

对于一个L层的网络，DenseNet共包含$\frac{L(L+1)}{2}$个连接，是一种密集连接。此外，DenseNet是直接concat来自不同的层的特征图，实现特征重用。

传统的网络在$l$层的输出为：
$$
x_l = H_l(x_l-1)
$$
对于ResNet，增加了来自上一层输入的identity函数：
$$
x_l = H_l(x_l-1) +x_{l-1}
$$
在DesNet中，会连接前面所有层作为输入：
$$
x_l = H_l([x_0,x_1,\dots,x_{l-1}])
$$
其中$H_l(·)$代表非线性转化函数（non-linear transformation），是一个组合操作，可能包括一系列的BN（Batch Normalization），ReLU，Pooling及Conv操作，$l$和$l-1$层之间可能包括多个卷积层。

![v2-0a9db078f505b469973974aee9c27605_r](/ResNet and DenseNet网络模型/v2-0a9db078f505b469973974aee9c27605_r.jpg)

上图可见，$h_3$的输入不仅包括来自$h_2$的$x_2$，还包括前面两层的$x_1$和$x_0$，它们是在channel维度上连接在一起的。

------

CNN网络一般要经过Pooling或者stride>1的Conv来降低特征图的大小，DenseNet的密集连接方式**需要特征图大小保持一致。**

解决方法是：使用DenseNet +Transition结构，其中DenseBlock是包含很多层的模块，每个层的特征图大小相同，层与层之间采用密集连接方式。而Transition模块是连接两个相邻的DenseBlock，并且通过Pooling使特征图大小降低。

![v2-ed66515594a04be849a8cee707cb83bf_r](/ResNet and DenseNet网络模型/v2-ed66515594a04be849a8cee707cb83bf_r.jpg)

------

**使用Pytorch实现DenseNet**

DenseNet的优势主要体现在以下几个方面：

- 由于密集连接方式，DenseNet提升了梯度的反向传播，使得网络更容易训练。由于每层可以直达最后的误差信号，实现了隐式的[“deep supervision”](https://link.zhihu.com/?target=https%3A//arxiv.org/abs/1409.5185)；
- 参数更小且计算更高效，这有点违反直觉，由于DenseNet是通过concat特征来实现短路连接，实现了特征重用，并且采用较小的growth rate，每个层所独有的特征图是比较小的；
- 由于特征复用，最后的分类器使用了低级特征。

要注意的一点是，如果实现方式不当的话，DenseNet可能耗费很多GPU显存，一种高效的实现如图10所示，更多细节可以见这篇论文[Memory-Efficient Implementation of DenseNets](https://link.zhihu.com/?target=https%3A//arxiv.org/abs/1707.06990)。不过我们下面使用Pytorch框架可以自动实现这种优化。



[参考资料](https://zhuanlan.zhihu.com/p/37189203)