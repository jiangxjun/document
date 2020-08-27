# print功能

print 默认输出是换行，如果要实现不换行需要在变量末尾加上 **end=""**


```python
print("hello world")
```

    hello world



```python
print('hello'+'world')
```

    helloworld



```python
print('hello'+4) #字符串不能直接和数字相加
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-4-3969ea1f57ce> in <module>
    ----> 1 print('hello'+4) #字符串不能直接和数字相加


    TypeError: can only concatenate str (not "int") to str



```python
print(int(2.6)+3)#整型
```

    5



```python
print(float('1.2')+3)#浮点型
```

    4.2


# 基础数学运算

| 运算符 | 描述 | 实例 |
|:---:|:---:|:---:|
| / | 除 | b/a输出结果为2.1 |
| % | 取模-返回除法的余数 | b%a输出结果为1 |
| `**` | 幂-返回x的y次幂 | x的y次幂 |
| // | 取整除 | 9//2=4 |


```python
%matplotlib inline 
import matplotlib.pyplot as plt
from numpy import pi,sin,linspace
from matplotlib.mlab import stineman_interp

x=linspace(0,2*pi,20)
y=sinx
yp=None
xi=linspace(x[0],x[-1],100)
yi=stineman_interp(xi,x,y,yp)

fig.ax = plt.subplots()
ax.plot(x,y,'ro',xi,yi,'-b.')
plt.show()
```


    ---------------------------------------------------------------------------
    
    ImportError                               Traceback (most recent call last)
    
    <ipython-input-1-1282f69f7ac5> in <module>()
    ----> 1 get_ipython().run_line_magic('matplotlib', 'inline')
          2 import matplotlib.pyplot as plt
          3 from numpy import pi,sin,linspace
          4 from matplotlib.mlab import stineman_interp
          5 


    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\interactiveshell.py in run_line_magic(self, magic_name, line, _stack_depth)
       2129                 kwargs['local_ns'] = sys._getframe(stack_depth).f_locals
       2130             with self.builtin_trap:
    -> 2131                 result = fn(*args,**kwargs)
       2132             return result
       2133 


    <C:\Anaconda3\envs\py3\lib\site-packages\decorator.py:decorator-gen-108> in matplotlib(self, line)


    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\magic.py in <lambda>(f, *a, **k)
        185     # but it's overkill for just that one bit of state.
        186     def magic_deco(arg):
    --> 187         call = lambda f, *a, **k: f(*a, **k)
        188 
        189         if callable(arg):


    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\magics\pylab.py in matplotlib(self, line)
         97             print("Available matplotlib backends: %s" % backends_list)
         98         else:
    ---> 99             gui, backend = self.shell.enable_matplotlib(args.gui)
        100             self._show_matplotlib_backend(args.gui, backend)
        101 


    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\interactiveshell.py in enable_matplotlib(self, gui)
       3035         """
       3036         from IPython.core import pylabtools as pt
    -> 3037         gui, backend = pt.find_gui_and_backend(gui, self.pylab_gui_select)
       3038 
       3039         if gui != 'inline':


    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\pylabtools.py in find_gui_and_backend(gui, gui_select)
        271     """
        272 
    --> 273     import matplotlib
        274 
        275     if gui and gui != 'auto':


    ImportError: No module named 'matplotlib'


python中^符号，用两个**


```python
3**2 # **2表示2次方
3**3 #**3表示3次方
3**4
```




    81



取余符号为%


```python
8%3
```




    2



## 比较运算符

|运算符|描述|
|:--|:--|
|==|等于|
|!=|不等于|


## 赋值运算符

|运算符|描述|
|:--|:--|
|%=|取模赋值|
|`**=`|幂赋值|
|//=|取整赋值|

## 位运算符

|运算符|描述|
|:--|:--|
|&|按位与|
|\|按位或|
|^|按位异或|
|~|按位取反|
|<<|左移动运算|
|>>|右移动运算|

## 逻辑运算符

|运算符|描述|
|:--|:--|
|and|布尔“与”-如果x为false，x and y返回false，否则返回y|
|or|布尔“或”-如果x为true， x or y 返回x的值，否则返回y的值|
|not|布尔“非”-如果x为true，not x 返回false，反之|


## 成员运算符

|运算符|描述|
|:--|:--|
|in|如果在指定序列中找到，返回true，否则false|
|not in|如果在指定的序列中没有找到，返回true，否则false|

## 身份运算符

|运算符|描述|
|:--|:--|
|is|判断两个标识符是不是引自一个对象，是返回true，否则false|
|is not|判断两个标识符是不是引自不同对象，是返回true，否则false|

## 运算优先级

# 变量命名规则


```python
apple=1 #赋值数字
print(apple)
```

    1



```python
apple='iphoneX'#赋值字符串
print('apple')
print(apple)
```

    apple
    iphoneX



```python
a,b,c=11,12,13#一次性定义多个变量
print(a,b,c)
```

    11 12 13


# 循环

## while循环

while condition:
     expressions
condition为判断条件，即true和false中一个，如果为true执行expressions语句，否则跳出循环继续往下执行。
会有意外缩进产生。


```python
condition=0
while condition < 10:
     print(condition) #顶格写不在循环
     condition = condition+1
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9



```python
condition=10
while condition:
    print(condition)
    condition -=1
```

    10
    9
    8
    7
    6
    5
    4
    3
    2
    1


var = 1
while var ==1:       #表达式永远为True
    num = int(input("输出一个数字："))
    print ("你输入的数字是："，num)

小于(<);等于(==);不等于(!=);不大于(<=)
会返回true和false值

none类型：
如果while后面接着的语句类型none，将会返回false。



```python
a=range(10) 
while a:
    print(a[-1])#打印出最后一位，将去除最后一位的列表a重新赋值给列表a
    a=a[:len(a)-1]
```

    9
    8
    7
    6
    5
    4
    3
    2
    1
    0


while循环使用else语句


```python
count =0
while count < 5:
    print (count,"小于5")
    count=count +1
else:
    print(count,"大于或等于5")
```

    0 小于5
    1 小于5
    2 小于5
    3 小于5
    4 小于5
    5 大于或等于5


## for循环

基本用法：
for item in sequence:
   expressions
其中:sequence为可迭代的对象，item为序列中的每个对象


```python
example_list=[1,2,3,4,5,6,7,12,543,876,12,3,2,5]
for i in example_list:
    print(i)
    print('inner of for')#每次循环都会输出inner of for
print('outer of for')#循环结束后输出一次out of for
```

    1
    inner of for
    2
    inner of for
    3
    inner of for
    4
    inner of for
    5
    inner of for
    6
    inner of for
    7
    inner of for
    12
    inner of for
    543
    inner of for
    876
    inner of for
    12
    inner of for
    3
    inner of for
    2
    inner of for
    5
    inner of for
    outer of for


## range使用

python内置工厂函数，range函数会返回一个序列，有三种使用方法：
1. range(start,stop)
start是序列的起始值，stop是结束值，但**不包括该值**，类似的数学中的表达为：左闭右开区间。

2. range(stop)
省略start，重0开始，相当于range(0,stop)

3. range(start,stop,step)
step表示步长，即相隔两个值的差值，从start开始，依次增加step值，直至**等于或大于**stop。



```python
for i in range(1,10):
 print(i)
for i in range(1,10,5):
 print(i)

```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    1
    6


集合range()和len()函数可以遍历一个序列的索引。


```python
a = ['google','baidu','runoob','taobao','qq']
for i in range(len(a)):
    print(i,a[i])
```

    0 google
    1 baidu
    2 runoob
    3 taobao
    4 qq


使用range()函数创建一个列表


```python

list1=list( range(0,5) )
print(list1)
```

    [0, 1, 2, 3, 4]


## break和continue语句及循环中的else子句


```python
for letter in 'Runoob':     # 第一个实例
   if letter == 'b':
      break
   print ('当前字母为 :', letter)
  
var = 10                    # 第二个实例
while var > 0:              
   print ('当期变量值为 :', var)
   var = var -1
   if var == 5:
      break
 
print ("Good bye!")
```

    当前字母为 : R
    当前字母为 : u
    当前字母为 : n
    当前字母为 : o
    当前字母为 : o
    当期变量值为 : 10
    当期变量值为 : 9
    当期变量值为 : 8
    当期变量值为 : 7
    当期变量值为 : 6
    Good bye!


continue语句用于跳出当前循环块中的剩余语句，然后继续进行下一轮循环


```python
for letter in 'Runoob':     # 第一个实例
   if letter == 'o':        # 字母为 o 时跳过输出
      continue
   print ('当前字母 :', letter)
 
var = 10                    # 第二个实例
while var > 0:              
   var = var -1
   if var == 5:             # 变量为 5 时跳过输出
      continue
   print ('当前变量值 :', var)
print ("Good bye!")
```

    当前字母 : R
    当前字母 : u
    当前字母 : n
    当前字母 : b
    当前变量值 : 9
    当前变量值 : 8
    当前变量值 : 7
    当前变量值 : 6
    当前变量值 : 4
    当前变量值 : 3
    当前变量值 : 2
    当前变量值 : 1
    当前变量值 : 0
    Good bye!


循环可以有**else**子句，在穷尽列表（以for循环）或条件变为false（以while循环）导致循环终止时被执行，但循环被break终止时不执行。


```python
for n in range(2,10):
    for x in range(2,n):
        if n%x == 0:
            print(n,'等于',x,'*',n //x)
            break
        else:
            #循环中没有找到元素
            print(n,'是质数')
```

    3 是质数
    4 等于 2 * 2
    5 是质数
    5 是质数
    5 是质数
    6 等于 2 * 3
    7 是质数
    7 是质数
    7 是质数
    7 是质数
    7 是质数
    8 等于 2 * 4
    9 是质数
    9 等于 3 * 3


## pass语句

pass语句是空语句，为了保持程序结构的完整性；pass不做任何事情，一般用于占位语句。


```python
for letter in 'Runoob': 
   if letter == 'o':
      pass
      print ('执行 pass 块')
   print ('当前字母 :', letter)
 
print ("Good bye!")
```

    当前字母 : R
    当前字母 : u
    当前字母 : n
    执行 pass 块
    当前字母 : o
    执行 pass 块
    当前字母 : o
    当前字母 : b
    Good bye!


# 内置集合


集合类型：
python中有list,tuple（元组，数组）,dict,set等，如果该集合对象作为while判断语句，若集合元素为0 ，返回false，否则返回true。


```python
tup=('python',2.7,64)#tuple类型
for i in tup:
    print(i)
#程序按行输出
```

    python
    2.7
    64



```python
dic={}            #dictionary模型
dic['lan']='python'
dic['version']=2.7
dic['platform']=64
for key in dic:
    print(key,dic[key])#key是乱序的
```

    lan python
    version 2.7
    platform 64



```python
s=set(['python','python2','python3','python']) #set类型
for item in s:
    print(item)  #输出乱序，去除重复项
```

    python2
    python3
    python


# 迭代器

python中for语句实际上实现了设计模式中的迭代器模式，可以按照迭代器的要求生成迭代器对象，以便于在for语句中使用。

只要在类中实现了iter()和next()函数，对象就可以在for语句中使用。

字符串，列表或元组对象都可用于创建迭代器。


```python
list = [1,2,3,4]
it = iter(list)    #创建迭代器
print (next(list)) #输出迭代器的下一个元素

for x in it:
    print (x,end="")
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-1-0fb025b0a758> in <module>()
          1 list = [1,2,3,4]
          2 it = iter(list)    #创建迭代器
    ----> 3 print (next(list)) #输出迭代器的下一个元素


    TypeError: 'list' object is not an iterator



```python
import sys   #引入 sys 模块

list = [1,2,3,4]
it = iter(list)  #创建迭代器对象

while True:
    try:
        print(next(it))
    except StopIteration:
        sys.exit()
```

    1
    2
    3
    4



    An exception has occurred, use %tb to see the full traceback.


    SystemExit



    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\interactiveshell.py:2969: UserWarning: To exit: use 'exit', 'quit', or Ctrl-D.
      warn("To exit: use 'exit', 'quit', or Ctrl-D.", stacklevel=1)


**创建一个迭代器**
把一个类作为一个迭代器需要在类中实现两个方法`__iter__()`与`__next__()`。
类都有一个构造函数，python的构造函数为`__init__()`，它会在对象初始化的时候执行。

`__iter__()`方法返回一个特殊的迭代器对象，这个迭代器实现了`__next__()`方法并通过`StopIteration`异常标识迭代的完成。

`__next__()`方法（python2里是next()）会返回下一个迭代对象。


```python
# define a Fib class
class Fib(object):
    def _init_(self, max): #注意init左右有两个_
        self.max = max
        self.n, self.a, self,b=0, 0, 1
        
    def _iter_(self):
        return self
    
    def _next_(self):
        if self.n < self.max:
            r = self.b
            self.a, self.b = self.b, self.a + self.b
            self.n = self.n + 1
            return r
        raise StopIteration()
        
#using fib object
for i in Fib(5): 
    print(i)

```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-50-3c5b777610b9> in <module>
         17 
         18 #using fib object
    ---> 19 for i in Fib(5):
         20     print(i)


    TypeError: Fib() takes no arguments



```python
# define a Fib class
class Fib(object):
    def __init__(self, max):
        self.max = max
        self.n, self.a, self.b = 0, 0, 1

    def __iter__(self):
        return self

    def __next__(self):
        if self.n < self.max:
            r = self.b
            self.a, self.b = self.b, self.a + self.b
            self.n = self.n + 1
            return r
        raise StopIteration()

# using Fib object
for i in Fib(5):
    print(i)
```

    1
    1
    2
    3
    5


**StopIteration**异常用于 标识迭代的完成，防止出现无线循环的情况，在`__next()__`方法中可以设置在完成指定循环次数后触发StopIteration异常结束迭代。


```python
class MyNumbers:
    def __iter__(self):
        self.a = 1   #初始值为1
        return self
    
    def __next__(self):
        if self.a <=20:
            x = self.a
            self.a += 1 #逐步增1
            return x
        else:
            raise StopIteration
            

#myiter = iter(MyNumbers())
myiter = list(MyNumbers())
for x in myiter:
    print(x)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20


# 生成器

python中使用**yield**关键字也能实现类似迭代的效果，yield语句每次执行时，立即返回结果给上层调用者，而当前的状态仍然保留，以便于迭代器下一次循环调用。

生成器是一个返回迭代器的函数，只能用于迭代操作，简单理解就是生成器就是一个迭代器。

调用生成器运行时，每次遇到**yield**时函数会暂停并保存当前所有的运行信息，返回yield的值，并在下一次执行 next()方法时从当前位置继续运行。

节约硬件资源，在需要的时候才会执行，并且只执行一次。

调用一个生成器函数，返回的是一个迭代器对象。


```python
def fib(max):
    a,b=0,1
    while max:
        r=b
        a,b=b,a+b
        max-=1
        yield r
        
#using generator 
for i in fib(5):
    print(i)
```

    1
    1
    2
    3
    5



```python
import sys
 
def fibonacci(n): # 生成器函数 - 斐波那契
    a, b, counter = 0, 1, 0
    while True:
        if (counter > n): 
            return
        yield a
        a, b = b, a + b
        counter += 1
f = fibonacci(10) # f 是一个迭代器，由生成器返回生成
 
while True:
    try:
        print (next(f), end=" ")
    except StopIteration:
        sys.exit()
```

    0 1 1 2 3 5 8 13 21 34 55 


    An exception has occurred, use %tb to see the full traceback.


    SystemExit



    C:\Anaconda3\envs\py3\lib\site-packages\IPython\core\interactiveshell.py:2969: UserWarning: To exit: use 'exit', 'quit', or Ctrl-D.
      warn("To exit: use 'exit', 'quit', or Ctrl-D.", stacklevel=1)


# if判断

if condition:
   expression
若condition的值为true，将会执行expressions语句内容，否则跳出该语句往下执行


```python
x=1
y=2
z=3
if x<y:
    print('x is less than y')
if x<y<z: #最好写成x<y and y<z
    print('x is less than y,ang y is less than z')
```

    x is less than y
    x is less than y,ang y is less than z



```python
x=2
y=2
if x==y:
    print('x is equal to y')
```

    x is equal to y


# if else判断

if condition:
    true_expressions
else:
    false_expressions


```python
x =1
y=2
z=3
if x>y:
    print('x is greater than y')
else:
    print('x is less or equal to y')
```

    x is less or equal to y


# 高级主题
var = var1 if condition else var2
如果condition的值为true，那么将var1赋给var；如果为false，则将var2的值赋给var。


```python
worked = True
result = 'done' if worked else 'not yet'
print(result)
```

    done


# if elif else判断

使用规则：
if condition1:
    true1_expressions
elif condition2:
    true2_expressions
elif condtion3:
    true3_expressions
elif ...
    ...
else:
    else_expressions
有 多个判断条件，可以通过elif语句添加多个判断条件，一旦某个条件为true，那么将执行对应的expression。并在代码执行完毕后跳出该if-elif-else语句块，往下执行。


```python
x=4
y=2
z=3
if x>1:
    print('x>1')
elif x<1:
    print('x<1')
else:
    print('x=1')
print('finish')
```

    x>1
    finish


# 向量化例子（去除代码中的for循环）


```python
import numpy as np #导入numpy库
a = np.array([1,2,3,4]) #创建一个数据a
print(a)


```

    [1 2 3 4]



```python
import time #导入时间库
a = np.random.rand(1000000)
b = np.random.rand(1000000)#通过round随机得到两个一百万维度的数组
tic = time.time()#测量当前时间
c = np.dot(a,b)
toc = time.time()#测量时间
print(c)
print("vectorized version:" + str(1000*(toc-tic)) + "ms")
c=0
tic = time.time()
for i in range(1000000):
    c += a[i]*b[i]
toc = time.time()
print(c)
print("for loop :" + str(1000*(toc-tic)) + "ms")
```

    250120.5894239894
    vectorized version:1.9960403442382812ms
    250120.5894239858
    for loop :386.0652446746826ms


# python中的广播


```python
import numpy as np
A= np.array([[56.0,0.0,4.4,68.0],
             [1.2,104.0,52.0,8.0],
             [1.8,135.0,99.0,0.9]])
print(A)
cal = A.sum(axis =0) #求和运算，按列执行 axis用来指明进行的运算是沿着哪个轴执行，在numpy中0轴是列，1轴是水平的，即行。
print(cal)
percentage = 100*A/cal.reshape(1,4) #将3*4矩阵A除以一个1*4矩阵，得到一个3*4矩阵
print(percentage)
```

    [[ 56.    0.    4.4  68. ]
     [  1.2 104.   52.    8. ]
     [  1.8 135.   99.    0.9]]
    [ 59.  239.  155.4  76.9]
    [[94.91525424  0.          2.83140283 88.42652796]
     [ 2.03389831 43.51464435 33.46203346 10.40312094]
     [ 3.05084746 56.48535565 63.70656371  1.17035111]]


axis用来指明将要进行的运算是沿着哪个轴执行，在numpy中，0轴是垂直的，也就是列，而1轴是水平的，也就是行。


# 15 关于python_numpy向量的说明


```python
import numpy as np
a = np.random.randn(5) #生成5个高斯随机数变量存储在数组a中
print(a) #数组a的形状shape是一个(5,)形状，一个一维数组，不是行/列向量。不直观
np.shape(a) #输出数组的shape导入numpy模块，里面有一个shape函数，要使用这个函数，numpy.shape()即可，但是不加numpy就不行，因为只有在numpy的命名空间里面才有个shape
print(a.T) #输出a的转置
print(np.dot(a,a.T))#输出数组a和a的转置的内积，结果不是矩阵，是一个数。
```

    [ 0.19718626 -0.55938823 -0.14788369 -1.8337937   0.63666497]
    [ 0.19718626 -0.55938823 -0.14788369 -1.8337937   0.63666497]
    4.141808818121443



```python
import numpy as np
a = np.random.randn(5,1) #如果设置a为(5,1)，则将其置于5行1列向量中，
print(a)
print(a.T) #此时a的转置是一个行向量，上面只有一对方括号，现在有两对，即1行5列的矩阵和一维数组的差别。
print(np.dot(a,a.T)) #此时输出是一个矩阵
```

    [[ 0.13184372]
     [-1.72236441]
     [ 0.89974126]
     [ 0.28644756]
     [ 0.35497523]]
    [[ 0.13184372 -1.72236441  0.89974126  0.28644756  0.35497523]]
    [[ 0.01738277 -0.22708294  0.11862524  0.03776631  0.04680126]
     [-0.22708294  2.96653915 -1.54968232 -0.49336707 -0.6113967 ]
     [ 0.11862524 -1.54968232  0.80953434  0.25772868  0.31938586]
     [ 0.03776631 -0.49336707  0.25772868  0.0820522   0.10168179]
     [ 0.04680126 -0.6113967   0.31938586  0.10168179  0.12600741]]


a = np.random.randn(5,1) a.shape=(5,1)，column vector（列向量）
a = np.random.randn(1,5) a.shape=(1,5), row vector（行向量）
要去简化你的代码，而且不要使用一维数组。总是使用 $n \times 1$ 维矩阵（基本上是列向量），或者 $1 \times n$ 维矩阵（基本上是行向量），这样你可以减少很多assert语句来节省核矩阵和数组的维数的时间。另外，为了确保你的矩阵或向量所需要的维数时，不要羞于 reshape 操作。

# TensorFlow

假设有一个损失函数$J(w)= w^2 -10w +25$，最小化，可见$w=5$。TensorFlow实现过程：


```python
import numpy as np
import tensorflow as tf
#导入TensorFlow

w= tf.Variable(0,dtype = tf.float32)
#定义参数w，在TensorFlow中，使用tf.Variable()来定义

cost = tf.add(tf.add(w**2,tf.multiply(- 10.,w)),25)
#定义损失函数J

train = tf.train.GradientDescentOptimizer(0.01).minimize(cost)
#学习率为0.01，目标是最小化损失

init = tf.global_variables_initializer()

session = tf.Session()#开启一个TensorFlow session
session.run(init)#初始化全局变量

session.run(w)#让TensorFlow评估一个变量，将w初始化为0，并定义损失函数，定义train为学习算法
#使用梯度下降法使得损失函数最小化
#此时还没有运行学习算法。
print(session.run(w))

```

    0.0


# 加载本地python文件

执行命令：
%load python文件的绝对路径
ctrl+enter执行
第一次执行，是将本地的Python文件内容加载到单元格内。此时，Jupyter Notebook会自动将“%load”命令注释掉（即在前边加井号“#”），以便在执行已加载的文件代码时不重复执行该命令；第二次执行，则是执行已加载文件的代码。


```python
# %load C:/Users/JXJ/Desktop/test.py
print("hello world")
```

    hello world


# 直接运行python文件

%run Python文件的绝对路径
或
!python3 Python文件的绝对路径
或
!python Python文件的绝对路径

ctrl+enter执行


```python
%run ~/Desktop/test.py
```

    hello world


#  import

`import`和`from…import`来导入相应的模块。

# 数据类型

py3中有6哥标准的数据类型：
1. number（数字）
2. string（字符串）
3. list（列表）
4. tuple（元组）
5. set（集合）
6. dictionary（字典）

不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。

## 数字
Python3 支持 int、float、bool、complex（复数）。

在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。

像大多数语言一样，数值类型的赋值和计算都是很直观的。

内置的 type() 函数可以用来查询变量所指的对象类型。


```python
a,b,c,d=20,5.5,True,4+3j
print(type(a),type(b),type(c),type(d))
```

    <class 'int'> <class 'float'> <class 'bool'> <class 'complex'>


还可以用isinstance来判断


```python
a=11
isinstance(a,int)
```




    True



isinstance 和 type 的区别在于：

type()不会认为子类是一种父类类型。
isinstance()会认为子类是一种父类类型。

还可以使用del语句删除一些对象引用。
del语句的语法是：
`del var1[,var2[,var3[……,varN]]]`

## string

Python中的字符串用单引号 ' 或双引号 " 括起来，同时使用反斜杠 \ 转义特殊字符。

字符串的截取的语法格式如下：
`变量[头下标：尾下标]`

加号 + 是字符串的连接符， 星号 * 表示复制当前字符串，紧跟的数字为复制的次数


```python
str = 'Runoob'
print(str) #输出字符串
print(str[0:-1]) #输出第一个到倒数第二个的所有字符
print (str[0])       # 输出字符串第一个字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str * 2)      # 输出字符串两次
print (str + "TEST") # 连接字符串

print('Ru\noob')
print(r'Ru\noob')  #字符串前加r（不能用空格），反斜杠不发生转义，表示原始字符串
```

    Runoob
    Runoo
    R
    noo
    noob
    RunoobRunoob
    RunoobTEST
    Ru
    oob
    Ru\noob


## list(列表)

列表可以完成大多数集合类的数据结构实现。列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）。

列表是写在方括号 [] 之间、用逗号分隔开的元素列表。

和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。

列表截取的语法格式如下：
`变量[头下标：尾下标]`

加号 + 是列表连接运算符，星号 * 是重复操作


```python
list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ]
tinylist = [123, 'runoob']
 
print (list)            # 输出完整列表
print (list[0])         # 输出列表第一个元素
print (list[1:3])       # 从第二个开始输出到第三个元素
print (list[2:])        # 输出从第三个元素开始的所有元素
print (tinylist * 2)    # 输出两次列表
print (list + tinylist) # 连接列表
```

    ['abcd', 786, 2.23, 'runoob', 70.2]
    abcd
    [786, 2.23]
    [2.23, 'runoob', 70.2]
    [123, 'runoob', 123, 'runoob']
    ['abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob']


List 内置了有很多方法，例如 append()、pop() 等等，这在后面会讲到。

注意：

1、List写在方括号之间，元素用逗号隔开。
2、和字符串一样，list可以被索引和切片。
3、List可以使用+操作符进行拼接。
4、List中的元素是可以改变的。


```python
#翻转字符串
def reverseWords(input): 
      
    # 通过空格将字符串分隔符，把各个单词分隔为列表
    inputWords = input.split(" ") 
  
    # 翻转字符串
    # 假设列表 list = [1,2,3,4],  
    # list[0]=1, list[1]=2 ，而 -1 表示最后一个元素 list[-1]=4 ( 与 list[3]=4 一样) 
    # inputWords[-1::-1] 有三个参数
    # 第一个参数 -1 表示最后一个元素
    # 第二个参数为空，表示移动到列表末尾
    # 第三个参数为步长，-1 表示逆向
    inputWords=inputWords[-1::-1] 
  
    # 重新组合字符串
    output = ' '.join(inputWords) 
      
    return output 
  
if __name__ == "__main__": 
    input = 'I like runoob'
    rw = reverseWords(input) 
    print(rw)
```

    runoob like I


## tuple(元组)

元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 () 里，元素之间用逗号隔开。

元组中的元素类型也可以不相同：


```python
tuple = ( 'abcd', 786 , 2.23, 'runoob', 70.2  )
tinytuple = (123, 'runoob')
 
print (tuple)             # 输出完整元组
print (tuple[0])          # 输出元组的第一个元素
print (tuple[1:3])        # 输出从第二个元素开始到第三个元素
print (tuple[2:])         # 输出从第三个元素开始的所有元素
print (tinytuple * 2)     # 输出两次元组
print (tuple + tinytuple) # 连接元组
```

    ('abcd', 786, 2.23, 'runoob', 70.2)
    abcd
    (786, 2.23)
    (2.23, 'runoob', 70.2)
    (123, 'runoob', 123, 'runoob')
    ('abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob')



```python
tup = (1,2,3,4,5,6)
print(tup[0])

print(tup[1:5])
```

    1
    (2, 3, 4, 5)


string、list 和 tuple 都属于 sequence（序列）。

注意：

1、与字符串一样，元组的元素不能修改。
2、元组也可以被索引和切片，方法一样。
3、注意构造包含 0 或 1 个元素的元组的特殊语法规则。
4、元组也可以使用+操作符进行拼接。

## set（集合）

集合（set）是由一个或数个形态各异的大小整体组成的，构成集合的事物或对象称作元素或是成员。

基本功能是进行成员关系测试和删除重复元素。

可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。


```python
student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
 
print(student)   # 输出集合，重复的元素被自动去掉
 
# 成员测试
if 'Rose' in student :
    print('Rose 在集合中')
else :
    print('Rose 不在集合中')
 
 
# set可以进行集合运算
a = set('abracadabra')
b = set('alacazam')
 
print(a)
 
print(a - b)     # a 和 b 的差集
 
print(a | b)     # a 和 b 的并集
 
print(a & b)     # a 和 b 的交集
 
print(a ^ b)     # a 和 b 中不同时存在的元素
```

    {'Rose', 'Tom', 'Mary', 'Jack', 'Jim'}
    Rose 在集合中
    {'b', 'a', 'd', 'c', 'r'}
    {'b', 'd', 'r'}
    {'a', 'b', 'l', 'r', 'd', 'm', 'z', 'c'}
    {'a', 'c'}
    {'b', 'l', 'r', 'm', 'z', 'd'}


## dictionary

列表是有序的对象集合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。

字典是一种映射类型，字典用 { } 标识，它是一个无序的 键(key) : 值(value) 的集合。

键(key)必须使用不可变类型。

在同一个字典中，键(key)必须是唯一的。


```python
dict = {}
dict['one'] = "1 - 菜鸟教程"
dict[2]     = "2 - 菜鸟工具"
 
tinydict = {'name': 'runoob','code':1, 'site': 'www.runoob.com'}
 
 
print (dict['one'])       # 输出键为 'one' 的值
print (dict[2])           # 输出键为 2 的值
print (tinydict)          # 输出完整的字典
print (tinydict.keys())   # 输出所有键
print (tinydict.values()) # 输出所有值
```

    1 - 菜鸟教程
    2 - 菜鸟工具
    {'code': 1, 'name': 'runoob', 'site': 'www.runoob.com'}
    dict_keys(['code', 'name', 'site'])
    dict_values([1, 'runoob', 'www.runoob.com'])


构造函数 dict() 可以直接从键值对序列中构建字典如下：
dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
x: x**2 for x in (2, 4, 6)}
dict(Runoob=1, Google=2, Taobao=3)

另外，字典类型也有一些内置的函数，例如clear()、keys()、values()等。

注意：

1、字典是一种映射类型，它的元素是键值对。
2、字典的关键字必须为不可变类型，且不能重复。
3、创建空字典使用 { }。

## python数据类型转换

需要对数据内置的类型进行转换，数据类型的转换，你只需要将数据类型作为函数名即可。

# 函数

## 语法

函数代码块以 **def**管金子开头，后接函数标识符名称和圆括号()。

任何传入的参数和自变量必须放在圆括号内，括号内可以用于定义参数。

函数的第一行语句可以选择性使用文档字符串来存放函数说明。

函数内容以冒号起始，并且缩进。

`return[表达式]`结束函数。不带表达式的return相当于返回none。

def 函数名(参数列表):
    函数体


```python
#计算面积的函数
def area(width,height):
    return width*height

def print_welcome(name):
    print("welcome",name)
    
print_welcome("Roob")
w=4
h=5
print("width=",w, "height = ",h, "area = ", area(w,h))
```

    welcome Roob
    width= 4 height =  5 area =  20


## 函数调用

定义一个函数：给定函数名称，指定函数里包含的参数，和代码块结构。

可以通过另一个函数调用执行，也可以直接从python命令提示符执行。


```python
def printme(str):
    #打印任何出入的字符串
    print(str)
    return
#调用函数
printme("调用任何函数")
printme("再次调用")
```

    调用任何函数
    再次调用


## 参数传递

`a =[1,2,3]` list类型
`a="runoob"` string类型
变量a没有类型，仅仅是一个对象的引用（一个指针），可以指向list类型对象，也可以指向string类型对象。

**可更改(mutable)与不可更改(immutable)对象**
在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

**不可变类型**：变量赋值 a=5 后再赋值 a=10，这里实际是新生成一个 int 值对象 10，再让 a 指向它，而 5 被丢弃，不是改变a的值，相当于新生成了a。

**可变类型**：变量赋值 `la=[1,2,3,4]` 后再赋值` la[2]=5 `则是将 list la 的第三个元素值更改，本身la没有动，只是其内部的一部分值被修改了。

python 函数的参数传递：

**不可变类型**：类似 c++ 的值传递，如 整数、字符串、元组。如fun（a），传递的只是a的值，没有影响a对象本身。比如在 fun（a）内部修改 a 的值，只是修改另一个复制的对象，不会影响 a 本身。

**可变类型**：类似 c++ 的引用传递，如 列表，字典。如 fun（la），则是将 la 真正的传过去，修改后fun外部的la也会受影响


```python
#传不可变对象
def changeint(a):
    a =10

b=2
changeint(b)
print(b)
```

    2


结果是2，在传递给changeint函数时，按传值形式复制了变量b，相当于修改了另一个复制的对象，本身b的值不受影响。还是2


```python
#传可变对象实例

#可写函数说明
def changeme( mylist ):
  # "修改传入的列表"
   mylist.append([1,2,3,4])
   print ("函数内取值: ", mylist)
   return

#调用changeme函数

mylist = [10,20,30]
changeme( mylist )
print ("函数外取值: ", mylist)
```

    函数内取值:  [10, 20, 30, [1, 2, 3, 4]]
    函数外取值:  [10, 20, 30, [1, 2, 3, 4]]


## 参数

**必需参数**：必须以正确的顺序传入函数，调用时的数量必须和声明的一样。

**关键字参数**：函数调用使用关键字参数来确定传入的参数值。使用关键字参数允许函数调用时参数的顺序和声明时不一致，python解释器能够用参数名匹配参数值。

**默认参数**：调用函数时，如果没有传递参数，则会使用默认参数。

**不定长参数**：函数处理比起始声明时更多的参数。声明时不会命名。基本语法如下：
```
def functionname([formal_args,] *var_args_tuple): 
"函数_文档字符串"
function_suite
return [expression]



​```python
#参数使用不需要使用指定顺序，关键字参数
#可写函数说明
def printinfo(name,age):
    #打印任何传入的字符串
    print("名字：", name)
    print("年龄：",age)
    return

#调用printinfo函数
printinfo(age = 50,name = "runoob")
```

    名字： runoob
    年龄： 50



```python
#不定长参数

# 可写函数说明
def printinfo( arg1, *vartuple ):
#加星号的参数会以元组tuple的形式，存放所有未命名的变量参数
  # "打印任何传入的参数"
   print ("输出: ")
   print (arg1)
   print (vartuple)
 
# 调用printinfo 函数
printinfo( 70, 60, 50 )
```

    输出: 
    70
    (60, 50)


如果在函数调用时没有指定参数，它就是一个空元组。也可以不向函数传递未命名的变量


```python
# 可写函数说明
def printinfo( arg1, *vartuple ):
   "打印任何传入的参数"
   print ("输出: ")
   print (arg1)
   for var in vartuple:
      print (var)
   return
 
# 调用printinfo 函数
printinfo( 10 )
printinfo( 70, 60, 50 )
```

    输出: 
    10
    输出: 
    70
    60
    50


加了两个星号 ** 的参数会以字典的形式导入。


```python
# 可写函数说明
def printinfo( arg1, **vardict ):
   "打印任何传入的参数"
   print ("输出: ")
   print (arg1)
   print (vardict)
 
# 调用printinfo 函数
printinfo(1, a=2,b=3)
```

    输出: 
    1
    {'b': 3, 'a': 2}


## 匿名函数

python使用lambda来创建匿名函数。

即不使用def语句这样的标准的形式定义一个函数

lambda只是一个表达式

lambda的主体是一个表达式，而不是一个代码块。仅能在lambda表达式中封装有限的逻辑进去。

lambda函数拥有自己的命名空间，且不能访问自己参数列表之外或全局命名空间中的参数。

lambda函数语法只包含一个语句，如下：
`lambda [arg1[,arg2,...argn]]:expression`


```python
# 可写函数说明
sum = lambda arg1, arg2: arg1 + arg2
 
# 调用sum函数
print ("相加后的值为 : ", sum( 10, 20 ))
print ("相加后的值为 : ", sum( 20, 20 ))
```

    相加后的值为 :  30
    相加后的值为 :  40


## 变量作用域

python中变量不是在任何位置都可以访问，访问权限决定于这个变量是在哪里赋值的。

作用域有四种：
L （Local） 局部作用域
E （Enclosing） 闭包函数外的函数中
G （Global） 全局作用域
B （Built-in） 内置作用域（内置函数所在模块的范围）

以 L –> E –> G –>B 的规则查找，即：在局部找不到，便会去局部外的局部找（例如闭包），再找不到就会去全局找，再者去内置中找。


```python
total = 0 # 这是一个全局变量
# 可写函数说明
def sum( arg1, arg2 ):
    #返回2个参数的和."
    total = arg1 + arg2 # total在这里是局部变量.
    print ("函数内是局部变量 : ", total)
    return total
 
#调用sum函数
sum( 10, 20 )
print ("函数外是全局变量 : ", total)
```

    函数内是局部变量 :  30
    函数外是全局变量 :  0


## global和nonlocal关键字

当内部作用域想修改外部作用域的变量时，用到。


```python
#修改全局变量num
#用到关键字global

num = 1
def fun1():
    global num 
    print(num)
    num = 123
    print(num)
    
fun1()
print(num)
```

    1
    123
    123



```python
#修改嵌套作用域（enclosing作用域，外层非全局作用域）中的变量
#使用nonlocal关键字

def outer():
    num = 10
    def inner():
        nonlocal num 
        num = 100
        print(num)
    inner()
    print(num)

outer()
```

    100
    100



```python
"""
a = 10
def test():
    a = a + 1
    print(a)
test()
#test函数中的a使用的是局部，未定义，无法修改。报错
"""
#修改a为全局变量，通过函数参数传递，可正常输出
a = 10
def test(a):
    a = a + 1
    print(a)
test(a)
```

    11


# 数据结构

## 字符串

使用`'`或`"`来创建字符串，只要为变量分配一个值即可。

python不支持单个字符类型，访问子字符串，使用方括号截取字符串。



```python
var1 = 'Hello World!'
var2 = "Runoob"
 
print ("var1[0]: ", var1[0])
print ("var2[1:5]: ", var2[1:5])
```

    var1[0]:  H
    var2[1:5]:  unoo


### 转义字符

需要在字符串中使用特殊字符时，用反斜杠（\）转义字符

### 字符串运算符

|操作符|	描述|	实例|
|:--|:--|:--|
|+|字符串连接|a+b输出 hello py|
|`*`|重复输出字符串|a`*`2输出结果hellohello|
|[]|通过索引获取字符串中字符|a[1]输出结果为e|
|[:]|截取字符串一部分，遵循左闭右开原则，str[0:2]不包含第3个字符|a[1:4]输出结果为ell|
|in|成员运算符,包含则输出true|‘H’in a输出true|
|%|格式字符串|将一个值插入一个有字符串格式符%的字符串中|

### 字符串格式化

在 Python 中，字符串格式化使用与 C 中 sprintf 函数一样的语法。


```python
print ("我叫 %s 今年 %d 岁!" % ('小明', 10))
```

    我叫 小明 今年 10 岁!


|符   号	|描述|
|:--|:--|
|  %c	| 格式化字符及其ASCII码|
|   %s	| 格式化字符串|
|  %d	| 格式化整数|
|  %u	| 格式化无符号整型|
|  %o	| 格式化无符号八进制数|
|  %x	| 格式化无符号十六进制数|
|  %X	 |格式化无符号十六进制数（大写）|
|  %f	| 格式化浮点数字，可指定小数点后的精度|
| %e	| 用科学计数法格式化浮点数|
| %E	 |作用同%e，用科学计数法格式化浮点数|
|  %g	| %f和%e的简写|
|  %G	 |%f 和 %E 的简写|
|  %p	| 用十六进制数格式化变量的地址|

Python2.6 开始，新增了一种格式化字符串的函数 str.format()，它增强了字符串格式化的功能。

**基本语法**是通过 `{}` 和 `: `来代替以前的 `% `。

format 函数可以接受不限个参数，位置可以不按顺序。

格式化操作辅助指令：

|符号|	功能|
|:--|:--|
|`*`|	定义宽度或者小数点精度|
|`-`	|用做左对齐|
|`+`	|在正数前面显示加号( + )|
|`<sp>`|	在正数前面显示空格|
|`#`|	在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')|
|`0`	|显示的数字前面填充'0'而不是默认的空格|
|`%`	|'%%'输出一个单一的'%'|
|`(var)`|	映射变量(字典参数)|
|`m.n.`	|m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)|


```python
"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
```




    'hello world'




```python
"{0} {1}".format("hello", "world")  # 设置指定位置
```




    'hello world'




```python
"{1} {0} {1}".format("hello", "world")  # 设置指定位置
```




    'world hello world'




```python
#设置参数
print("网站名：{name}, 地址 {url}".format(name="菜鸟教程", url="www.runoob.com"))

# 通过字典设置参数
site = {"name": "菜鸟教程", "url": "www.runoob.com"}
print("网站名：{name}, 地址 {url}".format(**site))
 
# 通过列表索引设置参数
my_list = ['菜鸟教程', 'www.runoob.com']
print("网站名：{0[0]}, 地址 {0[1]}".format(my_list))  # "0" 是必须的
```

    网站名：菜鸟教程, 地址 www.runoob.com
    网站名：菜鸟教程, 地址 www.runoob.com
    网站名：菜鸟教程, 地址 www.runoob.com



```python
#可以向str.format()传入对象

class AssignValue(object):
    def __init__(self, value):
        self.value = value
my_value = AssignValue(6)
print('value 为: {0.value}'.format(my_value))  # "0" 是可选的
```

    value 为: 6


### 三引号

python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。

一个典型的用例是，当你需要一块HTML或者SQL时，这时用字符串组合，特殊字符串转义将会非常的繁琐。


```python
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print (para_str)
```

    这是一个多行字符串的实例
    多行字符串可以使用制表符
    TAB ( 	 )。
    也可以使用换行符 [ 
     ]。


​    

### Unicode字符串

在Python2中，普通字符串是以8位ASCII码进行存储的，而Unicode字符串则存储为16位unicode字符串，这样能够表示更多的字符集。使用的语法是在字符串前面加上前缀 u。

在Python3中，所有的字符串都是Unicode字符串。

### 字符串内建函数

序号	方法及描述
1	
capitalize()
将字符串的第一个字符转换为大写

2	
center(width, fillchar)


返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。
3	
count(str, beg= 0,end=len(string))


返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数
4	
bytes.decode(encoding="utf-8", errors="strict")


Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。
5	
encode(encoding='UTF-8',errors='strict')


以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'
6	
endswith(suffix, beg=0, end=len(string))
检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.

7	
expandtabs(tabsize=8)


把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。
8	
find(str, beg=0, end=len(string))


检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1
9	
index(str, beg=0, end=len(string))


跟find()方法一样，只不过如果str不在字符串中会报一个异常.
10	
isalnum()


如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False
11	
isalpha()


如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False
12	
isdigit()


如果字符串只包含数字则返回 True 否则返回 False..
13	
islower()


如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False
14	
isnumeric()


如果字符串中只包含数字字符，则返回 True，否则返回 False
15	
isspace()


如果字符串中只包含空白，则返回 True，否则返回 False.
16	
istitle()


如果字符串是标题化的(见 title())则返回 True，否则返回 False
17	
isupper()


如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False
18	
join(seq)


以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串
19	
len(string)


返回字符串长度
20	
ljust(width[, fillchar])


返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。
21	
lower()


转换字符串中所有大写字符为小写.
22	
lstrip()


截掉字符串左边的空格或指定字符。
23	
maketrans()


创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。
24	
max(str)


返回字符串 str 中最大的字母。
25	
min(str)


返回字符串 str 中最小的字母。
26	
replace(old, new [, max])


把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。
27	
rfind(str, beg=0,end=len(string))


类似于 find()函数，不过是从右边开始查找.
28	
rindex( str, beg=0, end=len(string))


类似于 index()，不过是从右边开始.
29	
rjust(width,[, fillchar])


返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串
30	
rstrip()


删除字符串字符串末尾的空格.
31	
split(str="", num=string.count(str))


num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串
32	
splitlines([keepends])


按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。
33	
startswith(substr, beg=0,end=len(string))


检查字符串是否是以指定子字符串 substr 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。
34	
strip([chars])


在字符串上执行 lstrip()和 rstrip()
35	
swapcase()


将字符串中大写转换为小写，小写转换为大写
36	
title()


返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle())
37	
translate(table, deletechars="")


根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中
38	
upper()


转换字符串中的小写字母为大写
39	
zfill (width)


返回长度为 width 的字符串，原字符串右对齐，前面填充0
40	
isdecimal()


检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。

## 列表

**列表可以修改，则字符串和元组不能。**

创建一个列表：用逗号分隔不同的数据项，使用方括号括起来。

`list1=[1,2,3,4,5]`

`list2=['google','baidu']`

列表索引从0开始，列表可以进行截取、组合等。

**访问列表的值**：

使用下标索引来访问列表的值，可以用使用方括号截取字符。

**更新列表**：

可以使用`append()`方法来添加列表项。

**删除列表元素**：

使用`del`语句来删除列表的元素。还有`remove()`函数方法




```python
#访问列表的值
list1 = ['Google', 'Runoob', 1997, 2000];
list2 = [1, 2, 3, 4, 5, 6, 7 ];
 
print ("list1[0]: ", list1[0])
print ("list2[1:5]: ", list2[1:5]) #列表截取和拼接
```

    list1[0]:  Google
    list2[1:5]:  [2, 3, 4, 5]



```python
#更新列表
list = ['Google', 'Runoob', 1997, 2000]
 
print ("第三个元素为 : ", list[2])
list[2] = 2001 
print ("更新后的第三个元素为 : ", list[2])
```

    第三个元素为 :  1997
    更新后的第三个元素为 :  2001



```python
#删除列表元素
list = ['Google', 'Runoob', 1997, 2000]
 
print ("原始列表 : ", list)
del list[2]
print ("删除第三个元素 : ", list)
```

    原始列表 :  ['Google', 'Runoob', 1997, 2000]
    删除第三个元素 :  ['Google', 'Runoob', 2000]


**列表脚本操作符**

+用于组合列表,拼接，`*`用于重复列表

|Python表达式|	结果|	描述|
|:--|:--|:--|
|len([1, 2, 3])|	3|	长度|
|[1, 2, 3] + [4, 5, 6]|	[1, 2, 3, 4, 5, 6]|	组合|
|['Hi!'] * 4|	['Hi!', 'Hi!', 'Hi!', 'Hi!']|	重复|
|3 in [1, 2, 3]|	True	|元素是否存在于列表中|
|for x in [1, 2, 3]: print(x, end=" ")	|1 2 3	|迭代|

|方法|描述|
|:--|:--:|
|len(list)|列表元素个数|
|max(list)|返回列表最大值|
|min(list)|最小值|
|list(seq|将元组转换为列表|
|list.append(x)|把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]。|
|list.extend(L)|	通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L。|
|list.insert(i, x)|	在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。|
|list.remove(x)	|删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。|
|list.pop([i])	|从列表的指定位置移除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被移除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。）|
|list.clear()	|移除列表中的所有项，等于del a[:]。|
|list.index(x)	|返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。|
|list.count(x)|	返回 x 在列表中出现的次数。|
|list.sort()|	对列表中的元素进行排序。|
|list.reverse()	|倒排列表中的元素。|
|list.copy()|	返回列表的浅复制，等于a[:]。|


```python
a = [66.25, 333, 333, 1, 1234.5]
print(a.count(333), a.count(66.25), a.count('x'))

a.append(333)
print(a)

a.remove(333)
print(a)

a.reverse()
print(a)

a.index(333)
print(a)
```

    2 1 0
    [66.25, 333, 333, 1, 1234.5, 333]
    [66.25, 333, 1, 1234.5, 333]
    [333, 1234.5, 1, 333, 66.25]
    [333, 1234.5, 1, 333, 66.25]


### 将列表当做堆栈使用

 **堆栈** 特定的数据结构，最先进入的元素最后一个被释放（后进先出）。

 用append()方法可以把一个元素添加到堆栈项。

 用不指定索引的pop()方法可以把一个元素从**堆栈顶**释放出来。


```python
stack = [3,4,5]
stack.append(6)
stack.append(7)
print(stack)
stack.pop()
```

    [3, 4, 5, 6, 7]





    7



### 将列表当作队列使用

在队列中加入的第一个元素，第一个被取出来；列表做这样的目的效率不高。

在列表的最后添加或弹出元素速度快，但是在头部插入或弹出速度不快。（因为所有元素需要一个个地移动）


### 列表推导式

提供了从序列创建列表的简单途径。应用程序将一些操作应用于某个序列的每个元素，用获得的元素结果作为生成新列表的元素，或者根据确定的判定条件创建子序列。

每个列表推导式都在 for 之后跟一个表达式，然后零到多个 for 或 if 子句。

返回结果是一个根据表达从其后的for和if上下文环境中生成出来的列表。

如果希望表示推导出一个元组，必须使用括号。


```python
vec =[2,4,6]
[3*x for x in vec]

```




    [6, 12, 18]




```python
vec = [2,4,6]
[[x,x**2] for x in vec]
```




    [[2, 4], [4, 16], [6, 36]]




```python
#对序列里的每一个元素逐个调用某方法

freshfruit = ['banana','loganberry','passion fruit']
[weapon.strip() for weapon in freshfruit]

#Python strip() 方法用于移除字符串头尾指定的字符（默认为空格或换行符）或字符序列。

#注意：该方法只能删除开头或是结尾的字符，不能删除中间部分的字符。
```




    ['banana', 'loganberry', 'passion fruit']




```python
#用if子句作为过滤器

[3*x for x in vec if x >3]
```




    [12, 18]




```python
[3*x for x in vec if x <2]
```




    []




```python
#关于循环和其它技巧

vec1 = [2,4,6]
vec2 = [4,3,-9]

[x*y for x in vec1 for y in vec2]

```




    [8, 6, -18, 16, 12, -36, 24, 18, -54]




```python
vec1 = [2,4,6]
vec2 = [4,3,-9]
[x+y for x in vec1 for y in vec2]
```




    [6, 5, -7, 8, 7, -5, 10, 9, -3]




```python
vec1 = [2,4,6]
vec2 = [4,3,-9]
[ vec1[i]*vec2[i]  for i in range(len(vec1))  ]
```




    [8, 12, -54]



列表推导式可以使用复杂表达式或嵌套函数


```python
[str(round(355/113,i)) for i in range(1,6)  ]
#round()返回浮点数四舍五入的值，i表示几位小数
```




    ['3.1', '3.14', '3.142', '3.1416', '3.14159']



## del语句

使用del语句可以从一个列表中依索引而不是值来删除一个元素，与使用pop()返回一个值不同。

可以使用del语句从列表中删除一个切割，或清空整个列表。

## 元组和序列

元组由若干逗号分隔的值组成。

元组在输出时总是有括号的，以便于正确的表达嵌套结构。


```python
t = 12345,54312,'hello!'
print(t)
```

    (12345, 54312, 'hello!')



```python
t = 12345,54312,'hello!'
print(t[0])
```

    12345



```python
t = 12345,54312,'hello!'
u = t,(1,2,3,4,6)
print(u)
```

    ((12345, 54312, 'hello!'), (1, 2, 3, 4, 6))


## 集合

集合是一个无序不重复元素的集，基本功能包括关系测试和消除重复元素。

可以用（{}）创建集合。

如果创建空集，必须使用`set()`而不是{}。相当于创建一个空的字典。


```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)                      # 删除重复的
```

    {'banana', 'apple', 'orange', 'pear'}



```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
'orange' in basket  #检测成员
```




    True




```python
#两个集合的操作

a = set('abracadabra')
b = set('alacazam')

print(a) #唯一字母

print(a-b) #在集合a而不在集合b中

print(a|b) #在a或b中

print(a & b) #在a和b中都有的字母

print(a^b) #在a或b中，但不同时在a和b中
```

    {'a', 'b', 'd', 'c', 'r'}
    {'b', 'd', 'r'}
    {'l', 'r', 'a', 'm', 'b', 'z', 'd', 'c'}
    {'a', 'c'}
    {'l', 'd', 'm', 'b', 'z', 'r'}



```python
#集合也支持推导式

a= {x  for x in 'abracadabra' if x not in 'abc'}
print (a)
```

    {'d', 'r'}


## 字典

序列是以连续的整数为索引，与此不同，字典以**关键字**为索引，关键字可以是任意不可变类型，通常用字符串或数值。

字典可以看成 无序的键=》值对集合。

在一个字典中，关键字必须互不相同。

一对大括号创建一个空的字典：{}。


```python
tel = {'jack': 4098, 'sape': 4139}
tel['guido'] = 4127
print(tel)
tel['jack']


```

    {'sape': 4139, 'guido': 4127, 'jack': 4098}





    4098




```python
tel = {'jack': 4098, 'sape': 4139}

del tel['sape']
tel['irv'] = 4127

print(tel)


list(tel.keys()) 

'irv' in tel
```

    {'irv': 4127, 'jack': 4098}





    True



构造 dict()直接从键值对元组列表中构建字典。

如果有固定的模式，列表推导式指定特定的键值对



```python
 dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
    
```




    {'guido': 4127, 'jack': 4098, 'sape': 4139}




```python
# 字典可以创建任意键和值的表达式词典
{x: x**2 for x in (2, 4, 6)}

```




    {2: 4, 4: 16, 6: 36}



## 遍历技巧

在字典中遍历时，关键字和对应的值可以使用` items()` 方法同时解读出来：


```python
knights = {'gallahad': 'the pure', 'robin': 'the brave'}
for k, v in knights.items():
         print(k, v)
```

    gallahad the pure
    robin the brave


在序列中遍历时，索引位置和对应值可以使用 `enumerate()` 函数同时得到：


```python
for i, v in enumerate(['tic', 'tac', 'toe']):
    print(i, v)
```

    0 tic
    1 tac
    2 toe


同时遍历两个或更多的序列，可以使用 `zip()` 组合：


```python
questions = ['name', 'quest', 'favorite color']
answers = ['lancelot', 'the holy grail', 'blue']
for q, a in zip(questions, answers):
   print('What is your {0}?  It is {1}.'.format(q, a))
```

    What is your name?  It is lancelot.
    What is your quest?  It is the holy grail.
    What is your favorite color?  It is blue.


要反向遍历一个序列，首先指定这个序列，然后调用 `reversed()` 函数：


```python
for i in reversed(range(1, 10, 2)):
     print(i)
```

    9
    7
    5
    3
    1


要按顺序遍历一个序列，使用 `sorted()`函数返回一个已排序的序列，并不修改原值：


```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
for f in sorted(set(basket)):
    print(f)
```

    apple
    banana
    orange
    pear


# 模块

是一个包含所有定义的函数和变量的文件，后缀名.py。可以被别的程序引入，使用。也是使用python标注库的方法。

python本身带有一些标准的模块库。

## import语句

使用python源文件，需要在另一个源文件执行import语句。语法如下：

`import module1[,module2[,...moduleN]`

当解释器遇到import语句时，如果模块在当前搜索路径就会被导入。

搜索路径是一个解释器会先进行搜索的所有目录的列表。如想要导入模块 support，需要把命令放在脚本的顶端：

support.py文件代码：

filename: support.py

def print_func(par)

   print("hello:",par)
   return


test.py引入support模块：

import support  导入模块

support.print_func("ruboot")  调用模块

输出结果：

hello : ruboot

一个模块只会被导入一次，不管执行多少次import操作。

## from-import语句

from语句把从模块中导入一个指定的部分到当前命名空间，语法如下：

`from modname import name1[,...nameN]]`


```python
def fib(n):    # 定义到 n 的斐波那契数列
    a, b = 0, 1
    while b < n:
        print(b, end=' ')
        a, b = b, a+b
    print()
 
def fib2(n): # 返回到 n 的斐波那契数列
    result = []
    a, b = 0, 1
    while b < n:
        result.append(b)
        a, b = b, a+b
    return result

#from fibo import fib,fib2  
print(fib(500))
```

    1 1 2 3 5 8 13 21 34 55 89 144 233 377 
    None


`from modname import *`把一个模块的所有内容全部导入当前的命名空间内。

## name属性

当一个模块被另一个程序第一次引入时，其主程序将运行。

如果想在模块被引入时，模块中的某一程序块不执行，可以使用`__name__`属性来使得该程序块仅在该模块自身运行时执行。

每一个模块都有一个`__name__`属性，当其值为`__main__`时，表明该模块自身在运行，否则是被引入。（**注意：是双下划线**）


## dir()函数

内置的函数`dir()`可以找到模块内定义的所有名称。以一个字符串列表的形式返回。

## 包

包是一个管理python模块命名空间的形式，采用“点模块名称”。

如一个包的名称是`A.B`，表示一个包A中的子模块B。

在导入一个包的时候，Python 会根据 sys.path 中的目录来寻找这个包中包含的子目录。

目录只有包含一个叫做` __init__.py `的文件才会被认作是一个包。为了避免影响到搜索路径中的有效模块。

`from sound.effects import *`会发生什么？

Python 会进入文件系统，找到这个包里面所有的子模块，一个一个的把它们都导入进来。

Windows平台上工作的就不是非常好，因为Windows是一个大小写不区分的系统。

需要包作者提供一个精确的包的索引。

**导入语句遵循如下规则**：如果包定义文件 `__init__.py` 存在一个叫做` __all__ `的列表变量，那么在使用` from package import * `的时候就把这个列表中的所有名字作为包内容导入。

在更新包之后，需要保证`__all__`也更新，如果没有更新，如在在`:file:sounds/effects/__init__.py`中包含如下代码:

`__all__ = ["echo", "surround", "reverse"]`

这表示当你使用`from sound.effects import *`这种用法时，你只会导入包里面这三个子模块。

如果`__all__`没有定义，则使用`from sound.effects import *`这种用法时不会导入包`sound.effects`里的任何子模块。只是把包和其里面定义的所有内容导入进来。

记住，使用`from Package import specific_submodule`这种方法永远不会有错。事实上，这也是推荐的方法。除非是你要导入的子模块有可能和其他包的子模块重名。

如果在结构中包是一个子包（比如这个例子中对于包sound来说），而你又想导入兄弟包（同级别的包）你就得使用**导入绝对的路径来导入**。

比如，如果模块`sound.filters.vocoder `要使用包`sound.effects`中的模块`echo`，你就要写成 `from sound.effects import echo`。


无论是隐式的还是显式的相对导入都是从**当前模块**开始的。主模块的名字永远是`__main__`，一个Python应用程序的**主模块，应当总是使用绝对路径引用**。

包还提供一个额外的属性`__path__`。这是一个目录列表，里面每一个包含的目录都有为这个包服务的`__init__.py`，你得在其他`__init__.py`被执行前定义哦。可以修改这个变量，用来影响包含在包里面的模块和子包。

# 输入和输出

python输出值的方式中有两种是：

表达式语句和`print()`语句。

第三种是：使用文件对象的`write()`方法，标准输出文件可以用`sys.stdout`引用。

可以使用`str.format()`函数来格式化输出值，进而输出多样的形式。

可以使用`repr()`或`str()`函数来实现将输出的值转成字符串。

str()： 函数返回一个用户易读的表达形式。

repr()： 产生一个解释器易读的表达形式。


```python
s = 'hello,runb'
str(s)

```




    'hello,runb'




```python
s = 'hello,runb'
repr(s)
```




    "'hello,runb'"




```python
x = 10*3.25
y = 200*200
s = 'x的值为：'  + repr(x) +  ', y的值为：' + repr(y)+ '...'
print(s)
```

    x的值为：32.5, y的值为：40000...


有两种方式输出平方和立方的表：



```python
for x in range(1,11):
    print(repr(x).rjust(2), repr(x*x).rjust(3),end=' ')
    #end的使用
    print(repr(x*x*x).rjust(4))
```

     1   1    1
     2   4    8
     3   9   27
     4  16   64
     5  25  125
     6  36  216
     7  49  343
     8  64  512
     9  81  729
    10 100 1000


每列间的空格由print()添加。

`rjust()`将字符串靠右，并在左边填充空格。类似的有`ljust()`和`center()`。这方仅仅返回新的字符串。

还有一个`zfill()`，会在数字的左边填充0。


```python
for x in range(1,11):
    print('{0:2d}{1:3d}{2:4d}'.format(x,x*x,x*x*x))
    
```

     1  1   1
     2  4   8
     3  9  27
     4 16  64
     5 25 125
     6 36 216
     7 49 343
     8 64 512
     9 81 729
    101001000


## str.format()使用


```python
#基本使用如下

print( '{}网址："{}!"'.format('菜鸟教程','www.runbob.com')  )
```

    菜鸟教程网址："www.runbob.com!"


括号及其里面的字符（称为格式化字段）将会被`format()`中的参数替换。


```python
print('{0} 和{1}'.format('google','runboo')  )
```

    google 和runboo



```python
print('{1} 和{0}'.format('google','runboo')  )
```

    runboo 和google


括号内的数字用于指向传入对象在`format()`中的位置。


```python
 print('{name}网址： {site}'.format(name='菜鸟教程', site='www.runoob.com'))
```

    菜鸟教程网址： www.runoob.com


使用关键参数，值会指向使用该名字的参数


```python
print('站点列表 {0}, {1}, 和 {other}。'.format('Google', 'Runoob',  other='Taobao'))
```

    站点列表 Google, Runoob, 和 Taobao。



```python
import math
print('常量PI的值近似为：{}。'.format(math.pi))
print('常量 PI 的值近似为： {!r}。'.format(math.pi))


#可选项（：）和格式标识符可以跟着字段名，允许更好的格式化
print('常量 PI 的值近似为 {0:.3f}。'.format(math.pi))
```

    常量PI的值近似为：3.141592653589793。
    常量 PI 的值近似为： 3.141592653589793。
    常量 PI 的值近似为 3.142。


'!a' (使用 ascii()), '!s' (使用 str()) 和 '!r' (使用 repr()) 可以用于在格式化某个值之前对其进行转化

如果你有一个很长的格式化字符串, 而你不想将它们分开, 那么在格式化时通过变量名而非位置会是很好的事情。

最简单的就是传入一个字典, 然后使用方括号 `'[]'` 来访问键值


```python
table = {'Google':1,'Runoob':2,'Taobao':3}
print('Runoob: {0[Runoob]:d}; Google: {0[Google]:d}; Taobao: {0[Taobao]:d}'.format(table))
```

    Runoob: 2; Google: 1; Taobao: 3


在 `:` 后传入一个整数, 可以保证该域至少有这么多的宽度。 用于美化表格

也可以通过在 table 变量前使用 `**` 来实现相同的功能


```python
table = {'Google':1,'Runoob':2,'Taobao':3}
print('Runoob: {Runoob:d}; Google: {Google:d}; Taobao: {Taobao:d}'.format(**table))
```

    Runoob: 2; Google: 1; Taobao: 3


**旧式字符串格式化**:使用`%`操作符将坐标的参数类似`printf()`格式化字符串，将右边的代入。


```python
import math
print('常量PI的值近似为：%5.3f。' %math.pi)
```

    常量PI的值近似为：3.142。


## 读取键盘的输入

Python提供了` input() `内置函数从标准输入读入一行文本，默认的标准输入是键盘。

input 可以接收一个Python表达式作为输入，并将运算结果返回。

`str = input("请输入：")`

`print("你输入的内容是：",str)`

## 读和写文件

`open()`将会返回一个file对象，基本语法格式如下：

`open(filename,mode)`

filename:包含要访问的文件名称和字符串值。

mode:决定打开文件的模式：只读、写入、追加等。非强制性参数，默认文件访问模式为只读（r）。

|模 式|描述|
|:--:|--:|
|r|	以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。|
|rb|	以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。|
|r+	|打开一个文件用于读写。文件指针将会放在文件的开头。|
|rb+	|以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。|
|w	|打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb	|以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|w+	|打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb+	|以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|a	|打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|ab	|以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|a+|	打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。|
|ab+	|以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。|

![image.png](attachment:image.png)

将字符串写入放在桌面的文件foo.txt中：

`f = open("foo.txt","w")` 打开一个文件，注意路径


第一个参数表示要打开文件名；第二个参数描述文件如何使用。mode可以是`r`只读；`w`只用于写（如果存在同名文件则将被删除），`a`用于追加文件内容，所写的任何数据会被自动添加到末尾；`r+`同时用于读写。mode的参数是可选的，默认是`r`只读。

`f.write( "Python 是一个非常好的语言。\n是的，的确非常好!!\n" )`

`f.close()` 关闭文件



## 文件对象的方法

假设创建的文件对象为f。

### f.read()

读取一个文件的内容，调用`f.read(size)`,读取一定数目的数据，然后作为字符串或字节对象返回。

size是一个可选的数字类型的参数。当size被忽略或为负，则该文件的所有内容都将被读取并且返回。

### f.readline()

会从文件中读取单独一行，换行符为`\n`。

`f.readline()`如果返回一个空字符，说明已经读取到最后一行。

`f.readlines()`将返回该文件中包含的所有行。如果设置可选参数`sizehint`，则读取指定长度的字节，并且将这些字节按行分割。

另一种方式是迭代一个文件对象然后读取每行。

`for line in f:`

    `print(line, end=' ')`

### f.write()

`f.write(string)`将string写入到文件中，然后返回写入的字符数。如：

`f = open("foo.txt","w")`

`num = f.write("Python 是一个非常好的语言。\n是的，的确非常好!!\n")`

`print(num)`

`f.close()`

输出结果为：29

如果写入一些不是字符的东西，需要先进行转换：

`f = open("foo.txt","w")`

`value = ('www.runboo.com',14)`

`s = str(value)`

`f.write(s)`

`f.close()`

### f.tell()

返回文件对象当前所处的位置，它是从文件开头开始算起字节数。

### f.seek()

如果要改变文件当前位置，可以用`f.seek(offset,from_what)`函数。

`from_what`的值，如果是0表示开头，如果是1表示当前位置，2表示文件的结尾。默认值为1，即文件开头。如：

`seek(x,0)` ： 从起始位置即文件首行首字符开始移动 x 个字符

`seek(x,1)` ： 表示从当前位置往后移动x个字符

`seek(-x,2)`：表示从文件的结尾往前移动x个字符

### f.close()

在文本文件中（打开文件模式没有b的），只会相对于文件起始位置进行定位。

当处理完文件后，调用`f.close()`来关闭文件并释放系统的资源，如果尝试再调用该文件，则会抛出异常。


当处理一个文件对象时，使用**with**关键字要比try-finally语句要简短：

`with open('foo.txt','r') as f:`

     `read_data = f.read()`

`f.close()`

## pickle模块

python的pickle模块实现了基本的数据序列的反序列化。

通过pickle模块的序列化操作能够将程序中运行的对象信息保存到文件中，永久存储。

通过pickle模块的反序列化操作，能够从文件中创建上一次程序保存的对象。

基本接口：

`pickle.dump(obj,file,[,protocol])`

然后对file以读取的形式打开：

`x = pickle.load(file)`

其中file是类文件对象，有`read()`和`readline()`接口。

实例1：

`import pickle`

`#使用pickle模块将数据对象保存到文件`

`data1 = {'a':[1,2.0,3,4+6j],
       'b':('string', u'Unicode string'),
       'c': None}`

`selfref_list=[1,2,3]`

`selfref_list.append(selfref_list)`

`output = open('data.txt','wb')`二进制写入文件

`#pickle dictionary using protocol 0.`

`pickle.dump(data1,output)`

`#pickle the list using highest protocol available`

`pickle.dump(selfref_list,output,-1)`

`output.close()`

实例2：

`import pprint, pickle`

`#使用pickle模块从文件中重构python对象`

`pkl_file = open('data.pkl', 'rb')`

`data1 = pickle.load(pkl_file)`

`pprint.pprint(data1)`

`data2 = pickle.load(pkl_file)`

`pprint.pprint(data2)`

`pkl_file.close()`

# 文件(file)方法

## open()

`open()`方法用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用这个函数，如果文件无法打开，抛出 OSError。

使用`open()`一定要保证关闭文件对象，即调用`close()`方法 。

`open()`函数常用形式是接收两个参数：文件名（file）和模式（mode）。即：

`open(file,mode = 'r')`

完整格式为：

`open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)`

参数说明：

ile: 必需，文件路径（相对或者绝对路径）。

mode: 可选，文件打开模式

buffering: 设置缓冲

encoding: 一般使用utf8

errors: 报错级别

newline: 区分换行符

closefd: 传入的file参数类型

opener:


mode参数有：

|模式|	描述|
|:--|:--|
|t|	文本模式 (默认)。|
|x	|写模式，新建一个文件，如果该文件已存在则会报错。|
|b	|二进制模式。|
|+|	打开一个文件进行更新(可读可写)。|
|U	|通用换行模式（不推荐）。|
|r|	以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。|
|rb|	以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。|
|r+|	打开一个文件用于读写。文件指针将会放在文件的开头。|
|rb+|	以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。一般用于非文本文件如图片等。|
|w|	打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb|	以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。|
|w+|	打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb+|	以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。|
|a|	打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|ab|	以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|a+|	打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。|
|ab+|	以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。|

**默认方式**是文本模式，如果要以二进制打开，加上`b`

## file对象

file对象使用`open()`函数创建，常用file函数有：

|序号|	方法及描述|
|--:|--:|	
|file.close()|关闭文件。关闭后文件不能再进行读写操作。|
|file.flush()|刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。|
|file.fileno()|返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。|
|file.isatty()|如果文件连接到一个终端设备返回 True，否则返回 False。|
|file.next()|Python 3 中的 File 对象不支持 next() 方法。返回文件下一行。|
|file.read([size])|从文件读取指定的字节数，如果未给定或为负则读取所有。|
|file.readline([size])|读取整行，包括 "\n" 字符。|
|file.readlines([sizeint])|读取所有行并返回列表，若给定sizeint>0，返回总和大约为sizeint字节的行, 实际读取值可能比 sizeint 较大, 因为需要填充缓冲区。|
|file.seek(offset[, whence])|设置文件当前位置|
|file.tell()|返回文件当前位置。|
|file.truncate([size])|从文件的首行首字符开始截断，截断文件为 size 个字符，无 size 表示从当前位置截断；截断之后后面的所有字符被删除，其中 Widnows 系统下的换行代表2个字符大小。|
|file.write(str)|将字符串写入文件，返回的是写入的字符长度。|
|file.writelines(sequence)|向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。|

# OS 文件/目录

os 模块提供了非常丰富的方法用来处理文件和目录。如：

`os.chdir(path)`改变当前工作目录。

`os.access(path,mode)`检验权限模式

`os.chmod(path,mode)`更改权限

等等。

# 语法错误和异常处理

## 语法错误

称为解析错误。

SyntaxError : invalid syntax

## 异常

即便语法正确，但运行时，也可能发生错误。运行时检测到的错误称为异常。

异常以不同的类型出现，这些类型都作为信息的一部分打印出来: 例子中的类型有 ZeroDivisionError，NameError 和 TypeError。

错误信息的前面部分显示了异常发生的上下文，并以调用栈的形式显示具体信息。

## 异常-try-except语句

`while True:`
     
   `try:`

    `x = int(input("Please enter a number: "))`
     
     `break`

   `except ValueError:`
        
     `print("Oops!  That was no valid number.  Try again   ")`

try语句工作方式：

首先执行try子句（try和except之间语句）

如果没有异常，忽略except子句，try子句执行结束。

如执行try子句有异常，try子句剩余部分忽略，如果异常的类型和except之后的名称相符，对应的except子句将被执行。最后执行try语句之后的代码。

如果异常没有与任何except匹配，那么这个异常会被传递给上层的try中。


一个 try 语句可能包含多个except子句，分别来处理不同的特定的异常。最多只有一个分支会被执行。

处理程序将只针对对应的try子句中的异常进行处理，而不是其他的 try 的处理程序中的异常。

一个except子句可以同时处理多个异常，这些异常将被放在一个括号里成为一个元组。例如：

`except (RuntimeError, TypeError, NameError):
        pass`
        

try except 语句还有一个可选的**else子句**，如果使用这个子句，那么必须放在所有的except子句之后。这个子句将**在try子句没有发生任何异常的时候执行。**

for arg in sys.argv[1:]:

    try:
    
        f = open(arg, 'r')
        
    except IOError:
    
        print('cannot open', arg)
        
    else:
    
        print(arg, 'has', len(f.readlines()), 'lines')
        
        f.close()

## 抛出异常-raise语句

python使用`raise`语句抛出一个指定的异常。例如：

`raise NameError('HiThere')`

`Traceback (most recent call last):`

  `File "<stdin>", line 1, in ?`
    
`NameError: HiThere`
    

`raise`唯一的一个参数指定了要抛出的异常。它必须是一个异常的实例或者是异常的类（即except的子类）。

## 定义清理行为-try-finally语句

`try-finally`定义了无论在任何情况下都会执行的清理行为。

**无论try子句里面有没有发生异常，finally子句都会执行。**

如果一个异常在try子句中（或except或else子句里）被抛出，而没有任何的except把它截住，那么这个异常**在finally子句执行后被抛出。**


```python
def divide(x,y):
    try:
        result = x/y
    except ZeroDivisionError:
        print("division by zero!")
    else:
        print("result is",result)
    finally:
        print("executing finally clause")
divide(2,1)
```

    result is 2.0
    executing finally clause



```python
def divide(x,y):
    try:
        result = x/y
    except ZeroDivisionError:
        print("division by zero!")
    else:
        print("result is",result)
    finally:
        print("executing finally clause")
divide(2,0)
```

    division by zero!
    executing finally clause



```python
def divide(x,y):
    try:
        result = x/y
    except ZeroDivisionError:
        print("division by zero!")
    else:
        print("result is",result)
    finally:
        print("executing finally clause")
divide("2","1")
```

    executing finally clause



    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-28-e99a7014f207> in <module>()
          8     finally:
          9         print("executing finally clause")
    ---> 10 divide("2","1")


    <ipython-input-28-e99a7014f207> in divide(x, y)
          1 def divide(x,y):
          2     try:
    ----> 3         result = x/y
          4     except ZeroDivisionError:
          5         print("division by zero!")


    TypeError: unsupported operand type(s) for /: 'str' and 'str'


# 面向对象

## 面向对象技术简介

1. **类（class）**：描述具有相同的属性和方法的对象的集合。定义了集合中每个对象所共有的属性和方法。对象是类的实例。

2. **方法**：类中定义的函数。

3. **类变量**：在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。

4. **数据成员**：类变量或者实例变量用于处理类及其实例对象的相关的数据。

5. **方法重写**：如果从父类继承的方法不能满足子类的需求，可以对其进行改写。称为**覆盖（override）**，也称为方法重写。

6. **局部变量**：定义在方法中的变量，只作用于当前实例中的类。

7. **实例变量**：在类的声明中，属性是用变量来表示的，称为实例变量，是在类声明内部但是在类的其它成员方法之外声明。

8. **继承**：一个派生类（derived class） 继承  基类（base class）的字段和方法。继承允许把一个派生类的对象作为一个基类对象对待。如一个dog类型的对象派生自animal类。

9. **实例化**：创建一个类的实例，类的具体对象。

10. **对象**：通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。

python类提供了面向对象编程的所有基本功能：类的继承机制允许多个基类，派生类可以覆盖基类中的任何方法，方法中可以调整基类的同名方法。

对象可以包含任意数量和类型的数据。

## 类定义

语法格式：

`class Classname:`

    `<statement-1>`
     
    `<statement-N>` 


​    
创建一个类之后，可以通过类名访问其属性。

## 类对象

类对象支持两种操作：属性引用和实例化

**属性引用**使用标准语法：**obj.name**

类对象创建后。类命名空间中所有命名都是有效属性。


```python
class Myclass:
    """一个简单的类实例"""
    i= 12345
    def f():
        return 'hello world'
    
#实例化
x = Myclass()

#访问类的属性和方法

print("MyClass 类的属性 i为：",x.i)
print("MyClass 类的方法 f输出为：",x.f())
```

    MyClass 类的属性 i为： 12345



    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-2-29be863acd9b> in <module>()
         11 
         12 print("MyClass 类的属性 i为：",x.i)
    ---> 13 print("MyClass 类的方法 f输出为：",x.f())


    TypeError: f() takes 0 positional arguments but 1 was given



```python
class Myclass:
    """一个简单的类实例"""
    i= 12345
    def f(self): #每个与类相关联的方法调用都自动传递实参self，指向实例本身的引用，f()在定义时没有形参，会报错
        return 'hello world'
    
#类实例化操作
x = Myclass()

#访问类的属性和方法

print("MyClass 类的属性 i为：",x.i)
print("MyClass 类的方法 f输出为：",x.f())
```

    MyClass 类的属性 i为： 12345
    MyClass 类的方法 f输出为： hello world


类有一个名为`__init__()`方法（**构造方法**），该方法在类实例化时会自动调用，如：

`def __init__(self):`
       
       `self.data=[]`

类定义了`__init__()`方法，类的实例化操作会自动调用`__init__()`方法。


```python
class Complex:
    def __init__(self,realpart,imagpart): #__init__可以有参数
        self.r = realpart
        self.i = imagpart
    
x = Complex(3.0,-4.5)
print(x.r,x.i)
```

    3.0 -4.5


【注意】：

类的方法和普通函数只有一个特殊的区别——必须有一个额外的**第一个参数**,按照惯例为`self`。


```python
class Test:
    def prt(self):
        print(self)
        print(self.__class__)
        
t = Test()

t.prt()
```

    <__main__.Test object at 0x000002561FC0ADA0>
    <class '__main__.Test'>


self代表的是类的实例，代表当前对象的地址，而`self.class`则指向类。

`self`不是python关键字，换成其它的如`runb`之类的也能正常运行。

## 类的方法

在类的内部，使用`def`关键字来定义一个方法，与一般函数的定义不同。类方法必须包含第一个参数`self`，代表的是类的实例。


```python
#类的定义
class people:
    #定义基本属性
    
    name = ''
    age = 0
    #定义私有属性，私有属性在类外部无法直接进行访问
    __weight = 0
    
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    
    def speak(self):
        print("%s 说：我 %d 岁。" % (self.name,self.age))
        
#实例化类
p = people('runboo',10,30)
p.speak()
        
```

    runboo 说：我 10 岁。


## 继承

派生类的定义如下：

`class DerivedClassName(BaseClassName):`

       <statement-1>
       
       <statement-N>


​       
【注意】：

需要注意圆括号内的基类的顺序，若是基类有相同的方法名，而在子类使用时未指定，python从左至右搜索，即**方法在子类中未找到时，从左到右查找基类中是否包含方法。**


`BaseClassName`(实例中的基类名)必须与派生类定义在一个作用域内。

除了类，还可以用表达式。（这在基类定义在另一个模块中时非常有用。）


```python
class people:
    #定义属性
    name = ''
    age = 0
    #定义私有属性，私有属性在类外部无法直接进行访问
    __weight = 0
    
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    
    def speak(self):
        print("%s 说：我 %d 岁。" % (self.name,self.age))
    
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构造函数
        people.__init__(self,n,a,w)
        self.grade = g
        
    #覆写父类的方法
    def speak(self):
        print("%s 说： 我 %d 岁了，我在读 %d 年级" %(self.name,self.age,self.grade))
        
s = student('ken',10,60,3)
s.speak()
```

    ken 说： 我 10 岁了，我在读 3 年级


## 多继承

class DerivedClassName(Base1, Base2, Base3):

    <statement-1>
    .
    .
    .
    <statement-N>

需要注意**圆括号中父类的顺序**，若是父类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找父类中是否包含方法。


```python
class people:
    #定义属性
    name = ''
    age = 0
    #定义私有属性，私有属性在类外部无法直接进行访问
    __weight = 0
    
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    
    def speak(self):
        print("%s 说：我 %d 岁。" % (self.name,self.age))
    
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构造函数
        people.__init__(self,n,a,w)
        self.grade = g
        
    #覆写父类的方法
    def speak(self):
        print("%s 说： 我 %d 岁了，我在读 %d 年级" %(self.name,self.age,self.grade))
        
#另一类，多重继承之前的准备
class speaker():
    topic = ''
    name = ''
    def __init__(self,n,t):
        self.name = n
        self.topic = t
    def speak(self):
        print("我叫 %s，我是一个演说家，我演讲的主题是 %s"%(self.name,self.topic))

#多重继承

class sample(speaker,student):
    a = ''
    def __init__(self,n,a,w,g,t):
        student.__init__(self,n,a,w,g)
        speaker.__init__(self,n,t)

test = sample("Tim",25,80,4,"python")
test.speak() #方法同名。默认调用的是括号内排在前面的父类方法
```

    我叫 Tim，我是一个演说家，我演讲的主题是 python


## 方法重写


```python
class Parent:        # 定义父类
   def myMethod(self):
      print ('调用父类方法')
 
class Child(Parent): # 定义子类
   def myMethod(self):
      print ('调用子类方法')
 
c = Child()          # 子类实例
c.myMethod()         # 子类调用重写方法
super(Child,c).myMethod() #用子类对象调用父类已被覆盖的方法

#super()函数用于调用父类（超类）的一个方法
```

    调用子类方法
    调用父类方法


## 子类继承父类的构造函数说明

如果在子类中需要父类的构造方法需要显示地调用父类的构造方法，或者不重写父类的构造方法。

子类不重写`__init__()`，实例化子类时，会自动调用父类定义的`__init__()`。


```python
class Father(object):
    def __init__(self, name):
        self.name=name
        print ( "name: %s" %( self.name) )
    def getName(self):
        return 'Father ' + self.name
 
class Son(Father):
    def getName(self):
        return 'Son '+self.name
 
if __name__=='__main__':
    son=Son('runoob')
    print ( son.getName() )
```

    name: runoob
    Son runoob


如果重写了`__init__`函数，实例化子类时，就不会调用父类已经定义的`__init__`。


```python
class Father(object):
    def __init__(self, name):
        self.name=name
        print ( "name: %s" %( self.name) )
    def getName(self):
        return 'Father ' + self.name
 
class Son(Father):
    def __init__(self, name):
        print ( "hi" )
        self.name =  name
    def getName(self):
        return 'Son '+self.name
 
if __name__=='__main__':
    son=Son('runoob')
    print ( son.getName() )
```

    hi
    Son runoob


如果重写`__init__`时，要继承父类的构造方法，可以使用关键字`super`。

`super(子类,self).__init__(参数1,参数2,...)`

另一种经典写法：

`父类名称.__init__(self,参数1,参数2,...)`


```python
class Father(object):
    def __init__(self, name):
        self.name=name
        print ( "name: %s" %( self.name))
    def getName(self):
        return 'Father ' + self.name
 
class Son(Father):
    def __init__(self, name):
        super(Son, self).__init__(name)
        print ("hi")
        self.name =  name
    def getName(self):
        return 'Son '+self.name
 
if __name__=='__main__':
    son=Son('runoob')
    print ( son.getName() )
```

    name: runoob
    hi
    Son runoob


## 类属性和方法

### 类的私有属性

`__private_attrs`:两个下划线开头，声明该属性是私有的，不能在类的外部使用或直接访问。在类的内部的方法中使用时`self.__private_attrs`。

### 类的方法

在类的内部，使用`def`关键字来定义一个方法，类方法必须包含参数`self`作为第一个参数。`self`代表的是类的实例。

一般按照约定用`self`，也可以用`this`。

### 类的私有方法

`__private_methods`:两个下划线开头，声明该方法是私有的，不能在类的外部使用或直接访问。在类的内部的方法中使用时`self.__private_mathods`。

实例如下：


```python
class JustCounter:
    __secretCount = 0  # 私有变量
    publicCount = 0    # 公开变量
 
    def count(self):
        self.__secretCount += 1
        self.publicCount += 1
        print (self.__secretCount)
 
counter = JustCounter()
counter.count()
counter.count()
print (counter.publicCount)
print (counter.__secretCount)  # 报错，实例不能访问私有变量
```

    1
    2
    2



    ---------------------------------------------------------------------------
    
    AttributeError                            Traceback (most recent call last)
    
    <ipython-input-21-eb413b755b77> in <module>()
         12 counter.count()
         13 print (counter.publicCount)
    ---> 14 print (counter.__secretCount)  # 报错，实例不能访问私有变量


    AttributeError: 'JustCounter' object has no attribute '__secretCount'



```python
class Site:
    def __init__(self, name, url):
        self.name = name       # public
        self.__url = url   # private
 
    def who(self):
        print('name  : ', self.name)
        print('url : ', self.__url)
 
    def __foo(self):          # 私有方法
        print('这是私有方法')
 
    def foo(self):            # 公共方法
        print('这是公共方法')
        self.__foo()
 
x = Site('菜鸟教程', 'www.runoob.com')
x.who()        # 正常输出
x.foo()        # 正常输出，内部可以调用私有化方法
x.__foo()      # 报错,外部不能调用私有化方法
```

    name  :  菜鸟教程
    url :  www.runoob.com
    这是公共方法
    这是私有方法



    ---------------------------------------------------------------------------
    
    AttributeError                            Traceback (most recent call last)
    
    <ipython-input-23-9d93b50ee324> in <module>()
         18 x.who()        # 正常输出
         19 x.foo()        # 正常输出
    ---> 20 x.__foo()      # 报错


    AttributeError: 'Site' object has no attribute '__foo'


### 类的专有方法

|方法|描述|
|:--|:--|
|`__init__`|  构造函数，在生成对象时调用|
|`__del__`|  析构函数，释放对象时使用|
|`__repr__` | 打印，转换|
|`__setitem__`|  按照索引赋值|
|`__getitem__`|按照索引获取值|
|`__len__`|获得长度|
|`__cmp__`| 比较运算|
|`__call__`| 函数调用|
|`__add__`| 加运算|
|`__sub__`| 减运算|
|`__mul__`|乘运算|
|`__truediv__`| 除运算|
|`__mod__`| 求余运算|
|`__pow__`| 乘方|

### 运算符重载

python支持运算符重载，可以对类的专有方法进行重载。

类重载可以进行加减运算、打印、函数调用、索引等内置运算，运算符重载使得对象的行为与内置对象一样python在调用操作符时会自动调用这样的方法。

例如：如果类实现了`__add__`方法，当类的对象出现在`+`运算符中时会调用这个方法。


```python
class Vector:
   def __init__(self, a, b):
      self.a = a
      self.b = b
 
   def __str__(self):
      return 'Vector (%d, %d)' % (self.a, self.b)
   
   def __add__(self,other):
      return Vector(self.a + other.a, self.b + other.b)
 
v1 = Vector(2,10)
v2 = Vector(5,-2)
print (v1 + v2)
```

    Vector (7, 8)



```python
class computation():
    def __init__(self,value):
        self.value = value
    def __add__(self,other):
        return self.value + other
    def __sub__(self,other):
        return self.value -other
    
c = computation(5)
c + 5
c-3
```




    2



# 标准库

## 操作系统接口

OS模块提供了不少与操作系统相关联的函数。

`os.getcwd()` 返回当前的工作目录

`os.chdir()`修改当前的工作目录

`os.system('mkdir today')` 执行系统命令mkdir

建议使用`import os`导入模块。这样可以保证随操作系统不同而有所变化的`os.open()`不会覆盖内置函数`open()`。

使用OS这类大型模块的内置的`dir()`和`help()`函数非常有用。

针对于日常的文件和目录管理任务`:mod:shutil`模块提供了一个易于使用的高级接口。

`import shutil`

`shutil.copyfile('data.db', 'archive.db')`

`shutil.move('/build/executables', 'installdir')`


```python
import os
dir(os)
# returns a list of module functions
```




    ['F_OK',
     'MutableMapping',
     'O_APPEND',
     'O_BINARY',
     'O_CREAT',
     'O_EXCL',
     'O_NOINHERIT',
     'O_RANDOM',
     'O_RDONLY',
     'O_RDWR',
     'O_SEQUENTIAL',
     'O_SHORT_LIVED',
     'O_TEMPORARY',
     'O_TEXT',
     'O_TRUNC',
     'O_WRONLY',
     'P_DETACH',
     'P_NOWAIT',
     'P_NOWAITO',
     'P_OVERLAY',
     'P_WAIT',
     'R_OK',
     'SEEK_CUR',
     'SEEK_END',
     'SEEK_SET',
     'TMP_MAX',
     'W_OK',
     'X_OK',
     '_DummyDirEntry',
     '_Environ',
     '__all__',
     '__builtins__',
     '__cached__',
     '__doc__',
     '__file__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     '_dummy_scandir',
     '_execvpe',
     '_exists',
     '_exit',
     '_get_exports_list',
     '_putenv',
     '_unsetenv',
     '_wrap_close',
     'abort',
     'access',
     'altsep',
     'chdir',
     'chmod',
     'close',
     'closerange',
     'cpu_count',
     'curdir',
     'defpath',
     'device_encoding',
     'devnull',
     'dup',
     'dup2',
     'environ',
     'errno',
     'error',
     'execl',
     'execle',
     'execlp',
     'execlpe',
     'execv',
     'execve',
     'execvp',
     'execvpe',
     'extsep',
     'fdopen',
     'fsdecode',
     'fsencode',
     'fstat',
     'fsync',
     'ftruncate',
     'get_exec_path',
     'get_handle_inheritable',
     'get_inheritable',
     'get_terminal_size',
     'getcwd',
     'getcwdb',
     'getenv',
     'getlogin',
     'getpid',
     'getppid',
     'isatty',
     'kill',
     'linesep',
     'link',
     'listdir',
     'lseek',
     'lstat',
     'makedirs',
     'mkdir',
     'name',
     'open',
     'pardir',
     'path',
     'pathsep',
     'pipe',
     'popen',
     'putenv',
     'read',
     'readlink',
     'remove',
     'removedirs',
     'rename',
     'renames',
     'replace',
     'rmdir',
     'scandir',
     'sep',
     'set_handle_inheritable',
     'set_inheritable',
     'spawnl',
     'spawnle',
     'spawnv',
     'spawnve',
     'st',
     'startfile',
     'stat',
     'stat_float_times',
     'stat_result',
     'statvfs_result',
     'strerror',
     'supports_bytes_environ',
     'supports_dir_fd',
     'supports_effective_ids',
     'supports_fd',
     'supports_follow_symlinks',
     'symlink',
     'sys',
     'system',
     'terminal_size',
     'times',
     'times_result',
     'truncate',
     'umask',
     'uname_result',
     'unlink',
     'urandom',
     'utime',
     'waitpid',
     'walk',
     'write']




```python
import os
help(os)
# returns an extensive manual page created from the module's docstring
```

    Help on module os:
    
    NAME
        os - OS routines for NT or Posix depending on what system we're on.
    
    DESCRIPTION
        This exports:
          - all functions from posix, nt or ce, e.g. unlink, stat, etc.
          - os.path is either posixpath or ntpath
          - os.name is either 'posix', 'nt' or 'ce'.
          - os.curdir is a string representing the current directory ('.' or ':')
          - os.pardir is a string representing the parent directory ('..' or '::')
          - os.sep is the (or a most common) pathname separator ('/' or ':' or '\\')
          - os.extsep is the extension separator (always '.')
          - os.altsep is the alternate pathname separator (None or '/')
          - os.pathsep is the component separator used in $PATH etc
          - os.linesep is the line separator in text files ('\r' or '\n' or '\r\n')
          - os.defpath is the default search path for executables
          - os.devnull is the file path of the null device ('/dev/null', etc.)
        
        Programs that import and use 'os' stand a better chance of being
        portable between different platforms.  Of course, they must then
        only use functions that are defined by all platforms (e.g., unlink
        and opendir), and leave all pathname manipulation to os.path
        (e.g., split and join).
    
    CLASSES
        builtins.Exception(builtins.BaseException)
            builtins.OSError
        builtins.tuple(builtins.object)
            nt.times_result
            nt.uname_result
            stat_result
            statvfs_result
            terminal_size
        
        error = class OSError(Exception)
         |  Base class for I/O related errors.
         |  
         |  Method resolution order:
         |      OSError
         |      Exception
         |      BaseException
         |      object
         |  
         |  Methods defined here:
         |  
         |  __init__(self, /, *args, **kwargs)
         |      Initialize self.  See help(type(self)) for accurate signature.
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __str__(self, /)
         |      Return str(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  characters_written
         |  
         |  errno
         |      POSIX exception code
         |  
         |  filename
         |      exception filename
         |  
         |  filename2
         |      second exception filename
         |  
         |  strerror
         |      exception strerror
         |  
         |  winerror
         |      Win32 exception code
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from BaseException:
         |  
         |  __delattr__(self, name, /)
         |      Implement delattr(self, name).
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  __setattr__(self, name, value, /)
         |      Implement setattr(self, name, value).
         |  
         |  __setstate__(...)
         |  
         |  with_traceback(...)
         |      Exception.with_traceback(tb) --
         |      set self.__traceback__ to tb and return self.
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors inherited from BaseException:
         |  
         |  __cause__
         |      exception cause
         |  
         |  __context__
         |      exception context
         |  
         |  __dict__
         |  
         |  __suppress_context__
         |  
         |  __traceback__
         |  
         |  args
        
        class stat_result(builtins.tuple)
         |  stat_result: Result from stat, fstat, or lstat.
         |  
         |  This object may be accessed either as a tuple of
         |    (mode, ino, dev, nlink, uid, gid, size, atime, mtime, ctime)
         |  or via the attributes st_mode, st_ino, st_dev, st_nlink, st_uid, and so on.
         |  
         |  Posix/windows: If your platform supports st_blksize, st_blocks, st_rdev,
         |  or st_flags, they are available as attributes only.
         |  
         |  See os.stat for more information.
         |  
         |  Method resolution order:
         |      stat_result
         |      builtins.tuple
         |      builtins.object
         |  
         |  Methods defined here:
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  st_atime
         |      time of last access
         |  
         |  st_atime_ns
         |      time of last access in nanoseconds
         |  
         |  st_ctime
         |      time of last change
         |  
         |  st_ctime_ns
         |      time of last change in nanoseconds
         |  
         |  st_dev
         |      device
         |  
         |  st_file_attributes
         |      Windows file attribute bits
         |  
         |  st_gid
         |      group ID of owner
         |  
         |  st_ino
         |      inode
         |  
         |  st_mode
         |      protection bits
         |  
         |  st_mtime
         |      time of last modification
         |  
         |  st_mtime_ns
         |      time of last modification in nanoseconds
         |  
         |  st_nlink
         |      number of hard links
         |  
         |  st_size
         |      total size, in bytes
         |  
         |  st_uid
         |      user ID of owner
         |  
         |  ----------------------------------------------------------------------
         |  Data and other attributes defined here:
         |  
         |  n_fields = 17
         |  
         |  n_sequence_fields = 10
         |  
         |  n_unnamed_fields = 3
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from builtins.tuple:
         |  
         |  __add__(self, value, /)
         |      Return self+value.
         |  
         |  __contains__(self, key, /)
         |      Return key in self.
         |  
         |  __eq__(self, value, /)
         |      Return self==value.
         |  
         |  __ge__(self, value, /)
         |      Return self>=value.
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __getitem__(self, key, /)
         |      Return self[key].
         |  
         |  __getnewargs__(...)
         |  
         |  __gt__(self, value, /)
         |      Return self>value.
         |  
         |  __hash__(self, /)
         |      Return hash(self).
         |  
         |  __iter__(self, /)
         |      Implement iter(self).
         |  
         |  __le__(self, value, /)
         |      Return self<=value.
         |  
         |  __len__(self, /)
         |      Return len(self).
         |  
         |  __lt__(self, value, /)
         |      Return self<value.
         |  
         |  __mul__(self, value, /)
         |      Return self*value.n
         |  
         |  __ne__(self, value, /)
         |      Return self!=value.
         |  
         |  __rmul__(self, value, /)
         |      Return self*value.
         |  
         |  count(...)
         |      T.count(value) -> integer -- return number of occurrences of value
         |  
         |  index(...)
         |      T.index(value, [start, [stop]]) -> integer -- return first index of value.
         |      Raises ValueError if the value is not present.
        
        class statvfs_result(builtins.tuple)
         |  statvfs_result: Result from statvfs or fstatvfs.
         |  
         |  This object may be accessed either as a tuple of
         |    (bsize, frsize, blocks, bfree, bavail, files, ffree, favail, flag, namemax),
         |  or via the attributes f_bsize, f_frsize, f_blocks, f_bfree, and so on.
         |  
         |  See os.statvfs for more information.
         |  
         |  Method resolution order:
         |      statvfs_result
         |      builtins.tuple
         |      builtins.object
         |  
         |  Methods defined here:
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  f_bavail
         |  
         |  f_bfree
         |  
         |  f_blocks
         |  
         |  f_bsize
         |  
         |  f_favail
         |  
         |  f_ffree
         |  
         |  f_files
         |  
         |  f_flag
         |  
         |  f_frsize
         |  
         |  f_namemax
         |  
         |  ----------------------------------------------------------------------
         |  Data and other attributes defined here:
         |  
         |  n_fields = 10
         |  
         |  n_sequence_fields = 10
         |  
         |  n_unnamed_fields = 0
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from builtins.tuple:
         |  
         |  __add__(self, value, /)
         |      Return self+value.
         |  
         |  __contains__(self, key, /)
         |      Return key in self.
         |  
         |  __eq__(self, value, /)
         |      Return self==value.
         |  
         |  __ge__(self, value, /)
         |      Return self>=value.
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __getitem__(self, key, /)
         |      Return self[key].
         |  
         |  __getnewargs__(...)
         |  
         |  __gt__(self, value, /)
         |      Return self>value.
         |  
         |  __hash__(self, /)
         |      Return hash(self).
         |  
         |  __iter__(self, /)
         |      Implement iter(self).
         |  
         |  __le__(self, value, /)
         |      Return self<=value.
         |  
         |  __len__(self, /)
         |      Return len(self).
         |  
         |  __lt__(self, value, /)
         |      Return self<value.
         |  
         |  __mul__(self, value, /)
         |      Return self*value.n
         |  
         |  __ne__(self, value, /)
         |      Return self!=value.
         |  
         |  __rmul__(self, value, /)
         |      Return self*value.
         |  
         |  count(...)
         |      T.count(value) -> integer -- return number of occurrences of value
         |  
         |  index(...)
         |      T.index(value, [start, [stop]]) -> integer -- return first index of value.
         |      Raises ValueError if the value is not present.
        
        class terminal_size(builtins.tuple)
         |  A tuple of (columns, lines) for holding terminal window size
         |  
         |  Method resolution order:
         |      terminal_size
         |      builtins.tuple
         |      builtins.object
         |  
         |  Methods defined here:
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  columns
         |      width of the terminal window in characters
         |  
         |  lines
         |      height of the terminal window in characters
         |  
         |  ----------------------------------------------------------------------
         |  Data and other attributes defined here:
         |  
         |  n_fields = 2
         |  
         |  n_sequence_fields = 2
         |  
         |  n_unnamed_fields = 0
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from builtins.tuple:
         |  
         |  __add__(self, value, /)
         |      Return self+value.
         |  
         |  __contains__(self, key, /)
         |      Return key in self.
         |  
         |  __eq__(self, value, /)
         |      Return self==value.
         |  
         |  __ge__(self, value, /)
         |      Return self>=value.
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __getitem__(self, key, /)
         |      Return self[key].
         |  
         |  __getnewargs__(...)
         |  
         |  __gt__(self, value, /)
         |      Return self>value.
         |  
         |  __hash__(self, /)
         |      Return hash(self).
         |  
         |  __iter__(self, /)
         |      Implement iter(self).
         |  
         |  __le__(self, value, /)
         |      Return self<=value.
         |  
         |  __len__(self, /)
         |      Return len(self).
         |  
         |  __lt__(self, value, /)
         |      Return self<value.
         |  
         |  __mul__(self, value, /)
         |      Return self*value.n
         |  
         |  __ne__(self, value, /)
         |      Return self!=value.
         |  
         |  __rmul__(self, value, /)
         |      Return self*value.
         |  
         |  count(...)
         |      T.count(value) -> integer -- return number of occurrences of value
         |  
         |  index(...)
         |      T.index(value, [start, [stop]]) -> integer -- return first index of value.
         |      Raises ValueError if the value is not present.
        
        class times_result(builtins.tuple)
         |  times_result: Result from os.times().
         |  
         |  This object may be accessed either as a tuple of
         |    (user, system, children_user, children_system, elapsed),
         |  or via the attributes user, system, children_user, children_system,
         |  and elapsed.
         |  
         |  See os.times for more information.
         |  
         |  Method resolution order:
         |      times_result
         |      builtins.tuple
         |      builtins.object
         |  
         |  Methods defined here:
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  children_system
         |      system time of children
         |  
         |  children_user
         |      user time of children
         |  
         |  elapsed
         |      elapsed time since an arbitrary point in the past
         |  
         |  system
         |      system time
         |  
         |  user
         |      user time
         |  
         |  ----------------------------------------------------------------------
         |  Data and other attributes defined here:
         |  
         |  n_fields = 5
         |  
         |  n_sequence_fields = 5
         |  
         |  n_unnamed_fields = 0
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from builtins.tuple:
         |  
         |  __add__(self, value, /)
         |      Return self+value.
         |  
         |  __contains__(self, key, /)
         |      Return key in self.
         |  
         |  __eq__(self, value, /)
         |      Return self==value.
         |  
         |  __ge__(self, value, /)
         |      Return self>=value.
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __getitem__(self, key, /)
         |      Return self[key].
         |  
         |  __getnewargs__(...)
         |  
         |  __gt__(self, value, /)
         |      Return self>value.
         |  
         |  __hash__(self, /)
         |      Return hash(self).
         |  
         |  __iter__(self, /)
         |      Implement iter(self).
         |  
         |  __le__(self, value, /)
         |      Return self<=value.
         |  
         |  __len__(self, /)
         |      Return len(self).
         |  
         |  __lt__(self, value, /)
         |      Return self<value.
         |  
         |  __mul__(self, value, /)
         |      Return self*value.n
         |  
         |  __ne__(self, value, /)
         |      Return self!=value.
         |  
         |  __rmul__(self, value, /)
         |      Return self*value.
         |  
         |  count(...)
         |      T.count(value) -> integer -- return number of occurrences of value
         |  
         |  index(...)
         |      T.index(value, [start, [stop]]) -> integer -- return first index of value.
         |      Raises ValueError if the value is not present.
        
        class uname_result(builtins.tuple)
         |  uname_result: Result from os.uname().
         |  
         |  This object may be accessed either as a tuple of
         |    (sysname, nodename, release, version, machine),
         |  or via the attributes sysname, nodename, release, version, and machine.
         |  
         |  See os.uname for more information.
         |  
         |  Method resolution order:
         |      uname_result
         |      builtins.tuple
         |      builtins.object
         |  
         |  Methods defined here:
         |  
         |  __new__(*args, **kwargs) from builtins.type
         |      Create and return a new object.  See help(type) for accurate signature.
         |  
         |  __reduce__(...)
         |      helper for pickle
         |  
         |  __repr__(self, /)
         |      Return repr(self).
         |  
         |  ----------------------------------------------------------------------
         |  Data descriptors defined here:
         |  
         |  machine
         |      hardware identifier
         |  
         |  nodename
         |      name of machine on network (implementation-defined)
         |  
         |  release
         |      operating system release
         |  
         |  sysname
         |      operating system name
         |  
         |  version
         |      operating system version
         |  
         |  ----------------------------------------------------------------------
         |  Data and other attributes defined here:
         |  
         |  n_fields = 5
         |  
         |  n_sequence_fields = 5
         |  
         |  n_unnamed_fields = 0
         |  
         |  ----------------------------------------------------------------------
         |  Methods inherited from builtins.tuple:
         |  
         |  __add__(self, value, /)
         |      Return self+value.
         |  
         |  __contains__(self, key, /)
         |      Return key in self.
         |  
         |  __eq__(self, value, /)
         |      Return self==value.
         |  
         |  __ge__(self, value, /)
         |      Return self>=value.
         |  
         |  __getattribute__(self, name, /)
         |      Return getattr(self, name).
         |  
         |  __getitem__(self, key, /)
         |      Return self[key].
         |  
         |  __getnewargs__(...)
         |  
         |  __gt__(self, value, /)
         |      Return self>value.
         |  
         |  __hash__(self, /)
         |      Return hash(self).
         |  
         |  __iter__(self, /)
         |      Implement iter(self).
         |  
         |  __le__(self, value, /)
         |      Return self<=value.
         |  
         |  __len__(self, /)
         |      Return len(self).
         |  
         |  __lt__(self, value, /)
         |      Return self<value.
         |  
         |  __mul__(self, value, /)
         |      Return self*value.n
         |  
         |  __ne__(self, value, /)
         |      Return self!=value.
         |  
         |  __rmul__(self, value, /)
         |      Return self*value.
         |  
         |  count(...)
         |      T.count(value) -> integer -- return number of occurrences of value
         |  
         |  index(...)
         |      T.index(value, [start, [stop]]) -> integer -- return first index of value.
         |      Raises ValueError if the value is not present.
    
    FUNCTIONS
        _exit(status)
            Exit to the system with specified status, without normal exit processing.
        
        abort()
            Abort the interpreter immediately.
            
            This function 'dumps core' or otherwise fails in the hardest way possible
            on the hosting operating system.  This function never returns.
        
        access(path, mode, *, dir_fd=None, effective_ids=False, follow_symlinks=True)
            Use the real uid/gid to test for access to a path.
            
              path
                Path to be tested; can be string or bytes
              mode
                Operating-system mode bitfield.  Can be F_OK to test existence,
                or the inclusive-OR of R_OK, W_OK, and X_OK.
              dir_fd
                If not None, it should be a file descriptor open to a directory,
                and path should be relative; path will then be relative to that
                directory.
              effective_ids
                If True, access will use the effective uid/gid instead of
                the real uid/gid.
              follow_symlinks
                If False, and the last element of the path is a symbolic link,
                access will examine the symbolic link itself instead of the file
                the link points to.
            
            dir_fd, effective_ids, and follow_symlinks may not be implemented
              on your platform.  If they are unavailable, using them will raise a
              NotImplementedError.
            
            Note that most operations will use the effective uid/gid, therefore this
              routine can be used in a suid/sgid environment to test if the invoking user
              has the specified access to the path.
        
        chdir(path)
            Change the current working directory to the specified path.
            
            path may always be specified as a string.
            On some platforms, path may also be specified as an open file descriptor.
              If this functionality is unavailable, using it raises an exception.
        
        chmod(path, mode, *, dir_fd=None, follow_symlinks=True)
            Change the access permissions of a file.
            
              path
                Path to be modified.  May always be specified as a str or bytes.
                On some platforms, path may also be specified as an open file descriptor.
                If this functionality is unavailable, using it raises an exception.
              mode
                Operating-system mode bitfield.
              dir_fd
                If not None, it should be a file descriptor open to a directory,
                and path should be relative; path will then be relative to that
                directory.
              follow_symlinks
                If False, and the last element of the path is a symbolic link,
                chmod will modify the symbolic link itself instead of the file
                the link points to.
            
            It is an error to use dir_fd or follow_symlinks when specifying path as
              an open file descriptor.
            dir_fd and follow_symlinks may not be implemented on your platform.
              If they are unavailable, using them will raise a NotImplementedError.
        
        close(fd)
            Close a file descriptor.
        
        closerange(fd_low, fd_high, /)
            Closes all file descriptors in [fd_low, fd_high), ignoring errors.
        
        cpu_count()
            Return the number of CPUs in the system; return None if indeterminable.
        
        device_encoding(fd)
            Return a string describing the encoding of a terminal's file descriptor.
            
            The file descriptor must be attached to a terminal.
            If the device is not a terminal, return None.
        
        dup(fd, /)
            Return a duplicate of a file descriptor.
        
        dup2(fd, fd2, inheritable=True)
            Duplicate file descriptor.
        
        execl(file, *args)
            execl(file, *args)
            
            Execute the executable file with argument list args, replacing the
            current process.
        
        execle(file, *args)
            execle(file, *args, env)
            
            Execute the executable file with argument list args and
            environment env, replacing the current process.
        
        execlp(file, *args)
            execlp(file, *args)
            
            Execute the executable file (which is searched for along $PATH)
            with argument list args, replacing the current process.
        
        execlpe(file, *args)
            execlpe(file, *args, env)
            
            Execute the executable file (which is searched for along $PATH)
            with argument list args and environment env, replacing the current
            process.
        
        execv(path, argv, /)
            Execute an executable path with arguments, replacing current process.
            
            path
              Path of executable file.
            argv
              Tuple or list of strings.
        
        execve(path, argv, env)
            Execute an executable path with arguments, replacing current process.
            
            path
              Path of executable file.
            argv
              Tuple or list of strings.
            env
              Dictionary of strings mapping to strings.
        
        execvp(file, args)
            execvp(file, args)
            
            Execute the executable file (which is searched for along $PATH)
            with argument list args, replacing the current process.
            args may be a list or tuple of strings.
        
        execvpe(file, args, env)
            execvpe(file, args, env)
            
            Execute the executable file (which is searched for along $PATH)
            with argument list args and environment env , replacing the
            current process.
            args may be a list or tuple of strings.
        
        fdopen(fd, *args, **kwargs)
            # Supply os.fdopen()
        
        fsdecode(filename)
            Decode filename from the filesystem encoding with 'surrogateescape' error
            handler, return str unchanged. On Windows, use 'strict' error handler if
            the file system encoding is 'mbcs' (which is the default encoding).
        
        fsencode(filename)
            Encode filename to the filesystem encoding with 'surrogateescape' error
            handler, return bytes unchanged. On Windows, use 'strict' error handler if
            the file system encoding is 'mbcs' (which is the default encoding).
        
        fstat(fd)
            Perform a stat system call on the given file descriptor.
            
            Like stat(), but for an open file descriptor.
            Equivalent to os.stat(fd).
        
        fsync(fd)
            Force write of fd to disk.
        
        ftruncate(fd, length, /)
            Truncate a file, specified by file descriptor, to a specific length.
        
        get_exec_path(env=None)
            Returns the sequence of directories that will be searched for the
            named executable (similar to a shell) when launching a process.
            
            *env* must be an environment variable dict or None.  If *env* is None,
            os.environ will be used.
        
        get_handle_inheritable(handle, /)
            Get the close-on-exe flag of the specified file descriptor.
        
        get_inheritable(fd, /)
            Get the close-on-exe flag of the specified file descriptor.
        
        get_terminal_size(...)
            Return the size of the terminal window as (columns, lines).
            
            The optional argument fd (default standard output) specifies
            which file descriptor should be queried.
            
            If the file descriptor is not connected to a terminal, an OSError
            is thrown.
            
            This function will only be defined if an implementation is
            available for this system.
            
            shutil.get_terminal_size is the high-level function which should 
            normally be used, os.get_terminal_size is the low-level implementation.
        
        getcwd()
            Return a unicode string representing the current working directory.
        
        getcwdb()
            Return a bytes string representing the current working directory.
        
        getenv(key, default=None)
            Get an environment variable, return None if it doesn't exist.
            The optional second argument can specify an alternate default.
            key, default and the result are str.
        
        getlogin()
            Return the actual login name.
        
        getpid()
            Return the current process id.
        
        getppid()
            Return the parent's process id.
            
            If the parent process has already exited, Windows machines will still
            return its id; others systems will return the id of the 'init' process (1).
        
        isatty(fd, /)
            Return True if the fd is connected to a terminal.
            
            Return True if the file descriptor is an open file descriptor
            connected to the slave end of a terminal.
        
        kill(pid, signal, /)
            Kill a process with a signal.
        
        link(src, dst, *, src_dir_fd=None, dst_dir_fd=None, follow_symlinks=True)
            Create a hard link to a file.
            
            If either src_dir_fd or dst_dir_fd is not None, it should be a file
              descriptor open to a directory, and the respective path string (src or dst)
              should be relative; the path will then be relative to that directory.
            If follow_symlinks is False, and the last element of src is a symbolic
              link, link will create a link to the symbolic link itself instead of the
              file the link points to.
            src_dir_fd, dst_dir_fd, and follow_symlinks may not be implemented on your
              platform.  If they are unavailable, using them will raise a
              NotImplementedError.
        
        listdir(path=None)
            Return a list containing the names of the files in the directory.
            
            path can be specified as either str or bytes.  If path is bytes,
              the filenames returned will also be bytes; in all other circumstances
              the filenames returned will be str.
            If path is None, uses the path='.'.
            On some platforms, path may also be specified as an open file descriptor;\
              the file descriptor must refer to a directory.
              If this functionality is unavailable, using it raises NotImplementedError.
            
            The list is in arbitrary order.  It does not include the special
            entries '.' and '..' even if they are present in the directory.
        
        lseek(fd, position, how, /)
            Set the position of a file descriptor.  Return the new position.
            
            Return the new cursor position in number of bytes
            relative to the beginning of the file.
        
        lstat(path, *, dir_fd=None)
            Perform a stat system call on the given path, without following symbolic links.
            
            Like stat(), but do not follow symbolic links.
            Equivalent to stat(path, follow_symlinks=False).
        
        makedirs(name, mode=511, exist_ok=False)
            makedirs(name [, mode=0o777][, exist_ok=False])
            
            Super-mkdir; create a leaf directory and all intermediate ones.  Works like
            mkdir, except that any intermediate path segment (not just the rightmost)
            will be created if it does not exist. If the target directory already
            exists, raise an OSError if exist_ok is False. Otherwise no exception is
            raised.  This is recursive.
        
        mkdir(path, mode=511, *, dir_fd=None)
            Create a directory.
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
            
            The mode argument is ignored on Windows.
        
        open(path, flags, mode=511, *, dir_fd=None)
            Open a file for low level IO.  Returns a file descriptor (integer).
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        pipe()
            Create a pipe.
            
            Returns a tuple of two file descriptors:
              (read_fd, write_fd)
        
        popen(cmd, mode='r', buffering=-1)
            # Supply os.popen()
        
        putenv(name, value, /)
            Change or add an environment variable.
        
        read(fd, length, /)
            Read from a file descriptor.  Returns a bytes object.
        
        readlink(...)
            readlink(path, *, dir_fd=None) -> path
            
            Return a string representing the path to which the symbolic link points.
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        remove(path, *, dir_fd=None)
            Remove a file (same as unlink()).
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        removedirs(name)
            removedirs(name)
            
            Super-rmdir; remove a leaf directory and all empty intermediate
            ones.  Works like rmdir except that, if the leaf directory is
            successfully removed, directories corresponding to rightmost path
            segments will be pruned away until either the whole path is
            consumed or an error occurs.  Errors during this latter phase are
            ignored -- they generally mean that a directory was not empty.
        
        rename(src, dst, *, src_dir_fd=None, dst_dir_fd=None)
            Rename a file or directory.
            
            If either src_dir_fd or dst_dir_fd is not None, it should be a file
              descriptor open to a directory, and the respective path string (src or dst)
              should be relative; the path will then be relative to that directory.
            src_dir_fd and dst_dir_fd, may not be implemented on your platform.
              If they are unavailable, using them will raise a NotImplementedError.
        
        renames(old, new)
            renames(old, new)
            
            Super-rename; create directories as necessary and delete any left
            empty.  Works like rename, except creation of any intermediate
            directories needed to make the new pathname good is attempted
            first.  After the rename, directories corresponding to rightmost
            path segments of the old name will be pruned until either the
            whole path is consumed or a nonempty directory is found.
            
            Note: this function can fail with the new directory structure made
            if you lack permissions needed to unlink the leaf directory or
            file.
        
        replace(src, dst, *, src_dir_fd=None, dst_dir_fd=None)
            Rename a file or directory, overwriting the destination.
            
            If either src_dir_fd or dst_dir_fd is not None, it should be a file
              descriptor open to a directory, and the respective path string (src or dst)
              should be relative; the path will then be relative to that directory.
            src_dir_fd and dst_dir_fd, may not be implemented on your platform.
              If they are unavailable, using them will raise a NotImplementedError."
        
        rmdir(path, *, dir_fd=None)
            Remove a directory.
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        scandir(...)
            scandir(path='.') -> iterator of DirEntry objects for given path
        
        set_handle_inheritable(handle, inheritable, /)
            Set the inheritable flag of the specified handle.
        
        set_inheritable(fd, inheritable, /)
            Set the inheritable flag of the specified file descriptor.
        
        spawnl(mode, file, *args)
            spawnl(mode, file, *args) -> integer
            
            Execute file with arguments from args in a subprocess.
            If mode == P_NOWAIT return the pid of the process.
            If mode == P_WAIT return the process's exit code if it exits normally;
            otherwise return -SIG, where SIG is the signal that killed it.
        
        spawnle(mode, file, *args)
            spawnle(mode, file, *args, env) -> integer
            
            Execute file with arguments from args in a subprocess with the
            supplied environment.
            If mode == P_NOWAIT return the pid of the process.
            If mode == P_WAIT return the process's exit code if it exits normally;
            otherwise return -SIG, where SIG is the signal that killed it.
        
        spawnv(mode, path, argv, /)
            Execute the program specified by path in a new process.
            
            mode
              Mode of process creation.
            path
              Path of executable file.
            argv
              Tuple or list of strings.
        
        spawnve(mode, path, argv, env, /)
            Execute the program specified by path in a new process.
            
            mode
              Mode of process creation.
            path
              Path of executable file.
            argv
              Tuple or list of strings.
            env
              Dictionary of strings mapping to strings.
        
        startfile(...)
            startfile(filepath [, operation])
            
            Start a file with its associated application.
            
            When "operation" is not specified or "open", this acts like
            double-clicking the file in Explorer, or giving the file name as an
            argument to the DOS "start" command: the file is opened with whatever
            application (if any) its extension is associated.
            When another "operation" is given, it specifies what should be done with
            the file.  A typical operation is "print".
            
            startfile returns as soon as the associated application is launched.
            There is no option to wait for the application to close, and no way
            to retrieve the application's exit status.
            
            The filepath is relative to the current directory.  If you want to use
            an absolute path, make sure the first character is not a slash ("/");
            the underlying Win32 ShellExecute function doesn't work if it is.
        
        stat(path, *, dir_fd=None, follow_symlinks=True)
            Perform a stat system call on the given path.
            
              path
                Path to be examined; can be string, bytes, or open-file-descriptor int.
              dir_fd
                If not None, it should be a file descriptor open to a directory,
                and path should be a relative string; path will then be relative to
                that directory.
              follow_symlinks
                If False, and the last element of the path is a symbolic link,
                stat will examine the symbolic link itself instead of the file
                the link points to.
            
            dir_fd and follow_symlinks may not be implemented
              on your platform.  If they are unavailable, using them will raise a
              NotImplementedError.
            
            It's an error to use dir_fd or follow_symlinks when specifying path as
              an open file descriptor.
        
        stat_float_times(...)
            stat_float_times([newval]) -> oldval
            
            Determine whether os.[lf]stat represents time stamps as float objects.
            
            If value is True, future calls to stat() return floats; if it is False,
            future calls return ints.
            If value is omitted, return the current setting.
        
        strerror(code, /)
            Translate an error code to a message string.
        
        symlink(src, dst, target_is_directory=False, *, dir_fd=None)
            Create a symbolic link pointing to src named dst.
            
            target_is_directory is required on Windows if the target is to be
              interpreted as a directory.  (On Windows, symlink requires
              Windows 6.0 or greater, and raises a NotImplementedError otherwise.)
              target_is_directory is ignored on non-Windows platforms.
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        system(command)
            Execute the command in a subshell.
        
        times()
            Return a collection containing process timing information.
            
            The object returned behaves like a named tuple with these fields:
              (utime, stime, cutime, cstime, elapsed_time)
            All fields are floating point numbers.
        
        truncate(path, length)
            Truncate a file, specified by path, to a specific length.
            
            On some platforms, path may also be specified as an open file descriptor.
              If this functionality is unavailable, using it raises an exception.
        
        umask(mask, /)
            Set the current numeric umask and return the previous umask.
        
        unlink(path, *, dir_fd=None)
            Remove a file (same as remove()).
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            dir_fd may not be implemented on your platform.
              If it is unavailable, using it will raise a NotImplementedError.
        
        urandom(size, /)
            Return a bytes object containing random bytes suitable for cryptographic use.
        
        utime(path, times=None, *, ns=None, dir_fd=None, follow_symlinks=True)
            Set the access and modified time of path.
            
            path may always be specified as a string.
            On some platforms, path may also be specified as an open file descriptor.
              If this functionality is unavailable, using it raises an exception.
            
            If times is not None, it must be a tuple (atime, mtime);
                atime and mtime should be expressed as float seconds since the epoch.
            If ns is specified, it must be a tuple (atime_ns, mtime_ns);
                atime_ns and mtime_ns should be expressed as integer nanoseconds
                since the epoch.
            If times is None and ns is unspecified, utime uses the current time.
            Specifying tuples for both times and ns is an error.
            
            If dir_fd is not None, it should be a file descriptor open to a directory,
              and path should be relative; path will then be relative to that directory.
            If follow_symlinks is False, and the last element of the path is a symbolic
              link, utime will modify the symbolic link itself instead of the file the
              link points to.
            It is an error to use dir_fd or follow_symlinks when specifying path
              as an open file descriptor.
            dir_fd and follow_symlinks may not be available on your platform.
              If they are unavailable, using them will raise a NotImplementedError.
        
        waitpid(pid, options, /)
            Wait for completion of a given process.
            
            Returns a tuple of information regarding the process:
                (pid, status << 8)
            
            The options argument is ignored on Windows.
        
        walk(top, topdown=True, onerror=None, followlinks=False)
            Directory tree generator.
            
            For each directory in the directory tree rooted at top (including top
            itself, but excluding '.' and '..'), yields a 3-tuple
            
                dirpath, dirnames, filenames
            
            dirpath is a string, the path to the directory.  dirnames is a list of
            the names of the subdirectories in dirpath (excluding '.' and '..').
            filenames is a list of the names of the non-directory files in dirpath.
            Note that the names in the lists are just names, with no path components.
            To get a full path (which begins with top) to a file or directory in
            dirpath, do os.path.join(dirpath, name).
            
            If optional arg 'topdown' is true or not specified, the triple for a
            directory is generated before the triples for any of its subdirectories
            (directories are generated top down).  If topdown is false, the triple
            for a directory is generated after the triples for all of its
            subdirectories (directories are generated bottom up).
            
            When topdown is true, the caller can modify the dirnames list in-place
            (e.g., via del or slice assignment), and walk will only recurse into the
            subdirectories whose names remain in dirnames; this can be used to prune the
            search, or to impose a specific order of visiting.  Modifying dirnames when
            topdown is false is ineffective, since the directories in dirnames have
            already been generated by the time dirnames itself is generated. No matter
            the value of topdown, the list of subdirectories is retrieved before the
            tuples for the directory and its subdirectories are generated.
            
            By default errors from the os.scandir() call are ignored.  If
            optional arg 'onerror' is specified, it should be a function; it
            will be called with one argument, an OSError instance.  It can
            report the error to continue with the walk, or raise the exception
            to abort the walk.  Note that the filename is available as the
            filename attribute of the exception object.
            
            By default, os.walk does not follow symbolic links to subdirectories on
            systems that support them.  In order to get this functionality, set the
            optional argument 'followlinks' to true.
            
            Caution:  if you pass a relative pathname for top, don't change the
            current working directory between resumptions of walk.  walk never
            changes the current directory, and assumes that the client doesn't
            either.
            
            Example:
            
            import os
            from os.path import join, getsize
            for root, dirs, files in os.walk('python/Lib/email'):
                print(root, "consumes", end="")
                print(sum([getsize(join(root, name)) for name in files]), end="")
                print("bytes in", len(files), "non-directory files")
                if 'CVS' in dirs:
                    dirs.remove('CVS')  # don't visit CVS directories
        
        write(fd, data, /)
            Write a bytes object to a file descriptor.
    
    DATA
        F_OK = 0
        O_APPEND = 8
        O_BINARY = 32768
        O_CREAT = 256
        O_EXCL = 1024
        O_NOINHERIT = 128
        O_RANDOM = 16
        O_RDONLY = 0
        O_RDWR = 2
        O_SEQUENTIAL = 32
        O_SHORT_LIVED = 4096
        O_TEMPORARY = 64
        O_TEXT = 16384
        O_TRUNC = 512
        O_WRONLY = 1
        P_DETACH = 4
        P_NOWAIT = 1
        P_NOWAITO = 3
        P_OVERLAY = 2
        P_WAIT = 0
        R_OK = 4
        SEEK_CUR = 1
        SEEK_END = 2
        SEEK_SET = 0
        TMP_MAX = 2147483647
        W_OK = 2
        X_OK = 1
        __all__ = ['altsep', 'curdir', 'pardir', 'sep', 'pathsep', 'linesep', ...
        altsep = '/'
        curdir = '.'
        defpath = r'.;C:\bin'
        devnull = 'nul'
        environ = environ({'JPY_PARENT_PID': '1688', 'TERM': 'xter....WSH;.MSC...
        extsep = '.'
        linesep = '\r\n'
        name = 'nt'
        pardir = '..'
        pathsep = ';'
        sep = r'\'
        supports_bytes_environ = False
    
    FILE
        c:\anaconda3\envs\py3\lib\os.py


​    
​    

## 文件通配符

`glob`模块提供了一个函数用于从目录通配符搜索中生成文件列表。


```python
import glob
glob.glob('*.py')

#比如输出为['prime.py','random.py']形式。
```




    []



## 命令行参数

通用工具脚本经常调用命令行参数。这些命令行参数以链表的形式存储于`sys`模块的`argv`变量（argument vector参数矢量）。

## 错误输出重定向和程序终止

`sys`还有`stdin`,`stdout`和`stderr`属性，即使在`stdout`被重定向时，后者也可以用于显示警告和错误信息。

大多数脚本的定向终止都使用`sys.exit()`。

## 字符串正则匹配

`re`模块为高级字符串处理提供了正则表达式工具。对于复杂的匹配和处理，正则表达式提供了简洁、优化的解决方案。

如果只需要简单的功能，首先考虑字符串的方法。


```python
import re
'tea for too'.replace('too','two')
```




    'tea for two'



## 数学

`math`模块为浮点运算提供了底层C函数库的访问。


```python
import math
math.log(1024,2)
```




    10.0



`random`模块提供了生成随机数的工具


```python
import random
random.sample(range(100),10) #sample without replacement
```




    [45, 66, 56, 3, 97, 87, 35, 1, 38, 92]



## 访问互联网

有几个模块用于访问互联网以及处理网络通信协议。其中最简单的两个是用于处理从 urls 接收的数据的` urllib.request` 以及用于发送电子邮件的 `smtplib`。

## 日期和时间

`datetime`模块为日期和时间处理的同时提供了简单和复杂的方法。

支持日期和时间算法的同时，实现的重点放在更有效的处理和格式化的输出。

该模块还支持时区的处理。


```python
from datetime import date
now = date.today()
print(now)
```

    2019-05-29


## 数据压缩

接支持通用的数据打包和压缩格式：zlib，gzip，bz2，zipfile，以及 tarfile。


```python
import zlib

s = b'witch which has which witches wrist watch'

print(len(s))

t=zlib.compress(s)

print(len(t))

zlib.crc32(s)
```

    41
    37





    226805979



## 测试模块

开发高质量软件的方法之一是为每一个函数开发测试代码，并且在开发过程中经常进行测试

`doctest`模块提供了一个工具，扫描模块并根据程序中内嵌的文档字符串执行测试。

测试构造如同简单的将它的输出结果剪切并粘贴到文档字符串中。

通过用户提供的例子，它强化了文档，允许 doctest 模块确认代码的结果是否与文档一致。


```python

```
