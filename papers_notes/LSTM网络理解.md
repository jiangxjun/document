## Recurrent Neural Network

传统的神经网络很难处理一件事——使用先前事件推断后续的事件。RNN解决了这个问题，是包含循环的网络，允许信息的持久化。

<img src="/papers_notes/LSTM网络理解/RNN-rolled.png" alt="RNN-rolle" style="zoom:33%" />

$A$正在读取输入$x_t$，并输出$h_t$。循环可以使得信息可以从当前步传递到下一步。

RNN can be thought of as multiple copies of the same network, each passing a message to a successor(接替者). Consider what happens if we unroll the loop:

![RNN-unrolled](/LSTM网络理解/RNN-unrolled.png)

This chain-like nature reveals that RNN are intimately related to sequences and lists(和序列和列表相关). 

There have been incredible success applying RNNs to a variety of problems: **Speech recognition, Language modeling, Translation, Image captioning...**

Essential to these successes is the use of "LSTMs", a very special kind of RNN which works, for many tasks, much much better than standard version.

## The problem of Long-Term Dependencies

One of the appeals of RNNs is the idea that they might be able to connect previous information to the present task.

In theory, RNNs are absolutely capable of handling  long-term dependencies. It's entirely possible for the gap between the relevant information and the point where it is needed to become very large. While, as the gap grows, RNNs become unable to learn to connect the information.

例如：有一个语言模型用来基于先前的的词来预测下一个词，如果试着预测"the clouds are in the sky"最后的一个词，并不需要任何其他的上下文，显然最后的一个词就是sky。在这样的场景中，相关的信息和预测的词位置之间的间隔非常小，RNN可以学会使用先前的信息。

![RNN-shorttermdepdencies](/LSTM网络理解/RNN-shorttermdepdencies.png)

<img src="/mypages/papers_notes/LSTM网络理解/RNN-shorttermdepdencies.png" title="RNN-shorttermdepdencies" style="zoom:33%;" />

然而，对于一些更加复杂的场景，如预测"I grew up in France... I speak fluent French"最后的词，当前的信息建议下一个词可能是一种语言的名字，这需要先前提到的离当前位置很远的France的上下文。此时，相关信息和当前预测位置之间的间隔变得很大，在这个间隔不断变大时，RNN会丧失学习到连接如此远的信息的能力。虽然可以仔细挑选参数来解决这类toy problems。但在实践中，RNN肯定不能够成功学习到这些知识，Bengio,et al.(1994)等人对该问题进行了深入研究，发现一些使得RNN训练变得非常困难的根本原因。

![RNN-longtermdependencies](/LSTM网络理解/RNN-longtermdependencies.png)

LSTM don't have this problem!

## LSTM Networks

Long Short Term Memory networks(LSTMs)是一种RNN特殊的类型，可以学习长期依赖信息。LSTM由[Hochreiter & Schmidhuber(1997)](http://deeplearning.cs.cmu.edu/pdfs/Hochreiter97_lstm.pdf)提出，并被[Alex Graves](https://scholar.google.com/citations?user=DaFHynwAAAAJ&hl=en)进行了改良和推广。

LSTMs are **explicitly designed** to avoid the long-term dependency problem. Remembering info for long periods of time is practically their **default behavior**, not something they struggle to learn.

All RNNs have the form of a chain of repeating modules of neural networks(重复神经网络模块的链式结构). 

**标准的RNN**

标准的RNN中，重复的模块只有一个简单的结构，如一个tanh层：

![LSTM3-SimpleRNN](/LSTM网络理解/LSTM3-SimpleRNN.png)

**LSTM**

LSTM重复模块不同于单一神经网络层，这里是有四个，以一种非常特殊的方式进行交互：

![LSTM3-chain](/LSTM网络理解/LSTM3-chain.png)

**LSTM解析图元素**

![LSTM2-notation](/LSTM网络理解/LSTM2-notation.png)

Neural Network Layer: 学习到的网络层

Pointwise Operation: pointwise操作，如向量的和

Vector Transfer: 传输一整个向量，从一个节点输出到其他节点的输入

Concatenate: 向量的连接

Copy: 内容被复制，然后分发到不同的位置

## The Core Idea Behinds LSTMs

LSTM的关键是细胞状态，水平线在图上方贯穿运行。

![LSTM3-C-line](/LSTM网络理解/LSTM3-C-line.png)

细胞状态类似于传送带，直接在整个链上运行，只有一些少量的线性交互，信息在上面流传保持不变会变得很容易。

LSTM通过精心设计的“**门(gates)**”结构来去除或者增加信息到细胞状态的能力。

门是一种让信息选择式的通过的方法，包含一个sigmoid神经网络层和一个pointwise乘法操作。

![LSTM3-gate](/LSTM网络理解/LSTM3-gate.png)

Sigmoid层输出0-1之间的数值，描述每个部分有多少量可以通过。0表示“不允许任何量通过”，1表示“允许任意量通过”。

LSTM有三个门，来保护和控制细胞状态。

## Step-by-Step LSTM Walk Through

第一步**决定从细胞状态中丢弃什么信息**。通过**忘记门层(forget gate layer)**完成。该门读取$h_{t-1}$和$x_t$，输出一个0-1之间的数值给每个在细胞状态$C_{t-1}$中的数字。1表示完全保留，0表示完全舍弃。

![LSTM3-focus-f](/LSTM网络理解/LSTM3-focus-f.png)

第二步**决定什么样的新信息被存放到细胞状态中**。包含两个部分，一是sigmoid层（输入门层）决定什么值将要更新，还有一个是tanh层将创建一个新的候选值向量$\tilde{C}_t$，会被加入到状态中。

![LSTM3-focus-i](/LSTM网络理解/LSTM3-focus-i.png)

第三步**确定更新信息**。$C_{t-1}$更新为$C_t$。把旧状态与$f_t$相乘，丢弃掉确定需要丢弃的信息。接着加上$i_t \times \tilde{C}_t$，即是新的候选值，根据我们决定更新每个状态的程度进行变化。

![LSTM3-focus-C](/LSTM网络理解/LSTM3-focus-C.png)

第四步**更新细胞状态**。最终，确定输出什么值，这个输出将会基于我们的细胞状态，但也是一个过滤后的版本。

首先，运行一个sigmoid层来确定细胞状态的哪一部分将输出出去。接着，把细胞状态通过tanh进行处理，得到一个在-1到1之间的值，并将其与sigmoid门的输出相乘。最终，仅输出我们确定输出的那部分。

![LSTM3-focus-o](/LSTM网络理解/LSTM3-focus-o.png)

## Variants on LSTMs

以上介绍的是正常的LSTM结构，实际使用上，都会采用微小的变体。

1、流形的LSTM变体。

是由[Gers & Schmidhuber(2000)](ftp://ftp.idsia.ch/pub/juergen/TimeCount-IJCNN2000.pdf)提出的，增加了"peephole connection"。让 门层 也会接受细胞状态的输入。

![LSTM3-var-peepholes](/LSTM网络理解/LSTM3-var-peepholes.png)

图例中是所有部分都加入了peephole到每个门上，也有加入部分的peephole。

2、使用coupled忘记和输入门。

不同于之前是分开确定什么忘记和需要添加什么新的信息，这里是一同做出决定。We only forget when we're going to input something in its place. We only input new values to the state when we forget something older.

![LSTM3-var-tied](/LSTM网络理解/LSTM3-var-tied.png)

仅仅在输入的当前位置进行忘记，仅仅输入新的值到已经忘记的旧的信息状态里。

3、Gated Recurrent Unit (GRU)

是由[Cho,et al.(2014)](http://arxiv.org/pdf/1406.1078v3.pdf)提出的。将忘记门和输入门合成一个单一的 **更新门**。同样还混合了细胞状态和隐藏状态以及其他一些改动。最终的模型比标准的LSTM模型更加简单。

![LSTM3-var-GRU](/LSTM网络理解/LSTM3-var-GRU.png)

<img src="/mypages/papers_notes/LSTM网络理解/LSTM3-var-GRU.png" title="LSTM3-var-GRU" style="zoom:50%;" />

还有很多其他类型变体形式，如[Yao,et al.(2015)](http://arxiv.org/pdf/1508.03790v2.pdf)提出的Depth Gated RNN。[Koutnik, et al.(2014)](http://arxiv.org/pdf/1402.3511v1.pdf)提出的Clockwork RNN。[Greff, et al.(2015)](http://arxiv.org/pdf/1503.04069.pdf)给出了流行的LSTM变体的比较，结论是基本一样。[Jozefowicz,et al.(2015)](http://jmlr.org/proceedings/papers/v37/jozefowicz15.pdf)在超过10000种RNN架构上进行了测试，发现一些架构在某些任务上也取得了比LSTM更好的结果。

[参考资料——colah's blog](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)

