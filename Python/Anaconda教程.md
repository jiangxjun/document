---
title: Anaconda教程
date: 2020-5-20
categories:
- 教程
mathjax: true
description: Anaconda使用简单教程
---



## 修改conda 的镜像源

（现在不可用）

```python
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/

conda config --set show_channel_urls yes
```

此时，在目录 C:\Users<你的用户名> 下就会生成配置文件.condarc，内容如下：

```python
channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - defaults
show_channel_urls: true
```



## jupyter notebook使用

创建带jupyter notebook内核的虚拟环境：

```python
conda create --name py37_Pytorch python=3.7 ipykernel
```

关联和conda的环境和包：

`conda install nb_conda`

Markdown生成目录：

`conda install -c conda-forge jupyter_contrib_nbextensions`

[jupyter notebook使用教程](https://www.jianshu.com/p/91365f343585)





在虚拟环境下创建kernel文件：

```
conda install -n 环境名称 ipykernel
```

将环境写入jupyter notebook的kernel中

```
python -m ipykernel install --user --name 环境名称 --display-name "Python (环境名称)"
```



## pip 安装 PyTorch步骤

```python
pip3 install https://download.pytorch.org/whl/cpu/torch-1.0.0-cp37-cp37m-win_amd64.whl
```

安装版本为`torch-1.0.0`，CPU版本，没有CUDA，python3.x版本。

```python
pip install --no-deps torchvision
```

不使用：`pip3 install torchvision`，会报错。

[PyTorch安装](https://redstonewill.com/1948/)



## pip和conda区别

conda是一种通用包管理系统，是一个与语言无关的跨平台的环境管理器，可以构建和管理任何语言的任何类型的软件。因此适用于python包。

pip代表pip install packages，是python官方认可的包管理器，最常用于安装python包索引（PyPI）上的发布的包。

conda install包，默认是安装在base（anaconda）环境下，conda在指定的环境下安装包：

`conda install -n env_name pandas`。

anaconda是一个python的发行版，conda是一个包管理器。

## pip和pip3区别

在安装库numpy，pip3 install numpy和pip install numpy命令效果一致的，但当有多个版本的python虚拟环境时，用pip3可以自动区别用python3来安装库文件，避免发生和python2的冲突。

若只安装了python3，pip和pip3是一样的效果，安装python3后，会自动安装pip3，添加scripts到环境变量(避免出现不是内部或外部命令问题)。

若多版本python存在，使用pip install ，新安装的库文件会放在目录：`python2.x/site_packages`中；使用 pip3 install ，新安装的库文件会放在目录：`python3.x/site-packages`中。

## 一些常用命令

`conda activate env_name`激活环境，当前被激活环境前有*号

`conda deactivate env_name`关闭环境

（Linux下）：

`source activate/deactivate env_name`



`conda remove -n env_name --all`删除环境

`conda create --name env_name python=3.x`创建一个基于python3.x的名为env_name的虚拟环境，同样正对于python2.x版本。

`conda env list`查看所有安装的环境

`conda install requests`安装包

`conda install -n env_name numpy`安装在指定的环境下的包，若不指定，则是安装在当前活跃环境，也可通过-c指定某个channel来安装。

`conda list`查看所安装的包

`conda update requests`包更新

`conda update -n env_name packages`指定环境下的包更新

`conda remove requests`删除包

`conda list -n env_name`查看指定环境下的已安装包

`conda search numpy`查找package信息

------

conda将conda、python等都看成packages，都可以通过conda来管理conda和python版本，如：

`conda update conda`更新conda

`conda update anaconda`更新当前环境下的anaconda。

`conda update python`假设当前环境下的python为3.7版本，会升级为3.7.x系列的最新版本、

Anaconda的bin目录加入PATH，可能有不同的~/anaconadx/bin，：

`echo 'export PATH = "~/anaconda3/bin:$PATH"' >> ~/.bashrc`      Linux下的添加命令。

运行`conda --version`检查是否正确。



[Anaconda基本使用总结](https://www.jianshu.com/p/2f3be7781451#)



