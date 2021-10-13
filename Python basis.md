# 注释


```python
print("#注释单行")
```

    #注释单行



```python
print("'''注释多行")
```

    '''注释多行


###   '''  '''注释多行 


```python
print(1)
print(2)
print(3)
```

    1
    2
    3



```python
print(1)
'''print(1)
print(2)
print(3)'''
print(2)
print(3)
```

    1
    2
    3

# 输入输出

### print()输出



```python
print(123)print(111)print("111",end='')print(222)
```

    123111111222


####  print(end='')表示不换行

### % 替换


```python
print("年薪 %d" %10000)
```

    年薪 10000


## 输入input


```python
a = input("a=")
```

    a=10


## 字符串转换


```python
a  = input("a=")
print(float(a))
```

    a=10
    10.0



```python

```



# 元组----不能修改的列表()


```python
num = (1,2,3,)
num
```




    (1, 2, 3)




```python
num[1] = 7
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-4-391921ed9643> in <module>
    ----> 1 num[1] = 7


    TypeError: 'tuple' object does not support item assignment



```python
num[0] 
```




    1



## 将列表转换为元组----tuple()


```python
list_num = list(range(1,100,10))
print(list_num)
tuple_num = tuple(list_num)
tuple_num
```

    [1, 11, 21, 31, 41, 51, 61, 71, 81, 91]





    (1, 11, 21, 31, 41, 51, 61, 71, 81, 91)



# 字典{ }和列表一样可变


```python
boy = {'name':'wuhan','age':18}
```

字典是健值对，任何对象都可以作为字典中的值

### 通过名称和健访问字典元素


```python
boy['name']
```




    'wuhan'



### 添加键值对


```python
boy['wife'] = 'zhaoxin'
boy
```




    {'name': 'wuhan', 'age': 18, 'wife': 'zhaoxin'}



### 修改健值对


```python
boy['age'] = 20
boy
```




    {'name': 'wuhan', 'age': 20, 'wife': 'zhaoxin'}



### del  删除健值对


```python
del boy['wife']
boy
```




    {'name': 'wuhan', 'age': 20}



## 遍历字典中的键值对----items()方法


```python
boy.items()
```




    dict_items([('name', 'wuhan'), ('age', 20)])




```python
for key,value in boy.items():
    print("key:"+key)
    print("value:"+value)
```

    key:name
    value:wuhan
    key:age



    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-21-90587b8024bd> in <module>
          1 for key,value in boy.items():
          2     print("key:"+key)
    ----> 3     print("value:"+value)


    TypeError: can only concatenate str (not "int") to str


## 遍历字典中的键 ------ keys()


```python
for i in boy.keys():
    print(i)
```

    name
    age


## 遍历字典中的值----values()


```python
for i in boy.values():
    print(i)
```

    wuhan
    20


字典中可以有列表和字典，列表中也可以有元组和字典

### 列表中存储字典


```python
wuhan ={'age':'20','sex' : 'female'}
zhaoxin = {"age":'20','sex':'male'}

family = [wuhan,zhaoxin]
family
```




    [{'age': '20', 'sex': 'female'}, {'age': '20', 'sex': 'male'}]



### 字典中存储列表


```python
family = {'wife':['zhaoxin','huangxuejiao','jingjing'],'husbend':['wuhan']}
family
```




    {'wife': ['zhaoxin', 'huangxuejiao', 'jingjing'], 'husbend': ['wuhan']}



### 字典中存储字典


```python
university ={
    'frist' : {'王牌':"清华北大"},
    'secend' : {"985211":"上交浙大复旦国科"},
    'lowest' : {"停水停电大学":"湖工大"}
}
university
```




    {'frist': {'王牌': '清华北大'},
     'secend': {'985211': '上交浙大复旦国科'},
     'lowest': {'停水停电大学': '湖工大'}}

# 字符串处理

### " + "拼接字符串


```python
# coding = utf-8
a = "day"
b = "night"
x = " "
c = a + x +b 
c
```




    'day night'



### 获取长度len()


```python
a = input("a=")
length = len(a)
print("a的长度为：{:d}".format(length))
```

    a=hunansheng
    a的长度为：10


### 大小写转换 upper() lower()   title()首字母变大写


```python
a = input("a=")
b = a.upper()
b
```

    a=wuhan





    'WUHAN'




```python
A = input("A")
a = A.lower()
a
```

    AHUT





    'hut'




```python
a = input("a=")b = a.title()print(a)print(b)
```

    a=pythonpythonPython


## strip()去除首尾空格


```python
first = input("first=")later = first.strip()firstlater
```

    first=    you   are a   bitch





    'you   are a   bitch'



### strip(增加指定首尾字符进行删除)


```python
m = input("m=")n = m.strip("*")n
```

    m=我 ** 你个 大**





    '我 ** 你个 大'



## 字符串查找find()


```python
source_string =input("source_string:")destination_string = source_string.find('woman')destination_string
```

    source_string:you are a fucking foolish man





    -1



##    替换replace()


```python
the_word = input("first:")later = the_word.replace('man','woman')later
```

    first:you are a man





    'you are a woman'



## split()分割


```python
a_string = "you and me and she"
b_string = a_string.split("and")
b_string
```




    ['you ', ' me ', ' she']

# 列表---多类型数组

### 添加元素append()    insert()

### append()  ------队尾添加


```python
list_1 = [1,2,3]
list_1.append('wuhan')
list_1
```




    [1, 2, 3, 'wuhan']



### insert()-----指定位置添加


```python
list_1 = [1,2,3]
list_1.insert(1,'wuhan')
list_1
```




    [1, 'wuhan', 2, 3]



## 修改----根据索引进行修改


```python
list_1 = [1,2,3]
list_1[0] = 'hut'
list_1
```




    ['hut', 2, 3]



## 删除del()   pop()   remove()

## del()----根据索引直接删除


```python
list_1 = [1,2,3]
del list_1[0]
list_1
```




    [2, 3]



### pop()----根据索引删除返回


```python
list_1 = [1,2,3]list_1.pop(0)list_1
```




    [2, 3]



## remove()----根据值删除


```python
list_1 = [1,2,3]list_1.remove(3)list_1
```




    [1, 2]



### sort()排序 ------True为逆序


```python
list_2 = ['wuhan','zhaoxin','wife','husbund']list_2.sort()list_2
```




    ['husbund', 'wife', 'wuhan', 'zhaoxin']




```python
list_2 = ['wuhan','zhaoxin','wife','husbund']list_2.sort(reverse=True)list_2
```




    ['zhaoxin', 'wuhan', 'wife', 'husbund']



## 数值列表--range(),list()

### 生成递增数字----range(下限，上限，步长)


```python
for i in range(1,10,2):    print(i)
```

    13579


range() + append()创建列表


```python
list_n = []for i in range(1,10):    i = i**2    list_n.append(i)list_n
```




    [1, 4, 9, 16, 25, 36, 49, 64, 81]



list()转换为列表


```python
data_list = list(range(1,10))data_list
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9]



简单运算---sum(),max(),min()


```python
num = [11,2,4,9,17,10]print(sum(num))print(max(num))print(min(num))
```

    53
    17
    2


## 列表切片

指定列表的索引范围，以及步长即可  （start:end:step）


```python
list_1= list(range(1,100,10))
print(list_1[5:10:2])    
print(list_1[:-1])
```

    [51, 71, 91]
    [1, 11, 21, 31, 41, 51, 61, 71, 81]

# 函数

```python

```

```python
def fuctionname(parements):
    '''函数说明'''
    
```

## 必选参数，默认参数，可变参数，关键字参数

### 必选参数


```python
def suma(a,b):
    return a+b
suma(10,100)
```




    110



### 默认参数   -----若不给该参数值，则使用默认值


```python
def nonchange(a,b=100):
    return a+b
print(nonchange(100))
nonchange(100,200)
```

    200





    300



### 可变参数-----传入的参数数量可变，使用 “*”进行标识，接收到的是一个元组


```python
def change(*num):
    sum = 0
    for i in num:
        sum +=i
    return sum
print(change(1,3,9,12))
change(1,100,11,12,13,14,15)
```

    25





    166



### 关键字参数---允许传入任意个含参数名的参数，使用“**”标识,保存在字典中


```python
def vital(**num):    return numprint(vital())print(vital(x=1,y=2))
```

    {}{'x': 1, 'y': 2}



```python
def fire(x,y=100,*z,**w):    print(x)    print(y)    print(z)    print(w)fire(111,222,333,444)
```

    111222(333, 444){}


## 返回值----return

###  多个返回值是一个元组


```python
def non():    return 1,'wuhan','zhaoxin'non()
```




    (1, 'wuhan', 'zhaoxin')



### 返回函数


```python
def uction(*args):    def suma():        s = 0        for i in agrs:            s = s+i        return s    return sumauction(1,2,3,1)
```




    <function __main__.uction.<locals>.suma()>



### 闭包：当母函数返回子函数时，相关参数也会保存


```python
'''最大公约数---辗转相除法'''a = int(input("a="))        b =int(input("b="))def gcd(a,b):    if(b>a):        m = 0        m = a        a = b        b = m    c = 0    while(b>0):        c = a % b         a = b         b = c         return agcd(a,b)
```

    a=10b=30





    10



## 函数使用范围---Python作用域

### __***__是特殊变量，允许直接使用------public

### _****和__***即非公开的

### _***从外部访问会有异常-----protected

### __***从外部访问不会有异常---privated


```python
'''最大公约数'''
a = int(input("a="))
b = int(input('b='))
def lcm(a,b):
    return int((a*b)/_gcd(a,b))
def _gcd(a,b):
    if(a>b):
        m = 0
        m = a
        a = b
        b = m
    
    c=0
    while(b>0):
        c = a%b
        a =b
        b = c
        
    return a
lcm(a,b)
```

    a=5
    b=6
    
    30

```python
#循环结构
i = 0
while(i<5):
    print("舞七永远想着赵！")
    i = i+1
```

    舞七永远想着赵！
    舞七永远想着赵！
    舞七永远想着赵！
    舞七永远想着赵！
    舞七永远想着赵！

# 循环结构

```python
for i in range(1,10):
    if(i==5):
        continue
    print(i)
```

    1
    2
    3
    4
    6
    7
    8
    9



```python
a = int(input("a="))
b = int(input("b="))
while(a>2):
    while(b>2):
        print("双喜临门！")
        break
    break
```

    a=3
    b=3
    双喜临门！

迭代器

迭代器在访问元素时会丢失索引值，但是可以随机访问集合以及其他类型的数据结构。

迭代器仅仅在访问到某个数据结构的时候才能使用

## iter()------转换为迭代器

可直接作用于for循环的数据类型如list、tuple、dict等统称为可迭代对象:Iterable

## next()-----遍历迭代器

## isinstance()-----判断是否是可迭代对象


```python
from collections import Iterable
isinstance((),Iterable)
```

    <ipython-input-4-db24b0e597f6>:1: DeprecationWarning: Using or importing the ABCs from 'collections' instead of from 'collections.abc' is deprecated since Python 3.3, and in 3.9 it will stop working
      from collections import Iterable





    True



可以被next()函数调用并不断返回下一个值的对象称为迭代器:Iterator

next()函数访问每一个对象，直到对象访问完毕，返回一个StopIteration异常

所有的Iterable都可以通过iter()函数转化为Iterator

## 定义迭代器------Iterator

定义一个迭代器时，需要定义一个类，该类中含有一个iter()函数,这个函数能够返回带next()方法的Itertor对象


```python
class MyIterable:
    def __iter__(self):
        return MyIterator
    
class MyIterator:
    def __init__(self):
        self.num = 0
    def __next__(self):
        self.num += 1
        if self.num >= 10:
            raise StopIteration
        return self.num
```

## 迭代器的复制-----deepcopy()


```python

```

# 顺序与选择结构

### 交换顺序


```python
a = int(input("a="))
b = int(input("b="))
c = 0

c = a
a = b
b = c
print("a=",a)
print("b=",b)
```

选择结构--if else


```python
a = int(input("a="))
if(a<60):
    print("你怕是在吃屎！")
elif(a<70):
    print("起飞！")
elif(a<100):
    print("浪费！")
else:
    print("回家种田吧！")
```

    a=90
    浪费！


## 三元操作符


```python
x = int(input("x="))
y = int(input("y="))
c = x if x>y else y
print(c)
```

    x=10
    y=12
    12



# 模块

.py文件即为模块

导入模块  import 模块名.函数名


```python
from math import sqrt
x = 100
sqrt(x)
```




    10.0



后面导入的模块会覆盖前面导入的模块

自定义模块


```python
# mymode.py
def func(a,b):
    return a + b
import mymode.py
```


    ---------------------------------------------------------------------------
    
    ModuleNotFoundError                       Traceback (most recent call last)
    
    <ipython-input-11-e6c96a428efe> in <module>
          2 def func(a,b):
          3     return a + b
    ----> 4 import mymode.py


    ModuleNotFoundError: No module named 'mymode'


#### os模块：文件和目录，用于提供系统级别的操作；

#### sys模块：用于提供对解释器相关的操作；

#### json模块：处理JSON字符串；

#### logging: 用于便捷记录日志且线程安全的模块；

#### time&datetime模块：时间相关的操作，时间有三种表示方式；

#### hashlib模块：用于加密相关操作，代替了md5模块，主要是提供SHA1、SHA224、SHA256、SHA384、SHA512和MD5算法；

#### random模块：提供随机数。

### dir()获取模块内函数方法使用过的名字


```python
import math 
print(dir(math))
```

    ['__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees', 'dist', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'perm', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc']


### globals()  locals()都可被用来返回全局和局部命名空间里的名

### reload()再次执行模块顶层的代码，即重载模块

# 综合运用

## 递归函数-----汉诺塔的魅力

汉诺塔问题源于印度一个古老传说。相传大梵天创造世界的时候做了三根金刚石柱子，在一根柱子上从下往上按照大小顺序摞着64片黄金圆盘。大梵天命令婆罗门把圆盘从下面开始按大小顺序重新摆放在另一根柱子上并规定，任何时候，在小圆盘上都不能放大圆盘，且在三根柱子之间一次只能移动一个圆盘

我们每次都是以a或b中一根柱子为辅助，然后先将除了最下面的圆盘之外的其他圆盘移动到辅助柱子上，再将最底下的圆盘移到c柱子上，不断重复此过程。

这个反复移动圆盘的过程就是递归。例如我们每次想解决n个圆盘的移动问题，就要先解决（n-1)个盘子进行同样操作的问题。我们先假设a柱上只有3个圆盘，利用 Python 进行编程实现圆盘的移动，


```python
def move(n,a,b,c):
    if(n==1):         #终止递归的条件
        print(a + "->" + c)
        return 0
    move(n-1,a,c,b)   #假定已经有n-1个盘移动到了b
    move(1,a,b,c)     #把第n个盘移动到c
    move(n-1,b,a,c)   #把b上的n-1个盘移动道c

move(3,"a","b","c")
```

    a->c
    a->b
    c->b
    a->c
    b->a
    b->c
    a->c


## 求正整数的阶乘


```python
n = int(input("n="))

def fact(n):
    if(n==1):
        return 1
    else:
        return fact(n-1) * n
    

fact(n)    
```

    n=5





    120

## lambda函数----匿名函数

lambda函数不需要函数名，也没有返回值，因为表达式本身的结果就是返回值


```python
add = lambda x,y:x+y
add(2,3)
```




    5



### 对列表进行排序


```python
list_1 = [11,-3,9,14,33]

def f(n):
    return abs(n)

list_s = sorted(list_1,key=f)
print(list_s)
```

    [-3, 9, 11, 14, 33]



```python
list_1 = [11,-3,9,14,33]list_s = sorted(list_1,key=lambda x:abs(x))print(list_s)
```

    [-3, 9, 11, 14, 33]


### 比较两个数


```python
def maxs(a,b):    if(a>b):        return a    else:        return bdef mins(a,b):    if(a<b):        return a    else:        return bx = int(input("x="))y = int(input("y="))print("较大值：%d" %maxs(x,y))print("较小值：%d" %mins(x,y))
```

    x=10y=20较大值：20较小值：10

## Map-reduce-----映射与归并

map()映射，接受一个函数，另一个序列


```python
t = map(lambda x:x**2,[1,3,5,6])list(t)
```




    [1, 9, 25, 36]




```python
s = map(lambda x,y:x+y,[1,2,3,4,],[9,9,9,9])list(s)
```




    [10, 11, 12, 13]



reduce()函数把第一次计算的结果继续和序列中的下一个元素做累积计算


```python
from functools import reducei = reduce(lambda x,y:x+y,[1,2,3,4],9)i
```




    19



(((((1+9)+2)+3)+4)

### 分解质因数


```python
x = int(input("x="))
n = x
result = []
i = 2
while(i<=n):
    if(n%i==0):       #找到因数，进行累加
        print(i)
        result.append(i)
        n = n/i
    else:
        i = i+1
    if(n==1):
        break
        
print(x,'=','*'.join(map(str,result)))
```

    x=80
    2
    2
    2
    2
    5
    80 = 2*2*2*2*5



```python

```

## 最大公约数

枚举法


```python
def findit_1(x,y):
    m = max(x,y) + 1
    result = 0
    for i in range(2,m):
        if(x%i==0 and y%i==0):
            result = i  #从小到大找
        return result
    
x = int(input("x="))
y = int(input("y="))
findit(x,y)
```

    x=98
    y=78





    2



更相减损法


```python
def findit_2(x,y):
    while True:
        if x<y :
            x, y = y, x
        elif x == y :
            return x
        x = x-y
x = int(input("x="))
y = int(input("y="))
print(findit_2(x,y))
```

    x=98
    y=78
    2


更相减损法-递归


```python
def findit_2_pro(x,y):
    return x if y==0 else  findit_2_pro(y,x%y)

x = int(input("x="))
y = int(input("y="))
print(findit_2_pro(x,y))
```

    x=98
    y=78
    2


## 最小公倍数

几个数共有的倍数

a,b的最大公约数 * a,b的最小公倍数 = a*b


```python
def gcd(x, y):
            return x if y == 0 else gcd(y, x%y)
def lcm(x, y):
    return x // gcd(x, y) * y
x = int(input("x="))
y = int(input("y="))
print(lcm(x,y))
```

    x=78y=983822


## 输出指定范围内的素数

是否为素数


```python
def findsingle(x):    if(x==1):        return False    else:        for i in range(2,x):            if x%i == 0:                return False    return Truex = int(input("x="))print(findsingle(x))
```

    x=11True


也可以枚举2到根号x之间的正整数


```python
from math import sqrtdef meiju(x):    s = int(sqrt(x))    for i in range(2,s-1):        return ix = int(input("x="))print(meiju(x))
```

    x=11None


### 埃拉托斯特尼筛法----不大于正整数的素数

先用一个数组vis，把不大于该正整数x的所有正整数标记为0，表示没有访问。
然后从第一个素数2开始遍历整个区间，如果当前访问的数没有访问过，则可以认为它是一个素数，那么就将它在该区间内所有的倍数全部标记为已访问，这样就保证外部的循环发现的没有访问过的数都是素数。

所使用的原理是从2开始，将每个素数的各个倍数，标记成合数。一个素数的各个倍数，是一个差为此素数本身的等差数列。此为这个筛法和试除法不同的关键之处，后者是以素数来测试每个待测数能否被整除。

先用2去筛，即把2留下，把2的倍数剔除掉；再用下一个素数，也就是3筛，把3留下，把3的倍数剔除掉；接下去用下一个素数5筛，把5留下，把5的倍数剔除掉；不断重复下去……。


```python
 def sieve(x):        vis = [0 for i in range(x+1)]  #先标记        prime_table = []        for i in range(2, x+1):            if vis[i] == 0:                #剩下的数即为素数                prime_table.append(i)                  for j in range(i*2, x+1, i):#剔除素数的倍数，即合数                    vis[j] = 1        return prime_tablex = int(input("x="))sieve(x)
```

    x=10





    [2, 3, 5, 7]



### 欧拉筛法


```python
def ouler(x):        vis = [0 for i in range(x+1)]        prime_table = []        ln = 0        for num in range(2, x+1):            if vis[num] == 0:                prime_table.append(num)                ln += 1            for j in range(ln):                if num * prime_table[j] > x:     #避免越界                    break                vis[num * prime_table[j]] = 1    #满足条件就筛选掉                if num % prime_table[j] == 0:    #避免重复筛选                    break        return prime_tablex = int(input("x="))ouler(x)
```

    x=11





    [2, 3, 5, 7, 11]



## 文件处理


Python对文件的操作大致可分为下列三步：

通过open函数打开指定文件，并且获得文件的句柄。
通过上一步的文件句柄，对文件进行读(read)、写(write)操作。
通过文件句柄的close函数关闭文件句柄。

 open（文件路径，读写方式）
 读写方式:
     a:打开文件用于追加
     b:二进制
     w:写
     w+:读写

read()-----一次性全读出来

readline()-------一次读一行

readlines()------一次读若干行形成一个list


```python
'''f = open("***.txt")print(f.read())f.close()'''
```




    '\nf = open("***.txt")\nprint(f.read())\nf.close()\n'




```python
'''f.write()'''
```




    '\nf.write()\n'



用写模式打开文件，会清空文件原有的数据！

#### sorted()----排序


```python
ls = ['Alice', 'Bob', 'qwer']def func(key):    return len(key)print(sorted(ls, key=func))
```

    ['Bob', 'qwer', 'Alice']



```python
ls = ['Alice', 'Bob', 'qwer']def func(key):    return len(key)print(sorted(ls, key=lambda x:len(x)))
```

    ['Bob', 'qwer', 'Alice']



```python
lis = []with open(filename,"r") as f:    lis.extend(list(map(lambda x: int(s),f.readlines)))with open(filenames,"w") as f:    for line in lis:        f.write(str(line)+"\n")
```

## 判断素数


```python
import mathx = int(input("x="))def issinle(x):    if(x==1):        return False    for i in range(2,int(math.sqrt(x))+1):        if(x%i==0):            return False    return Trueissinle(x)
```

    x=19





    True



#### 格式化输出

%---占位符


```python
print("your age : %2.2d" %20.20)
```

    your age : 20



```python
print("pi  : %3.2d" %(3.1415926))
```

    pi  :  03


{}   +   format

可指明顺序和名称，以及关键字参数,还可以指明对齐方式等


```python
print("{0} {2} {1} {0}".format("one","two","no"))
```

    one no two one



```python
print("{hut}".format(hut="湖南停水停电大学"))
```

    湖南停水停电大学



```python
d = {"a":123,"b":999}print("{a}{b}".format(**d))
```

    123999



```python
print("{:>010}".format(3.1415926))
```

    03.1415926



```python
print("{:^010}".format(3.1415926))
```

    3.14159260



```python
print("{:4.3f}".format(3.1415926))
```

    3.142


f-string格式化输出，需要用f引出


```python
a = 999b = {"a":123,"b":666}print(f"{a}{b}")
```

    999{'a': 123, 'b': 666}



```python
a = 999b = {"a":123,"b":666}print(f"{a:^010}")
```

    0009990000



```python
a = 999b = {"a":123,"b":666}print(f"{a:.3f}")
```

    999.000


99乘法表


```python
x = int(input("x="))for h in range(1,x+1):    for l in range(h,10):        print(f"{h}*{l}={h*l:<3}",end="")        if(l==9):            print("",end='')    print("")    
```

    x=21*1=1  1*2=2  1*3=3  1*4=4  1*5=5  1*6=6  1*7=7  1*8=8  1*9=9  2*2=4  2*3=6  2*4=8  2*5=10 2*6=12 2*7=14 2*8=16 2*9=18 


input以字符串形式返回

eval()-----直接求出表达式的值


```python
eval("5*5+99")
```




    124



## 类的基础语法

### 类的声明与定义

Python 是一门面向对象的语言。面向对象编程 - Object Oriented Programming（简称 OOP）是一种编程思想，在面向对象编程中，把对象作为程序的基本单元，把程序视为一系列对象的集合。一个对象包括了数据和操作数据的方法，消息传递成为联系对象的方法。


对象可按其性质划分为类，对象也就是类的实例。类是用来描述具有相同的属性和方法的对象的集合，即抽象的集合。例如书这个类，它代表着所有书，它具有书所共有的属性：书名、版本、作者和出版日期，它也具有所有书都共有的方法：销售。

在 Python 中，类的声明是通过class关键字表示的：

class ClassName(bases_classes):
    '类文档字符串'
    class_suite     # 类体
class后面接着是类名ClassName，类名的开头通常是大写。类名后面的(bases_classes)表示这个类是由哪个类继承来的，如果没有合适的继承类，就使用object类，object类是所有类都会继承的基类。类文档字符串是对类所进行的说明，可以通过ClassName.__doc__查看


```python
class Classname(bases_classes):    '''类文档字符串，用于说明类'''    class_suite      #类体:类体由类成员、方法、数据属性组成
```


```python
class man(object):    '''人类'''    manlist=["male","female"]    for i in manlist:        print(i)
```

    malefemale


Python中类的声明和定义是一起的


```python
class Book(object):    '书籍类'    def _init_(self,name,author,data,version):        self.name = name        self.author = author        self.data = data        self.version = version    def sell(bookName,price):        print("%s的销售价格为%d" %(bookName,price))
```

### 类的属性与实例化

属性就是对类和对象特征的描述，外部以属性来区分不同的类，类具有数据属性和方法。而由类创建出来的实例-对象，具有它所属的类的数据属性和方法

#### 数据属性

类的数据属性只与类绑定，不属于任何实例。在类创建后，属性也被创建，类的数据属性也可以称为静态变量，它通常用来跟踪与类相关的值。类的数据属性使用的并不多，一般都是用实例数据属性


```python
class human(object):    age = 20
```

#### 特殊属性

类中还有很多特殊属性，具体如下:

ClassName.__name__：类ClassName的名字；

ClassName.__doc__：类ClassName的文档字符串；

ClassName.__bases__：类ClassName的所有父类构成的元组；

ClassName.__dict__：类ClassName的属性；

ClassName.__module__：类ClassName定义所在的模块；

Instance.__class__：实例Instance所对应的类。

#### 类的方法

类中的方法也称为函数。Python中用关键字def定义一个方法，后面接方法名，最后接参数


```python
class human(object):    def eat(self):        print("eat food")
```

类中的方法一定要通过实例的句点方法去调用


```python
class human(object):    def eat(self):        print("eat food")me = human()me.eat()
```

    eat food


#### 类的实例化


类的实例化通过函数操作符来创建


```python
class human(object):    def eat(self):        print("eat food")me = human()
```

#### 类的初始化

在实例化一个对象后，Python 会检查是否实现了__init__()方法。如果没有实现__init__()方法，则不会做其它的操作，直接返回对象，实例化过程完毕。而__init__()方法是用来给类本身初始化的，支持带参数的初始化

__init__()是解释器在创建一个实例后调用的第一个方法。


```python
class Book:    def __init__(self,bookname,price,author):        self.bookname = bookname        self.price = price        self.author = author    def sell(self):        print("%s书本的价格为%d" %(self.bookname,int(self.price)))book = Book("python","45","aas")book.sell()
```

    python书本的价格为45


当实例化一个自定义类时，将参数通过构造函数 __init__ ，赋值给成员变量，且成员变量是通过将 self. 作为前缀引出。Python 中类的方法的第一个参数始终是 self ，在外部实例调用其方法时，不需要考虑 self 这一位置上的参数，因为默认就是实例本身。

 __repr__ 是 Python 中一个十分常用的函数，当实例作为 print 函数的参数时，就会输出实例的 __repr__ 的返回值


```python
class Student():    def __init__(self, name, age):        self.name = name        self.age = age    def __repr__(self):        return f'Name: {self.name}\nAge: {self.age}'stu = Student('Zhang', 15)print(stu)
```

    Name: ZhangAge: 15


### 绑定与方法调用

 如果用实例去调用方法，这种限制就被称为 Python 中的绑定（binging）   没有创建实例时，方法就是未绑定的

#### 调用绑定方法

self---代表实例本身

在定义方法时，self总是作为第一个参数传递的。self代表实例本身，self.变量代表调用此实例的变量，self.方法代表调用实例的方法。因为声明方法时已经传入self，所以在调用时self就不用明确传入了，此时实例是隐含的。


```python
class bindExample:    def bindMethod(self):        print("绑定方法调用实例")be = bindExample()be.bindMethod()
```

    绑定方法调用实例


#### 调用非绑定方法

即不创建实例，用类去调用


```python
class bindExample:    def bindMethod(self):        print("非绑定方法调用实例")be = bindExample()bindExample.bindMethod(be)
```

    非绑定方法调用实例


### 类方法与静态方法

静态方法由类直接调用，静态方法在类中定义，无需参数

在声明静态方法的时候，使用函数修饰符@staticmethod


```python
class human(object):    @staticmethod    def sth():        print("🤏")human.sth()
```

    🤏


类方法由实例调用，传入的参数为类本身，通常用cls作为参数名字

在声明类方法的时候，使用函数修饰符@classmethod


```python
class university(object):    @classmethod    def hut(cls):        print("湖南停水停电大学！")HUT = university()HUT.hut()
```

    湖南停水停电大学！


### 类的导入

#### 导入整个模块


```python
import moudlename
```

调用模块中的类


```python
b = moudlename.classname()
```

#### 导入单个或多个类,此时可直接用类调用

在这种方法中，若导入的类名相同，则后面导入的类将会覆盖前面导入的类。


```python
from ModuleName import ClassName1,ClassName2,...
```


```python
object = ClassName()object.属性object.方法
```

#### 导入模块中所有的类

科直接用类调用


```python
from ModuleName import *
```


```python
object = ClassName()object.属性object.方法
```


```python

```

## 类的继承

### 初识继承

通过继承，子类可以继承其父类所有的属性和方法，这在很大程度上增强了代码的重用

父类
父类也称基类，其声明方法与一般的类的声明方法一样。父类中存在着一些公共的属性和方法，子类继承于父类。




子类
子类继承于父类，拥有父类中的属性和方法，它自己也可根据实际情况声明一些属于自己的属性和方法。


```python
class subClass(parentClass1,parentClass2,parentClass3,……):    class_suite
```

括号后面的就是继承的父类


```python
class ParentClass:    static_var = 100    def parentMethod(self):        print("这是父类")class SubClass(ParentClass):    def subMethod(self):        print("这是子类")sc = SubClass()print(sc.static_var)sc.parentMethod()sc.subMethod()print("%s所属的父类为%s" %(sc.__class__,SubClass.__bases__))
```

    100这是父类这是子类<class '__main__.SubClass'>所属的父类为(<class '__main__.ParentClass'>,)


对于任何子类来说，__bases__类是一个包含其父类的集合的元组，对于没有父类的类来说，其__bases__属性值为空

### 覆盖方法

即子类重写父类的方法


```python
class Parent:    def sayHello(self):        print("hello,i am class parent")class Subclass(Parent):    def sayHello(self):        print("hello,i am class subclass")sc = Subclass()sc.sayHello()
```

    hello,i am class subclass


在重写了父类中的方法后，也可以调用父类中的被重写方法。这时就是去调用一个未绑定的父类方法


```python
Parent.sayHello(sc)
```

    hello,i am class parent


也可以显示调用


```python
class Parent:    def sayHello(self):        print("hello,i am class parent")class Subclass(Parent):    def sayHello(self):        Parent.sayHello(self)        print("hello,i am class subclass")sc = Subclass()sc.sayHello()
```

    hello,i am class parenthello,i am class subclass



```python
class Parent:    def sayHello(self):        print("hello,i am class parent")class Subclass(Parent):    def sayHello(self):        Parent.sayHello(self)        print("hello,i am class subclass")sc = Subclass()sc.sayHello()
```

    hello,i am class parenthello,i am class subclass


但是最好的方法是在子类的重写方法里使用super()内建方法


```python
class Parent:    def sayHello(self):        print("hello,i am class parent")class Subclass(Parent):    def sayHello(self):        super(Subclass,self).sayHello()        print("hello,i am class subclass")sc = Subclass()sc.sayHello()
```

    hello,i am class parenthello,i am class subclass


### 从标准类派生

#### 标准数据类型

Number（数字）、String（字符串）、List（列表）、Tuple（元组）、Sets（集合）和Dict（字典）。而根据内存中的内容是否可变，分为可变类型与不可变类型。其中，数字、字符串、元组和集合被称为不可变类型，列表和字典称为可变类型。

#### 不可变类型子类化

我们可以使用super()内建函数去捕获对应的父类，然后调用父类的__new__()方法进行实例化

假定我们需要处理大量的浮点数，将浮点数四舍五入后得到最后的结果。这时我们可以定义这样一个类，用来进行这个操作。例如：

在这个类里面，通过调用父类的构造器来创建对象，然后实例化float、RoundFloat。


```python
class RoundFloat(float):    def __new__(cls, val):        return float.__new__(cls,round(val,1))print(RoundFloat(2.6557))
```

    2.7


#### 可变类型子类化

子类化一个可变类型与子类化不可变类型很类似，但是我们可能不需要使用__new__()或者是__init__()，因为一般情况下我们定义的类所继承到的类型的默认行为就足够我们用了


```python
class SortedKeyDict(dict):    def keys(self):        return sorted(super( SortedKeyDict, self).keys())d = SortedKeyDict((('zhangsan', 1), ('lisi', 2),('wangwu', 3)))print("By iterator:".ljust(12), [key for key in d])print("By keys():".ljust(12), d.keys())
```

    By iterator: ['zhangsan', 'lisi', 'wangwu']By keys():   ['lisi', 'wangwu', 'zhangsan']


### 多重继承

多重继承就是允许子类继承多个父类，子类可以调用多个父类的方法和属性。

但是，当多个父类拥有相同方法名的方法时，我们通过方法名调用父类方法就有一定的顺序。


```python
class A(object):    def test(self):        print("this is A.test()")class B(object):    def test(self):        print("this is B.test()")    def check(self):        print("this is B.check()")class C(A,B):    passclass D(A,B):    def check(self):        print("this is D.check()")class E(C,D):    pass
```

但是由于在多重继承中遵循广度优先的方式

如果调用E.check()方法，那么先到类E中查找，然后在类C中查找，再到类D中查

## 类的其他特性

### 类的内建函数

#### issubclass()

这个函数用来判断一个类是否是另外一个类的子类或者子孙类。


```python
issubclass(subclass, parentclass)
```

#### isinstance()

这个函数用来判断一个对象是否是给定类的实例


```python
isinstance(object,class)
```

#### hasattr()

它用于判断一个对象是否有一个特定的属性，一般用于在调用某个属性前检查属性是否存在


```python
class testClass(object):  foo = 100  def __init__(self,name):      self.name = nametest = testClass('theName')print(hasattr(test,'name'))print(hasattr(testClass,'foo'))
```

    TrueTrue


#### getattr()

getattr()是用来获取对象的属性或者方法。若返回的是对象，则返回对象的值，若返回的是对象的方法，则返回方法的内存地址

#### setattr()

setattr()是用来给对象的属性赋值。若属性不存在，就先创建属性然后再赋值


```python
class testClass(object):  foo = 100  def __init__(self,name):      self.name = nametest = testClass('theName')setattr(test,'fool','200')setattr(test,'foo','50')print(getattr(test,'fool'))print(getattr(test,'foo'))
```

    20050


#### delattr()删除属性

#### dir()

作用在实例上时，显示实例变量、实例所在的类、基类中定义的方法和属性；

作用在类上时，显示类与它的基类的__dict__内容；

作用在模块上时，显示此模块的__dict__内容；

dir()不带参数时，显示调用者的局部变量


```python
class testClass(object):    foo = 100    def __init__(self,name):        self.name = nametest = testClass('theName')print(dir(test))
```

    ['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'foo', 'name']


#### super()

super()函数的作用就是找出相应的类的父类，然后调用父类的方法与属性


```python
class parentClass:    def __init__(self):        self.name = "parent"    def tell(self):        print("this is parentClass")class subClass(parentClass):    def tell(self):        print("this is subClass")        parentClass.tell(self)sc = subClass()sc.tell()
```

    this is subClassthis is parentClass



```python
class parentClass:    def __init__(self):        self.name = "parent"    def tell(self):        print("this is parentClass")class subClass(parentClass):    def tell(self):        print("this is subClass")        super(subClass,self).tell()sc = subClass()sc.tell()
```

    this is subClassthis is parentClass


#### vars()

vars()是用来返回对象的属性及其值的一个字典。如果没有给出对象，则返回当前调用位置的属性和属性值。

### 类的私有化

在默认的情况下，Python 中的属性都是公开的（public），这就意味着此类所在的模块和导入了这个类的模块都可以访问到这个类中的属性和方法。但有时我们不希望外界直接访问某方法或属性，此时我们可以将这个方法和属性私有化

#### 双下划线

在 Python 中，可以在属性或方法前添加双下划线将其变为私有。在这种方法下，要调用私有属性就在名字前加上单下划线和类名。利用这种调用方法，就可以很好地避免当子类变量名与父类变量名相同时覆盖父类的变量

单下划线+类名调用


```python
class privatization(object):    def __init__(self,var):        self._var = var        self.__var = var        self.__var__ = var        self.varation = varpr = privatization(2)print(pr._var)print(pr.__var__)print(pr.varation)print(pr._privatization__var)
```

    2222


#### 单下划线

在一个模块中以单下划线开头的变量和函数被默认当做内部函数。当我们使用from module import *来导入模块时，这些不会被导入。但如果使用import module来导入整个模块，这部分还是会被导入，那么就可以用module.var来访问


```python

```

在 Python 中，以双下划线开头和双下划线结尾的是一些特殊的方法。比如\_\_init_\_()’、\_\_del__()’等。Python 官方建议不要以这样的方式来定义自己的变量或函数

### 包装与授权

包装在 Python 中经常用到，包装就是把已存在的程序重新打包，使这个程序更加适合当前应用环境。



包装就是对已存在对象的属性功能进行调整，删除不需要的、添加或是修改已存在的功能，以达到自己所理想的规格，并装换成另外一种更适合当前使用场合的对外接口。

包装包括定义一个类，它的实例拥有标准类型的核心行为。

例如，我们需要处理一个数据，处理这个数据需要一系列的步骤，我们可以将这些步骤写到一个类里面。每当应用于不同的场景时，就将各种适合于此场景的方法包装成类，且原对象的属性和方法依然可以调用。


```python
class Wrap(object):    def __init__(self,obj):     # 声明了构造函数，模拟要包装对象的构造方法        self.__obj = obj     # __obj就是这个被包装对象的核心    def get(self):     # 获取__obj对象        return self.__obj    def __repr__(self):        return 'self.__obj'    def __str__(self):     # 转换__obj对象        return str(self.__obj)    def __getattr__(self,thelist):        return getattr(self.__obj,thelist)
```

而授权是包装特有的一个属性，通过授权，可以使当前类调用传入对象已存在的属性

授权是包装的一个特性，采用已存在的功能达到最大限度的代码重用。在包装中我们可以新建、修改或删除已有的功能，授权的过程就是将更新的功能交由新类来处理，已存在的功能就授权给对象的默认属性。

要实现授权，一定要覆盖\_\_getattr\_\_()方法。在代码里包含一个对getattr()内建函数的调用，调用getattr()得到默认对象的属性（数据属性或者方法）并返回它，以便于访问或者调用

### 对象的销毁

对象销毁也称垃圾回收，很多语言都有自己的垃圾回收机制。Python 的垃圾回收机制使用了引用计数这一机制来追踪内存中的对象

#### 增加引用计数

在 Python 中，当一个对象被创建时，就自动地创建了一个引用计数器。当引用计数加1时，增加对这个对象的引用，引用计数器也依次增加

对象被创建时；

创建了另一个别名时；

被作为参数传递给函数时；

成为容器对象的一个元素时。


```python
x = 12y = xz = y
```

在这个例子中，语句x = 12创建了对象12并将这个对象赋值给了x。此时12的引用计数为1，语句y = x创建了一个指向对象12的别名y，计数为2，在语句z = y中又创建了一个别名，所以此时对象12的引用计数为3。

#### 减少引用计数


当别名被重新赋值时，源对象的引用计数减1


```python
var1 = "we"var2 = var1var1 = 12
```

在这个例子中，对象"we"赋值给了var1，引用为1，语句var2 = var1将对象的值又赋给了var2，引用为2。但在语句var1 = 12中，将对象12赋值给了var1，此时对象"we"的引用减1，12的引用加1。

对象的引用计数在下列情况下减少：

一个本地引用离开了其作用范围时，

比如函数结束；

对象别名被销毁时；

对象本身被销毁时。

#### 对象销毁

当对象的引用计数变为0时，它被垃圾回收。Python 中的垃圾回收机制可以处理两种情况，一种是引用为0，另一种是循环引用。循环引用是指两个对象互相引用，且都没有外部的对象对它们进行引用。


```python
class delObject:    def __init__(self):        self.var = 100    def __del__(self):        class_name = self.__class__.__name__        print("对象%s销毁" %class_name)do1 = delObject()do2 = do1do3 = do1print(id(do1))print(id(do2))print(id(do3))del(do1)del(do2)del(do3)
```

    140411259295008140411259295008140411259295008对象delObject销毁


在这个例子中，__del__()为一个析构函数。当删除对象时，会调用本身的函数，在对象删除完毕时也会再次调用这个函数。


## 面向对象编程实训

### 定义三维向量类

在 Python 中，不论类的名字是什么，构造方法的名字总是固定为__init__()。另外，在 Python 类中，构造方法、析构方法以及所有属于实例的方法，都必须以 self 作为第一个参数，用来表示对象本身


```python
class vt:    def __init__(self,__x,__y,__z):        self.__x = __x        self.__y = __y        self.__z = __z
```

### 计算三维向量的长度

类中的方法可以分为实例方法、类方法、静态方法和特殊方法几大类。普通实例方法和特殊方法都必须使用 self 作为第一个参数，表示对象本身。对象的私有数据成员，在实例方法和特殊方法中，可以使用 self 作为前缀直接访问。对于一个 N 维向量而言，向量的长度被定义为，各分量平方和的平方根


```python
class vt:    def __init__(self,__x,__y,__z):        self.__x = __x        self.__y = __y        self.__z = __z            def length(self):        return sqrt(self.__x**2+self.__y**2+self.__z**2)
```

### 三维向量之间的加减法

在 Python 面向对象编程中，类的特殊方法在形式上是前后各有 2 个下划线，作用是实现与某个运算符或内置函数的对应关系。

例如，如果某个类实现了__len__()这个特殊方法，那么这个类的对象就支持内置函数len()；如果某个类实现了__add__()这个特殊方法，那么这个类的对象就支持加法运算符；如果某个类实现了__sub__()这个特殊方法，那么这个类的对象就支持减法运算符；如果某个类实现了__str__()这个特殊方法，那么这个类的对象就支持print()函数。


```python
class Vector3d:    def __init__(self, x, y, z):        self.__x = x        self.__y = y        self.__z = z    def length(self):        return (self.__x**2 + self.__y**2 + self.__z**2) ** 0.5    # 请在这里增加3个特殊方法，分别用来支持加法运算符、减法运算符以实现两个三维向量间的加法和减法运算，以及打印函数print()    	#********** Begin *********#    def __str__(self):        print(self.__x,self.__y,self.__z)    def __add__(self, v):        return self.__x+v.__x,self.__y+v.__y,self.__z+v.__z    def __sub__(self, v):        return self.__x-v.__x,self.__y-v.__y,self.__z-v.__z    	#********** End *********#
```

# 进阶篇

## 正则表达式

### 正则表达式基础知识

正则表达式是对字符串操作的一种逻辑公式，就是用事先定义好的一些特定字符、及这些特定字符的组合，组成一个“规则字符串”，来筛选出符合这个规则的内容。

可以简单理解为：一个强大的搜索工具中，正则表达式就是你要搜索内容的条件表达式。

#### re.findall()

作用：遍历整个字符串，可以获取其中所有匹配的字符串，返回一个列表。

一般用法：
re.findall(r'正则表达式'，'要匹配的文本')



匹配单词"to"


```python
import retext = "0537-146987425,0537-299656897,The moment you think about giving up,think of the reason why you held on so long. Total umbrella for someone else if he, you’re just not for him in the rain.Never put your happiness in someone else’s hands.Sometimes you have to give up on someone in order to respect yourself. aaaa bbbbcc d dddddd"print(re.findall(r'to',text))
```

    ['to', 'to']


匹配以"g"开头的所有单词


```python
print(re.findall(r'\bg\w*?\b',text))
```

    ['giving', 'give']


长度为4的单词


```python
print(re.findall(r'\b\w{4}\b',text))
```

    ['0537', '0537', 'held', 'long', 'else', 'just', 'rain', 'your', 'else', 'have', 'give', 'aaaa']


#### 正则表达式元字符

^	匹配字符串的开始

$	匹配字符串的结束

.	匹配除换行符以外的任意字符

\d	匹配数字

\b	匹配单词头或单词尾

\w	匹配任何字母、数字以及下划线

\s	匹配任何空白字符，包括空格、制表符、换页符

\B	与\b相反,匹配非单词边界

\W	与\w相反

\S	与\s相反

{m,n}	{}前的字符或子模式重复至少m次，至多n

### re模块中常用的功能函数

#### compile函数

编译正则表达式模式，返回一个对象的模式（可以把那些常用的正则表达式编译成正则表达式对象，这样可以提高一点效率）。

格式：re.compile(pattern,flags=0)


```python
import retext = "The moment you think about giving up,think of the reason why you held on so long."text1 = "Life is a journey,not the destination,but the scenery along the should be and the mood at the view."rr = re.compile(r'\w*o\w*')print(rr.findall(text))   #查找text中所有包含'o'的单词print(rr.findall(text1))   #查找text1中所有包含'o'的单词
```

    ['moment', 'you', 'about', 'of', 'reason', 'you', 'on', 'so', 'long']['journey', 'not', 'destination', 'along', 'should', 'mood']


#### match()函数

在字符串刚开始的位置匹配，在开头匹配到目的字符便返回，如果开头没有目的字符将匹配失败，返回None。

格式：re.match(pattern, string, flags=0)

match()函数返回的是一个match object对象，而match object对象有以下方法：

group()：返回被正则匹配的字符串；

start()：返回匹配开始的位置；

end()：返回匹配结束的位置；

span()：返回一个元组包含匹配 (开始，结束) 的位置；

groups()：返回正则整体匹配的字符串，可以一次输入多个组号，对应组号匹配的字符串。


```python
print(re.match('edu','educoder.net').group())print(re.match('edu','www.educoder.net').group())
```

    edu



    ---------------------------------------------------------------------------AttributeError                            Traceback (most recent call last)<ipython-input-10-ce1ea56a1fb9> in <module>      1 print(re.match('edu','educoder.net').group())----> 2 print(re.match('edu','www.educoder.net').group())


    AttributeError: 'NoneType' object has no attribute 'group'


#### search()函数

re.search()函数会在字符串内查找模式匹配，只要找到第一个匹配然后返回。如果字符串没有匹配，则返回None。

格式：re.search(pattern, string, flags=0)


```python
print(re.search('edu','www.educoderedu.net').group())print(re.search('eduaaa','www.educoderedu.net').group())
```

    edu



    ---------------------------------------------------------------------------AttributeError                            Traceback (most recent call last)<ipython-input-11-3d0f67c062a6> in <module>      1 print(re.search('edu','www.educoderedu.net').group())----> 2 print(re.search('eduaaa','www.educoderedu.net').group())


    AttributeError: 'NoneType' object has no attribute 'group'


match()和search()比较类似，它们的区别在于match()只匹配字符串的开头，如果开头没有出现目的字符串，即使后面出现了也不会进行匹配；search()函数会在整个字符内匹配，只要找到一个目的字符串就返回。


```python
import retext = input()#********** Begin *********##1.用compile方法，匹配所有含字母i的单词rr = re.compile(r'\w*i\w*')print(rr.findall(text))#2.在字符串起始位置匹配字符The是否存在，并返回被正则匹配的字符串print(re.match('The',text).group())#3.在整个字符串查看字符is是否存在，并返回被正则匹配的字符串print(re.search('is',text).group())#********** End **********#
```

    here is a time in life that is full of uneasiness.We have no other choice but to face it.`['is', 'time', 'in', 'life', 'is', 'uneasiness', 'choice', 'it']



    ---------------------------------------------------------------------------AttributeError                            Traceback (most recent call last)<ipython-input-13-0d84f3bf47c4> in <module>      7       8 #2.在字符串起始位置匹配字符The是否存在，并返回被正则匹配的字符串----> 9 print(re.match('The',text).group())     10      11 #3.在整个字符串查看字符is是否存在，并返回被正则匹配的字符串


    AttributeError: 'NoneType' object has no attribute 'group'


#### finditer()

搜索字符串，返回一个Match对象的迭代器（包含匹配的开始和结束的位置，如下图中的i所示）。找到正则匹配的所有子串，把它们作为一个迭代器返回。

格式：re.finditer(pattern, string, flags=0)


```python
itext = re.finditer(r'\d+','12 edueduedu44coder deducoder, 11skdh   ds 12')      #匹配所有的数字for i in itext:    print(i)    print(i.group())    print(i.span())   #span()返回一个元组包含匹配 (开始,结束) 的位置
```

    <re.Match object; span=(0, 2), match='12'>12(0, 2)<re.Match object; span=(12, 14), match='44'>44(12, 14)<re.Match object; span=(31, 33), match='11'>11(31, 33)<re.Match object; span=(43, 45), match='12'>12(43, 45)


#### split()

按照能够匹配的子串，将string分割后返回列表。

格式：re.split(pattern, string)；

可以使用re.split来分割字符串，如：re.split(r'\s+', text)将字符串，按空格分割成一个单词列表。

以数字为分割符，将字符串分割：


```python
print(re.split(r'\d+','asas2kdjs4jds5djdfj1djf0'))
```

    ['asas', 'kdjs', 'jds', 'djdfj', 'djf', '']


#### sub()

使用re替换string中每一个匹配的子串后，返回替换后的字符串。

格式：re.sub(pattern, repl, string, count)；

用-替代,如下：


```python
import retext = "aaa,bbb,ccc,ddd"print(re.sub(r',', '-', text))
```

    aaa-bbb-ccc-ddd


#### subn()

返回替换次数。

格式：subn(pattern, repl, string, count=0, flags=0)；
解释：用A替换123中的1，结果为A23，repl就是指的A。

把所有的数字替换为A：




```python
print(re.subn('\d','A','1asd2dkjf34'))
```

    ('AasdAdkjfAA', 4)



```python
import retext = input()#********** Begin *********##1.匹配以t开头的所有单词并显示itext = re.finditer(r'\bt\w*\b',text)for i in itext:    print(i.group())#2.用空格分割句子print(re.split(r'\s+',text))#3.用‘-’代替句子中的空格 print(re.sub(r'\s','-',text))#4.用‘-’代替句子中的空格，并返回替换次数print(re.subn(r'\s','-',text))#********** End **********#
```

    the is minethe['the', 'is', 'mine']the-is-mine('the-is-mine', 2)


## 文件操作与异常处理

### 从文件中读取数据

#### 读取整个文件


```python
with open('test.txt') as file_object:    contents = file_object.read()    print(contents)
```

文件中的第一行代码中有函数open()，用于打开文件，这是我们处理文件的第一步。函数open()中的参数'test.txt'就是要打开的文件。函数open()返回的是打开文件的对象，第一行代码就是把文本文件 test.txt 打开，并将其对象保存在file_object变量中。

关键字with的功能是在不再需要访问文件后自动将文件关闭。所以我们在这里只是open()打开了文件，但是没有加入close()代码关闭文件，因为 Python 会在处理文件之后自动将文件关闭

#### 逐行读取


```python
ith open('test.txt') as file_object:    for line in file_object:        print(line)
```

我们可以采取rstrip()方法消除空行


```python
ith open('test.txt') as file_object:    for line in file_object:        print(line.rstrip())
```

#### 创建一个包含文件各行内容的列表


```python
with open('test.txt') as file_object:    lines = file_object.readlines()
```

上述代码中readlines()方法就是从文本文件 test.txt 中依次读取每一行，并保存在lines列表中


```python
# 输出前n行n = int(input("n:"))with open('d.txt') as f :    lines = f.readlines()for i in range(0,n):    print(lines[i].rstrip())
```

### 将信息写入文件

#### 写入空文件

要将信息写入文本文件中，我们依然用open()方法，只不过除了将文本文件名当作参数传入函数open()中去之外，还需要再传入写参数w


```python
with open('test2.txt','w') as example:    example.write('Hello world!')
```

我们也可以往 test2.txt 中传入多行信息，例如：



```python
with open('test2.txt','w') as example:    example.write('Hello world!\n')    example.write('Hello python!\n')
```

#### 附加到文件尾

使用w命令打开一个待写入的文本文件时，如果该文本文件原来已经存在了，Python 将会在写入内容前将文本文件中原来的内容全部清空。所以我们如果要在已经存在的文本文件中添加信息内容，而不是将原来的信息内容都清除，就要采取附加模式打开文件。

我们在函数open()中传入了参数a,告诉 Python 程序我们是将信息加入到文本文件的末尾，而不是覆盖文件。


```python
with open('test2.txt','a') as example:    example.write('Hello my brothers!\n')    example.write('Hello my sisters!\n')
```


```python
#coding=utf-8#输入字符串s = input()# 请在此添加代码，将字符串s输入到test2.txt中#********** Begin *********#with open("src/Step2/test2.txt","w") as f:    f.write(s)#********** End **********##输出test2.txt中的内容with open('src/Step2/test2.txt') as file_object:    lines = file_object.readlines()for line in lines:    print(line.rstrip())
```

### 异常处理

当 Python 程序在运行过程中出现错误时，都会创建一个异常对象，如果我们编写了处理异常和错误的代码，程序将继续运行。如果我们没有对异常和错误进行处理，程序就会停止，显示一个t\fraceback，其中包含有关异常和错误的报告。

所以我们要主动编写异常处理的代码，要敢于在错误面前吭声，这样程序报错时就会显示我们自己编写的友好的错误信息，而不是让人困惑的t\fraceback。

我们一般使用try-except代码块处理异常，try-except代码块让 Python 程序在遇到错误时执行指定的操作，而不是产生t\fraceback

#### try-except


```python
print(2/0)
```


    ---------------------------------------------------------------------------ZeroDivisionError                         Traceback (most recent call last)<ipython-input-24-d2c0889640ff> in <module>----> 1 print(2/0)


    ZeroDivisionError: division by zero



```python
try:    print(2/0)except:    print("We can't divide by zero!")
```

    We can't divide by zero!


ry-except代码块的作用就是当try代码块中的程序代码运行没有错误，则跳过except代码块；反之如果try代码块中的程序代码运行出现错误，则运行except代码块中的内容，一般except代码块中的内容都是输出错误信息。

如果except代码块后面还有其他代码，程序将继续运行，因为 Python 已经在程序报错后执行了except代码块中的内容，告诉了错误信息，所以可以继续运行程序

#### raise

除了系统自动抛出异常外，程序员也可以通过 Python 的raise显式抛出自己的包含特定信息的异常。一旦执行了raise语句，raise之后的语句将不能执行。




```python
ef read_C():    try:        C = float(sys.argv[1])       except ValueError:        raise ValueError('Degrees must be number, not "%s"' % sys.argv[1])    if C < -273.15:        raise ValueError('C=%g is a non-physical value!' % C)    return C
```

#### else代码块

可以在try-except代码块后面添加try代码块，当try代码块中的程序运行没有异常时，程序将运行else代码块中的内容


```python
a = int(input())b = int(input())try:    answer = a/bexcept:    print("We can't divide by zero!")else:    print(answer)    
```

    30We can't divide by zero!


try-except-else代码块的原理大致如下：先运行try代码块中的程序内容，如果运行出错则执行except代码块中的程序内容，如果运行正确则执行else代码块中的程序内容

## Python堆栈与队列

### 熟悉list

#### 弹出第一个和最后一个元素


```python
ls = [1, 2, 3]print(ls)#删除前的lsval = ls[0]del(ls[0])print(val)#输出第一个元素的值print(ls)#输出修改后的ls
```

    [1, 2, 3]1[2, 3]


很明显，过程比较麻烦，需要先取再删

我们可以使用pop()

其接收一个整数，表示需要获取的元素的下标，且支持负数下标，不使用参数，则默认弹出最后一个元素。


```python
ls = [1, 2, 3]print(ls)#删除前的lsval = ls.pop(-1)#如果是获取最后一个元素的值，此处的 -1 可省略print(val)#输出最后一个元素的值print(ls)#输出修改后的lsval = ls.pop(0)print(val)#输出第一个元素的值print(ls)#输出修改后的ls
```

    [1, 2, 3]3[1, 2]1[2]


#### 向list添加数据


```python
ls = [1, 2, 3]print(ls)ls.append([4, 5, 6])print(ls)#输出通过append函数修改后的lsls.extend([4, 5, 6])print(ls)#输出通过extend函数修改后的ls
```

    [1, 2, 3][1, 2, 3, [4, 5, 6]][1, 2, 3, [4, 5, 6], 4, 5, 6]


append 函数是把参数直接原封不动地添加到 ls 对象的尾部，而 extend 函数是把参数中的元素提取出来，然后再添加到 ls 对象的尾部，所以大家在用的时候，要视情况选择正确的函数。


```python
ls = [1, 2, 3]print(ls)ls = ls + [4, 5, 6]print(ls)#输出类似extend函数修改后的ls
```

    [1, 2, 3][1, 2, 3, 4, 5, 6]


### 用Python实现简单的栈

#### 栈的基本操作

栈的基本操作
栈（ Stack ）又名堆栈，它是一种运算受限的线性表。
其限制是仅允许在表的一端进行插入和删除运算。这一端被称为栈顶，相对地，把另一端称为栈底。

向一个栈插入新元素，又称作进栈、入栈或压栈，它是把新元素放到栈顶元素的上面，使之成为新的栈顶元素；
从一个栈删除元素，又称作出栈或退栈，它是把栈顶元素删除掉，使其相邻的元素成为新的栈顶元素。

栈元素的出入特点是先入后出或后入先出（FILO—first in last out）。

一开始需要声明栈的大小 size ，栈有一个 top 指针，始终指向栈顶元素，空栈 top 值为 -1 。
当栈没有满时，可以在栈顶进行压栈操作；
当栈不空时，可以将栈顶元素弹出，即出栈操作。





```python
class Stack():    def __init__(self,size=5):        self.top = -1        self.size = size        self.stack = []            def is_full(self):        return self.top == self.size-1    def is_empty(self):        return self.top == -1    def push(self,x):        if self.is_full():            return             raise Exception("满了！没法入栈了！")        else:            self.top += 1            self.stack.append(x)                def pop(self,x):        if is_empty():            return             raise Exception("栈空了，没法弹出！")        else:            self.top -= 1            self.stack.pop()    def __repr__():        return str(self.stack)
```

### 用Python实现简单的队列

队列（ Queue ）是一种特殊的线性表，特殊之处在于，它只允许在表的前端（ front ）进行删除操作，即出队。而在表的后端（ rear ）进行插入操作，即入队。

和栈一样，队列是一种操作受限制的线性表。进行插入操作的端称为队尾，进行删除操作的端称为队首。

队列元素的出入特点是先入先出或后入后出（FIFO—first in first out）。

一开始需要声明队列的大小 size ，队列有一个 front 指针和一个 rear ，分别指向队首元素和队尾元素。

当队列没有满时，可以在队尾进行入队操作；
当队列不空时，可以将队首元素弹出，即出队操作


```python
class Queue():    def __init__(self,size=5):        self.size = size        self.front = 0        self.rear = 0        self.queue = []    def is_full(self):        return self.rear - self.front == self.size    def is_empty(self):        return self.front == self.rear    def en_queue(self,x):        if is_full():            return             raise Exception("Queue is full！")        else:            self.rear += 1            self.queue.append(x)    def out_queue(self,x):        if self.is_empty():            return            raise Exception("Queue is empty!")        else:            self.front += 1            self.queue.pop(0)    def __repr__(self):        return str(self.queue)
```

### 栈在括号匹配的应用


```python
class Solution:    def isValid(self, s):        """        :type s: str        :rtype: bool        """        #请在此添加代码，实现判断字符串s是否合法，若合法，返回True，否则返回False        #********** Begin *********#        try:            stack = []            for i in s:                if i =='(':                    stack.append(')')                if i =='{':                    stack.append('}')                if i =='[':                    stack.append(']')                if i in ')}]':                    if stack.pop() != i:                        return False        except IndexError:            return False        return stack ==  []        #********** End **********#
```


      File "<tokenize>", line 13    except IndexError:    ^IndentationError: unindent does not match any outer indentation level



### 栈在表达式求值中的应用

#### 逆波兰表达式

后缀表达式

中缀表达式(a+b)*c-(a+b)/e对应的的后缀表达式为ab+c*ab+e/-

中序表达式的简单是相对人类的思维结构来说的，对计算机而言，中序表达式是非常复杂的结构。相对的，逆波兰式在计算机看来，却是比较简单易懂的结构。因为计算机普遍采用的内存结构是栈式结构，它执行先进后出的顺序

栈和表示式求值

算法思想：

顺序扫描表达式的每一项，如果该项是操作数，则将其直接压入栈中；

如果该项是运算符op，则连续从栈弹出 2 个操作数X和Y，并将X和Y关于op的运算结果入栈；

全部处理后，栈顶元素就是最终表达式的值


```python
class Solution:    def evalRPN(self, tokens):        """        :type tokens: List[str]        :rtype: int        """        #请在此添加代码，实现将含有逆波兰表达式的list转换成其对应表达式的值，并返回        #********** Begin *********#        ls = []        for item in tokens:            #print(f'item {item} ls {ls}')            if item[-1] >= '0' and item[-1] <= '9':                ls.append(int(item))            else:                if item == '+':                    ls[-2] = ls[-2] + ls[-1]                elif item == '-':                    ls[-2] = ls[-2] - ls[-1]                elif item == '*':                    ls[-2] = ls[-2] * ls[-1]                elif item == '/':                    tmp = -1 if ls[-2] * ls[-1] < 0 else 1                    ls[-2] = abs(ls[-2]) // abs(ls[-1]) * tmp                ls.pop()        return ls[0]        #********** End **********#
```

### 栈在递归中的应用

#### 二叉树的后续遍历

后序遍历（ Postorder Traversal ，LRD ）是二叉树遍历的一种，也叫做后根遍历、后序周游。后序遍历有递归算法和非递归算法两种。在二叉树中，先左后右再根。巧记：左右根。

算法描述

后序遍历，首先遍历左子树，然后遍历右子树，最后访问根结点。在遍历左、右子树时，仍然先遍历左子树，然后遍历右子树，最后遍历根结点。即：

若二叉树为空，则结束返回；

否则：

后序遍历左子树；
后序遍历右子树；
访问根结点。


```python
class TreeNode:    def __init__(self, x):        self.val = x        self.left = None        self.right = None
```

则该树的递归算法为：


```python
def lrd(tree):    if tree:        lrd(tree.left)        lrd(tree.right)        vis(tree.val)
```

将递归改为非递归：

如：斐波那契数列


```python
def fibonacci(n):    if n <= 1:        return n    return fibonacci(n-1) + fibonacci(n-2)
```

用栈改为非递归：---借助一个大小为2的栈即可


```python
def fibonacci(n):    stack = [0, 1]    if n <= 1:        return n    for i in range(2, n+1):        stack[0], stack[1] = stack[1], stack[0] + stack[1]    return stack[1]
```

二叉树的非递归算法

从根结点开始不断的访问其左子树，并将访问过的结点入栈；

如果结点为空，则取栈顶元素，为判断本次返回是，从左子树返回，还是右子树返回，需要临时变量 pre 记录上一次访问的结点。如果栈顶元素是从左子树返回，并且其存在右子树，则访问其右子树，并回到步骤 1；

否则，该栈顶元素的左、右子树都已经遍历完，将栈顶元素出栈，标记该结点已经访问，并将下一个访问的结点设置为空，回到步骤 2。

## 迭代器与生成器

### 迭代器

迭代，就是反复执行某一步骤的意思。迭代器，则是用来实现这一动作的东西。

迭代器的概念主要涉及到两部分：可迭代对象Iterable和迭代器对象Iterator

可迭代对象
凡是可以返回一个迭代器的对象，都可以叫做可迭代对象，可迭代对象不是某一个具体的对象，而是实现了特定功能的一类对象

tuple，list、dict、str等类型都是可迭代对象

可迭代对象实现了成员函数__iter__，这个函数返回一个迭代器，因此也可以这样说：实现了__iter__函数的对象就是可迭代对象。

迭代器
迭代器是一个内部带有状态的对象。在你调用next函数时，它会根据内部的状态来返回不同的值，以此达到遍历数据的目的


```python
data = [1,2,3]i1 = iter(data) #获取data的一个迭代器i2 = iter(data) #获取data的一个迭代器print(next(i1))print(next(i1))print(next(i1))print(next(i2))print(next(i2))print(next(i2))
```

    123123


可以看到对同一个迭代器连续调用3次next返回的是三个不同的值，而且，从同一个可迭代对象返回的不同迭代器互相不影响。

当迭代器里的元素都遍历过之后，再调用next就会引发StopIteration异常，这时需要使用try...except 语句来处理


```python
data = [1,2,3]i1 = iter(data)try:    while(True): #循环获取迭代器的值        print(next(i1))except StopIteration:    print("stop") #迭代结束，抛出异常
```

    123stop


还可以使用for来避免异常的抛出

#### 创建迭代器

一个迭代器对象需要实现两个成员函数：__iter__和__next__。
__iter__函数返回迭代器自身，__next__函数则是根据内部状态决定是返回一个值，还是引发一个StopIteration异常。




```python
class SimpleRange:    start = 0    max = 0    def __init__(self,start,max): #构造函数，指定Range的起始值start与最大值max        self.start = start        self.max = max    def __iter__(self):         return self #返回自己    def __next__(self):        if self.start < self.max: #判断start是否到达了max            t = self.start            self.start += 1            return t #不是则返回start的值，并且start自增1        else:            raise StopIteration #是则引发异常，宣告迭代结束for s in SimpleRange(0,3): #获取0-2的值    print(s)
```

    012


### 生成器

#### 生成器函数

生成器函数与一个普通函数很像，但是当它要返回一个值时，用的不是return，而是yield。只要函数中使用了yield关键字，他就变成了一个生成器函数。


```python
def func():        print(1)    yield 1        print(2)    yield 2s = func()print(next(s))print(next(s))
```

    1122


会返回一个生成器，并不立刻执行函数，只有当对生成器进行next操作时，才会真正开始执行函数，我们称这种特性为延迟计算（Lazy Evaluation）。

并且，每一次进行next操作，函数会从上一个yield语句（或者函数第一条语句）执行到下一个yield语句（或者函数结尾），然后返回yield的值


```python
def Fun1():    n = 0    yield n    n += 1    yield n    n += 1    yield ng = Fun1()for s in g: #生成器也是一个迭代器，所以也可以使用for语句    print(s)
```

    012


生成器不仅能保持执行流程，还能保存局部变量

#### 使用生成器创建迭代器


```python
def Fun1(max):    start = 0    while start < max:        yield start        start += 1g = Fun1(3) #得到一个能返回0-2的生成器for s in g:    print(s)
```

    012


我们将这种能够中断执行，之后又能从断点以上一次的状态继续执行的函数叫做协程

#### 列表生成式


```python
data = [x**2 for x in range(11)]data
```




    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]



带有条件筛选的列表生成式


```python
data = [x**2 for x in range(11) if x%2==0 ]data
```




    [0, 4, 16, 36, 64, 100]




```python
data = [x*y for x in range(11) if x%2==0 for y in range(5)]data
```




    [0, 0, 0, 0, 0, 0, 2, 4, 6, 8, 0, 4, 8, 12, 16, 0, 6, 12, 18, 24, 0, 8, 16, 24, 32, 0, 10, 20, 30, 40]



#### 生成器表达式

只有使用next函数调用时，才会一项一项的返回元素：


```python
lis = (x*x for x in range(10))print(next(lis))print(next(lis))print(next(lis))print(next(lis))
```

    0149


生成器表达式比列表生成器更节省空间

## 数据解析：JSON与XML

### JSON基础知识

JSON 全称：JavaScript Object Notation(JavaScript 对象表示法)，是一种轻量级的文本数据交换格式。与接下来要介绍的 XML 相比，拥有更小、更快、更易解析的特点。

一个典型的 JSON 格式的字符串如下：




```python
{"students":     [        { "name":"赵昊" , "age": 15 },         { "name":"龙傲天" , "age": 16 },         { "name":"叶良辰" , "age": 17 }    ]}
```




    {'students': [{'name': '赵昊', 'age': 15},  {'name': '龙傲天', 'age': 16},  {'name': '叶良辰', 'age': 17}]}



#### 数据表示

JSON 中数据都以名称:值的形式表示，名称包括在一对双引号" "中，值则有多种形式，多条数据之间用逗号,隔开

#### 数据类型


JSON 的值可以是如下类型：

字符串（在双引号中）

数字（整数或浮点数）

逻辑值（true 或 false）

数组（在中括号中）

对象（在大括号中）

null

#### 数组

JSON 的数组用一对方括号[]表示，类似于list，数组元素用逗号,隔开，元素值可以是任意 JSON 数据类型


```python
"names":["赵昊","龙傲天","叶良辰"]"ages":[15,16,17]
```

#### 对象

JSON 的对象用一对大括号{}表示，类似于dict，对象可以拥有多个名称/值 对，名称/值 对用逗号,隔开


```python
"first":{ "name":"赵昊" , "age": 15 }
```

### 使用JSON库

json库是 Python 内置的一个用于操作 JSON 数据的库，提供了几个函数用于解析与生成（或者说反序列化与序列化）JSON 格式的数据。

#### 解析JSON数据

json库提供了一个函数loads，用于从 Python 的字符串中解析 JSON 数据。使用它的方法很简单，只需将含有 JSON 数据的字符串当做参数传递给它，它的返回值就是由 Python 中的基础数据类型组成的对象


```python
import jsondata = '{"a":1,"b":2,"c":3,"d":4,"e":5}';text = json.loads(data)print(text)
```

    {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}


JSON 的对象类型转换成了 Python 的dict类型

JSON	Python

object(对象)	dict

array(数组)	list

string(字符串)	unicode

number (int)	int, 

number (real)	float

true	True

false	False

null	None

JSON 数据类型转化成 Python 数据类型后，就可以按照 Python 的方式来使用了：


```python
import jsondata = '[1,2,3]';text = json.loads(data)text.append(4) #调用list的append函数print(text)
```

    [1, 2, 3, 4]


如果需要以不同的字符编码来解析，可以指定 encoding参数


```python
import jsondata = '{"a":1,"b":2,"c":3,"d":4,"e":5}';text = json.loads(data,encoding = "utf-8")print(text)
```

    {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}


    <ipython-input-10-cb2d81e933e3>:3: DeprecationWarning: 'encoding' is ignored and deprecated. It will be removed in Python 3.9  text = json.loads(data,encoding = "utf-8")


json库的另一个函数load也是用于解析 JSON 数据的，它与loads函数唯一不同的地方在于，它是从文件中解析


```python
import jsondata = open("test.txt","r",encoding = "utf-8")text = json.load(data) #将文件对象传递给load函数print(text)fp.close()
```

#### 生成JSON数据

与解析的那两个函数相对应，json库也提供了两个函数：dumps和dump，来将由 Python 基础数据类型组成的对象转化成 JSON 数据，使用方法也类似


```python
import jsondata = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]json = json.dumps(data) #转化成JSON格式的字符串print(json)
```

    [{"a": 1, "b": 2, "c": 3, "d": 4, "e": 5}]


dumps没有可选参数encoding，当要转化的对象含有中文等非 ASCII 字符时，建议指定可选参数ensure_ascii为False。否则非 ASCII 的字符将会被显示成\uXXXX的形式


```python
data = {"name":"小明"}print(json.dumps(data)) #ensure_ascii默认值为Trueprint(json.dumps(data,ensure_ascii= False)) #指定ensure_ascii为False
```


    ---------------------------------------------------------------------------AttributeError                            Traceback (most recent call last)<ipython-input-12-4f1ab10a2c1a> in <module>      1 data = {"name":"小明"}----> 2 print(json.dumps(data)) #ensure_ascii默认值为True      3 print(json.dumps(data,ensure_ascii= False)) #指定ensure_ascii为False


    AttributeError: 'str' object has no attribute 'dumps'


使用dump函数直接输出到文件也很简单，只需多传递一个文件对象作为参数。


```python
import jsonfp = open("test.txt","w")data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]json.dump(data,fp) #转化成JSON格式的字符串后输出到文件fp.close()
```

### XML

XML 全称可扩展标记语言（EXtensible Markup Language），是一种用于标记电子文件使其具有结构性的标记语言，可以用来标记数据、定义数据类型。


```python
<?xml version="1.0" encoding="UTF-8"?>
<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>
```

#### 文档的声明

XML 文档的声明是可选的，如果要声明，需要将其放在文档的第一行最顶端。


```python
<?xml version="1.0" encoding="utf-8"?>
```

以上定义了 XML 的版本1.0和所使用的编码utf-8。




```python

```

#### 元素

XML 元素指的是 XML 文件中出现的标签，一个标签分为开始标签和结束标签，结束标签与开始标签名称相同，只是要在前面加一个斜杠/


```python
<hello></hello>
<to></to>
```

一个标签中也可以嵌套其他的若干个子标签。但所有的标签必须合理的嵌套，绝不允许交叉嵌套


```python
<student>
    <name>赵昊</name>
    <age>16</age>
</student>
```

格式良好的 XML 文档必须有且仅有一个根元素，其他的元素都是这个元素的子孙元素

元素命名规则

名称可以包含字母、数字以及其他的字符

名称不能以数字或者标点符号开始

名称不能以字母 xml（或者 XML、Xml 等等）开始

名称不能包含空格

名称是大小写敏感的

XML 没有保留字，元素名称可以任意使用

#### 属性

一个元素可以有多个属性，每个属性都有它自己的名称和取值。同一个元素下，属性名称不能重复。属性的值一定要用双引号或者单引号括起来，


```python
<date year="2018" month="7" day="28"></date>
```

属性的命名规范和元素的命名规范一样

#### 注释

XML 文件中注释采用：‘’‘< ! --注释内容-- >’‘’ 这样的格式，注释没有结束标签，不能嵌套


```python
<!--一个正确的注释1-->
<hello>
<!--一个正确的注释2-->
</hello>
<!--<!--一个发生嵌套的错误的注释-->-->
```


```python
<?xml version='1.0' encoding='utf-8'?>
<data count="3">
    <student name="赵昊" age="15" sex="男性"></student>
    <student name="龙傲天" age="16" sex="男性"></student>
    <student name="玛丽苏" age="15" sex="女性"></student>
</data>
```

### SAX解析XML文件

SAX是一种基于事件驱动的 API，使用SAX解析 XML 时，主要分两个部分：解析器和事件处理器

#### 解析器

解析器负责读取 XML 文档，并向事件处理器发送事件，比如元素开始跟元素结束事件。
SAX提供了两个函数：parse和parseString。前者用于从文件中解析 XML 数据，后者用于从字符串中解析 XML 数据


```python
xml.sax.parse( xmlfile, contenthandler)
xml.sax.parseString(xmlstring, contenthandler)
```

parse函数的第一个参数是 XML 文件的路径


```python
xml.sax.parse("test.xml",contenthandler)
```

parseString函数的第一个参数是，含有 XML 数据的字符串


```python
data = "<data>Hello</data>"
xml.sax.parseString(data,contenthandler)
```

而它们的第二个参数则是，接下来要介绍的事件处理器

#### 事件处理器

事件处理器则负责对事件作出响应，对传递的 XML 数据进行处理。
一个事件处理器必须是ContentHandler类型的子类，通过重写父类的以下函数来响应解析器的事件请求：

cha\fracters(content)函数，它会在以下时机被调用：
如果从一行开始，遇到标签之前，存在字符，则content的值为这些字符串；
如果从一个标签，遇到下一个标签之前，存在字符，则content的值为这些字符串；
如果从一个标签，遇到行结束符（换行符）之前，存在字符，则content的值为这些字符串；
标签可以是开始标签，也可以是结束标签。

startDocument()函数，它在文档启动的时候调用；

endDocument()函数，它在解析器到达文档结尾时调用

startElement(name, attrs)函数，它在遇到 XML 开始标签时调用，name是标签的名字，attrs是标签的属性值字典；

endElement(name)函数，它在遇到 XML 结束标签时调用。


```python
<data>文字1文字2<ele1>元素1数据</ele1>文字3文字4<ele2>元素2数据</ele2>文字5</data>
```


```python
import xml.saxclass Handler(xml.sax.ContentHandler):    def startDocument(self):        print("文档开始")    def endDocument(self):        print("文档结束")    def startElement(self,name,attrs):        print("开始标签：" , name)    def endElement(self,name):        print("结束标签：" , name)    def cha\fracters(self,content):        print("数据：" ,content)if __name__ == '__main__':    xml.sax.parse("test.xml",Handler())
```

会得到结果：

文档开始

开始标签： data

数据： 文字1

数据：<换行>

数据： 文字2

开始标签： ele1

数据： 元素1数据

结束标签： ele1

数据： 文字3

数据：<换行>

数据： 文字4

开始标签： ele2

数据： 元素2数据

结束标签： ele2

数据： 文字5

数据：<换行>

结束标签： data

文档结束

### 使用ElementTree解析XML

#### ElementTree

xml.etree.ElementTree模块是一个轻量级的 DOM(文件对象模型)，具有方便友好的 API。代码可用性好，速度快，消耗内存少。
ElementTree模块大致可以三部分：ElementTree类，Element类以及一些操作 XML 的函数。

#### 解析

xml.etree.ElementTree提供了两个函数：parse和fromstring，用于从文件和字符串解析 XML 数据


```python
import xml.etree.ElementTree as ETdoc = ET.parse("data.xml") #从文件解析XML数据root = doc.getroot() #获取根元素data = "<a>hello</a>"el = ET.fromstring(data) #从字符串解析XML数据
```

parse函数返回一个ElementTree对象，fromstring返回一个Element对象。

Element对象代表一个 XML 元素，它的功能接下来会介绍。

ElementTree对象代表一个 XML 文档，它提供了函数getroot，来获取一个文档的根元素

#### 查找元素

Element对象和ElementTree对象都提供了用于在子元素查找元素的函数：

find(name)：用于在直接子元素中，查找一个名为name的元素；

findall(name)：用于在直接子元素中，查找所有名为name的元素，它的返回值可以看做一个所有元素都是Element对象的tuple对象，可以对它进行迭代操作或者索引[]操作；

iter(name = None)：用于在当前元素下的所有子元素中，查找名为name的元素，如果不指定name，则返回所有子元素。它返回一个迭代器对象。

#### 获取元素的文本与属性值

Element有一个属性text，这个属性用于获取直接在这个元素的开始、结束标志之间的文本。如果没有文本，则返回空字符串


```python
import xml.etree.ElementTree as ETdata = "<a>TextA<b>TextB</b></a>"ele = ET.fromstring(data)print(ele.text)print(ele.find("b").text)
```

如果要获取一个元素的某个属性，可以使用get(name)函数，它会寻找当前元素上名为name的属性。如果找到就返回这个属性的值，没找到则返回空字符串


```python
import xml.etree.ElementTree as ETdoc = ET.parse("data.xml") #从文件解析XML数据root = doc.getroot() #获取根元素for s in root.findall("movie"): #选择所有名为moive的元素        de = s.find("description") #获取description元素        print("%s: %s" % (s.get("title"),de.text)) #获取tile属性，与description元素的文本值格式化输出
```

## 进程与线程

### 初识多进程

#### 什么是进程

什么是进程？ 最直观的就是一个个pid，进程是程序在计算机上的一次执行活动。

#### 多进程的优点

多进程技术，就是可以让你在同一时间同时执行多条任务的技术。你的代码将不仅仅是从上到下，从左到右这样规规矩矩的一条线执行。你可以一条线跟你的客户交流，另一条线，你早就把你外卖送到了其他客户的手里

#### 如何实现多进程

Python是跨平台的，自然也应该提供一个跨平台的多进程支持。multiprocessing模块就是跨平台版本的多进程模块。

实现多进程可以使用Python官方提供的一个类Process。

Process类用来描述一个进程对象。创建子进程的时候，只需要传入一个执行函数和函数的参数，即可完成Process示例的创建。

•start()方法启动进程；

•join()方法实现进程间的同步，等待所有进程退出；

•close()用来阻止多余的进程涌入进程池 Pool造成进程阻塞；


```python
multiprocessing.Process(group=None, target=None, name=None, args=(), kwargs={}, *, daemon=None)
```

target是函数名字，需要调用的函数；

args函数需要的参数，以tuple的形式传入。


```python
import multiprocessingimport osdef run_proc(name):    print('Child process {0} {1} Running '.format(name, os.getpid()))if __name__ == '__main__':    print('Parent process {0} is Running'.format(os.getpid()))    for i in range(5):        p = multiprocessing.Process(target=run_proc, args=(str(i),))        print('process start')        p.start()    p.join()    print('Process close')
```

    Parent process 724 is Runningprocess startprocess startprocess startprocess startprocess startProcess close


#### Pool类

如果进程数太多了，我一个人根本搞不过来，怎么办呢？还好有进程池Pool这个好基友啊，简单来说，Pool可以提供指定数量的进程，供用户调用。当有新的请求提交到Pool中时，如果池还没有满，那么就会创建一个新的进程，用来执行该请求；但如果池中的进程数，已经达到规定最大值，那么该请求就会等待，直到池中有进程结束，才会创建新的进程。

Pool可以提供指定数量的进程供用户使用，默认是 CPU 核数。当有新的请求提交到Pool的时候，如果池子没有满，会创建一个进程来执行，否则就会让该请求等待；

Pool对象调用join方法，会等待所有的子进程执行完毕；

调用join方法之前，必须调用close；

调用close之后，就不能继续添加新的Process了。

#### pool.apply_async

apply_async方法用来同步执行进程，允许多个进程同时进入池子。
apply_async是异步非阻塞的。
异步处理就是，你现在问我问题，我可以不回答你，等我有时间了，再处理你这个问题。同步就反其道而行之，同步信息会立即被处理。


```python
import multiprocessingimport osimport timedef run_task(name):    print('Task {0} pid {1} is running, parent id is {2}'.format(name, os.getpid(), os.getppid()))    time.sleep(1)    print('Task {0} end.'.format(name))if __name__ == '__main__':    print('current process {0}'.format(os.getpid()))    p = multiprocessing.Pool(processes=3)    for i in range(6):        p.apply_async(run_task, args=(i,))    print('Waiting for all subprocesses done...')    p.close()    p.join()    print('All processes done!')
```

    current process 724Waiting for all subprocesses done...


完全没有等待子进程执行完毕，主进程就已经执行完毕，并退出程序。

#### pool.apply

该方法只能允许一个进程进入池子，在一个进程结束之后，另外一个进程才可以进入池子。

apply方法是阻塞的。

意思就是等待当前子进程执行完毕后，再执行下一个进程。

因为apply是阻塞的，所以进入子进程执行后，等待当前子进程执行完毕，再继续执行下一个进程。




```python
import multiprocessingimport osimport timedef run_task(name):    print('Task {0} pid {1} is running, parent id is {2}'.format(name, os.getpid(), os.getppid()))    time.sleep(1)    print('Task {0} end.'.format(name))if __name__ == '__main__':    print('current process {0}'.format(os.getpid()))    p = multiprocessing.Pool(processes=3)    for i in range(6):        p.apply(run_task, args=(i,))    print('Waiting for all subprocesses done...')    p.close()    p.join()    print('All processes done!')
```

#### apply 和 apply_async 的区别

apply是阻塞式的。
首先主进程开始运行，碰到子进程，操作系统切换到子进程，等待子进程运行结束后，再切换到另外一个子进程，直到所有子进程运行完毕。然后，再切换到主进程，运行剩余的部分。

apply_async是异步非阻塞式的。
首先主进程开始运行，碰到子进程后，主进程说：让我先运行个够，等到操作系统进行进程切换的时候，再交给子进程运行。因为我们的程序太短，然而还没等到操作系统进行进程切换，主进程就运行完毕了。想要子进程执行，就告诉主进程：你等着所有子进程执行完毕后，再运行剩余部分。

一般建议：**废弃apply，使用apply_async**

#### Python多线程

线程：简单来说，一个进程中包含多个线程，比如打开一个 QQ（进程），然后你一边聊 QQ（一个线程），一边用 QQ 传送文件（一个线程），等等。在一个进程内部，要同时干多件事，就需要同时运行多个“子任务”，我们把进程内的这些“子任务”称为线程（ Thread 

使用线程可以把占据长时间的程序任务放到后台去处理；
用户界面可以更加吸引人，比如用户点击了一个按钮，去触发某些事件的处理，可以弹出一个进度条，来显示处理的进度；
程序的运行速度可能加快；
在一些等待的任务实现上，如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下，我们可以释放一些珍贵的资源，如内存占用等等。


#### 如何编写多线程

Python 的标准库提供了两个模块：_thread和threading，_thread是低级模块，threading是高级模块，对_thread进行了封装。绝大多数情况下，我们只需要使用threading这个高级模块。

启动一个线程就是，把一个函数传入，并创建Thread实例，然后调用start()开始执行：




```python
import time, threading# 新线程执行的代码:def loop():    print('thread %s is running...' % threading.current_thread().name)    n = 0    while n < 5:        n = n + 1        print('thread %s >>> %s' % (threading.current_thread().name, n))        time.sleep(1)    print('thread %s ended.' % threading.current_thread().name)print('thread %s is running...' % threading.current_thread().name)t = threading.Thread(target=loop, name='LoopThread')t.start()t.join()print('thread %s ended.' % threading.current_thread().name)
```

    thread MainThread is running...thread LoopThread is running...thread LoopThread >>> 1thread LoopThread >>> 2thread LoopThread >>> 3thread LoopThread >>> 4thread LoopThread >>> 5thread LoopThread ended.thread MainThread ended.


#### 线程锁

线程安全

由于线程之间是进行随机调度，当多个线程同时修改同一条数据时，可能会出现脏数据。所以，出现了线程锁，即同一时刻，允许一个线程执行操作。线程锁用于锁定资源，你可以定义多个锁， 像下面的代码, 当你需要独占某一资源时，任何一个锁都可以锁这个资源。就好比你用不同的锁，都可以把相同的一个门，锁住是一个道理。

由于线程之间是进行随机调度，如果有多个线程同时操作一个对象，如果没有很好地保护该对象，会造成程序结果的不可预期，我们也称此为“线程不安全”。




```python
import threadingimport timedef run(n):    global num    num += 1num = 0t_obj = []for i in range(20000):    t = threading.Thread(target=run, args=("t-%s" % i,))    t.start()    t_obj.append(t)for t in t_obj:    t.join()print("num:",num)"""产生脏数据后的运行结果：num: 19999"""
```

    num: 20000





    '\n产生脏数据后的运行结果：\nnum: 19999\n'



#### 互斥锁

python 提供了一种 "相互排斥"的方法（互斥锁即由此得名）。两个线程不能同时对同一个互斥对象加锁。

互斥锁是这样工作的。如果线程 a 试图锁定一个互斥对象，而此时线程 b 已锁定了同一个互斥对象时，线程 a 就将进入睡眠状态。一旦线程 b 释放了互斥锁，线程 a 就能够锁定这个互斥对象。同样地，当线程 a 正锁定互斥对象时，如果线程 c 试图锁定互斥对象的话，线程 c 也将临时进入睡眠状态。对已锁定的互斥对象上，调用互斥锁的所有线程都将进入睡眠状态，这些睡眠的线程将“排队”访问这个互斥对象。


```python
import threadingimport timedef run(n):    lock.acquire()  #获取锁    global num    num += 1    lock.release()  #释放锁lock = threading.Lock()     #实例化一个锁对象num = 0t_obj = []  for i in range(20000):    t = threading.Thread(target=run, args=("t-%s" % i,))    t.start()    t_obj.append(t)for t in t_obj:    t.join()print("num:", num)
```

    num: 20000


**判断给定区间内的素数个数**


```python
import threadingimport mathans = 0lock = threading.Lock()# 判断数字是否为质数#********** Begin *********#def isPrime(n):    if n <= 1:        return False    for i in range(2, int(math.sqrt(n)) + 1):        if n % i == 0:            return False    return True#********** End *********##********** Begin *********## 计算给定区间含有多少个质数def howMany(T):    sum = 0;    for i in range(T[0], T[1] + 1):        if isPrime(i):            sum += 1    lock.acquire()    try:        global ans        ans += sum    finally:        lock.release()#********** End *********##********** Begin *********## 对整个数字空间N进行分段CPU_COUNTdef seprateNum(N, CPU_COUNT):    list = [[i * (N // CPU_COUNT) + 1, (i + 1) * (N // CPU_COUNT)] for i in range(0, CPU_COUNT)]    list[0][0] = 1    if list[CPU_COUNT - 1][1] < N:        list[CPU_COUNT - 1][1] = N    return list#********** End *********#if __name__ == '__main__':    N = int(input())    threadNum = 32    t = []    sepList = seprateNum(N, threadNum)    for i in range(0, threadNum):        t.append(threading.Thread(target = howMany, args = (sepList[i], )))        t[i].start()    for i in range(0, threadNum):        t[i].join()    print(N - 1 - ans, end = '')
```

    105

### Python-ThreadLocal变量

我们知道多线程环境下，每一个线程均可以使用所属进程的全局变量。如果一个线程对全局变量进行了修改，将会影响到其他所有的线程。为了避免多个线程，同时对变量进行修改，引入了线程同步机制，通过互斥锁，条件变量或者读写锁来控制对全局变量的访问。

全局变量并不能满足多线程环境的需求，很多时候线程还需要拥有自己的私有数据，这些数据对于其他线程来说不可见。因此，线程中也可以使用局部变量，局部变量只有线程自身可以访问，同一个进程下的其他线程不可访问。

有时候使用局部变量不太方便，因此 Python 提供了 ThreadLocal 变量，它本身是一个全局变量，但是每个线程却可以利用它，来保存属于自己的私有数据，这些私有数据对其他线程也是不可见的。

多线程全局变量的同步问题


```python
import threadingglobal_num = 0def thread_cal():    global global_num    for i in range(1000):        global_num += 1threads = []for i in range(10):    threads.append(threading.Thread(target=thread_cal))    threads[i].start()for i in range(10):    threads[i].join()print(global_num)
```

    10000


多线程中使用全局变量时，普遍存在这个问题，解决办法也很简单，可以使用互斥锁、条件变量或者是读写锁。下面考虑用互斥锁，来解决上面代码的问题。只需要在进行+1运算前加锁，运算完毕释放锁即可，这样就可以保证运算的原子性


```python
import threadingdef show(num):    print(threading.current_thread().getName(), num)def thread_cal():    local_num = 0    for _ in range(1000):        local_num += 1    show(local_num)threads = []for i in range(10):    threads.append(threading.Thread(target=thread_cal))    threads[i].start()
```

    Thread-40150 1000Thread-40151Thread-40152 1000 1000Thread-40153 1000Thread-40154 1000Thread-40155 1000Thread-40156 1000Thread-40157 1000Thread-40158 1000Thread-40159 1000


可以看出，这里每个线程都有自己的 local_num，各个线程之间互不干涉

#### Thread-local对象

上面程序中，我们需要给 show 函数传递 local_num 局部变量，并没有什么不妥。不过考虑在实际生产环境中，我们可能会调用很多函数，每个函数都需要很多局部变量，这时候用传递参数的方法会很不友好。

为了解决这个问题，一个直观的的方法就是建立一个全局字典，保存进程 ID 到该进程局部变量的映射关系，运行中的线程可以根据自己的 ID ，来获取本身拥有的数据。这样，就可以避免在函数调用中，传递参数


```python
global_data = {}def show():    cur_thread = threading.current_thread()    print(cur_thread.getName(), global_data[cur_thread])def thread_cal():    cur_thread = threading.current_thread()    global_data[cur_thread] = 0    for _ in range(1000):        global_data[cur_thread] += 1    show()  # Need no local variable.  Looks good....
```

保存一个全局字典，然后将线程标识符作为 key，相应线程的局部数据作为 value，这种做法并不完美。首先，每个函数在需要线程局部数据时，都需要先取得自己的线程ID，略显繁琐。更糟糕的是，这里并没有真正做到线程之间数据的隔离，因为每个线程都可以读取到全局的字典，每个线程都可以对字典内容进行更改。

为了更好解决这个问题，Python 线程库实现了 ThreadLocal 变量（很多语言都有类似的实现，比如 Java）。ThreadLocal 真正做到了线程之间的数据隔离，并且使用时，不需要手动获取自己的线程 ID


```python
global_data = threading.local()def show():    print(threading.current_thread().getName(), global_data.num)def thread_cal():    global_data.num = 0    for _ in range(1000):        global_data.num += 1    show()threads = []...
```

每个线程都可以通过 global_data.num， 获得自己独有的数据，并且每个线程读取到的 global_data 都不同，真正做到线程之间的隔离。


```python
import threadingglobal_data = threading.local()def action():    global_data.x = 0    for i in range(1000000):        global_data.x += 1        global_data.x -= 1x = int(input())thread = []for i in range(10):    thread.append(threading.Thread(target = action))    thread[i].start()for i in range(10):    thread[i].join()print(x)
```

    1010


### 进程与线程

**线程和进程的应用场景**

是否采用多任务的第二个考虑是任务的类型。我们可以把任务分为计算密集型和 IO 密集型。

计算密集型任务的特点是要进行大量的计算，消耗 CPU 资源，比如计算圆周率、对视频进行高清解码等等，全靠 CPU 的运算能力。这种计算密集型任务虽然也可以用多任务完成，但是任务越多，花在任务切换的时间就越多，CPU 执行任务的效率就越低。所以，要最高效地利用 CPU，计算密集型任务同时进行的数量，应当等于 CPU 的核心数。

计算密集型任务由于主要消耗 CPU 资源，因此，代码运行效率至关重要。Python这样的脚本语言运行效率很低，完全不适合计算密集型任务。对于计算密集型任务，最好用 C 语言编写。

第二种任务的类型是 IO 密集型，涉及到网络、磁盘 IO 的任务都是 IO 密集型任务。这类任务的特点是 CPU 消耗很少，任务的大部分时间都在等待 IO 操作完成（因为 IO 的速度远远低于 CPU 和内存的速度）。对于 IO 密集型任务，任务越多，CPU 效率越高，但也有一个限度。常见的大部分任务都是 IO 密集型任务，比如 Web 应用。

IO 密集型任务执行期间，99% 的时间都花在 IO 上，花在 CPU 上的时间很少。因此，用运行速度极快的 C 语言并不能提升运行效率。对于 IO 密集型任务，最合适的语言就是开发效率最高（代码量最少）的语言，脚本语言是首选，C 语言最差。

### 分布式进程

正如大家所知道的 Process 比 Thread 更稳定，而且 Process 可以分布到多台机器上，而 Thread 最多只能分布到同一台机器的多个 CPU 上。 Python 的 multiprocessing 模块不但支持多进程，其中 managers 子模块还支持把多进程分布到多台机器上。一个服务进程可以作为调度者，将任务分布到其他多个进程中，依靠网络通信。由于 managers 模块封装很好，不必了解网络通信的细节，就可以很容易地编写分布式多进程程序。

如果我们已经有一个通过 Queue 通信的多进程程序，在同一台机器上运行。现在，由于处理任务的进程任务繁重，希望把发送任务的进程和处理任务的进程分布到两台机器上，这应该怎么用分布式进程来实现呢？你已经知道了原有的 Queue 可以继续使用，而且通过 managers 模块把 Queue 通过网络暴露出去，就可以让其他机器的进程来访问 Queue 了。

# 高级篇---数据分析

## Numpy初体验

### Numpy创建数组

#### 一维数组

在 Python 中创建数组有许多的方法，这里我们使用 Numpy 中的arange方法快速的新建一个数组


```python
import numpy as npa = np.arange(5)a
```




    array([0, 1, 2, 3, 4])



#### 多维数组


```python
import numpy as np a  = np.array([np.arange(3),np.arange(3)])a
```




    array([[0, 1, 2],       [0, 1, 2]])



#### 复制数组


```python
import numpy as npx = [y for y in range(6)]b=np.array([x]*4)b
```




    array([[0, 1, 2, 3, 4, 5],       [0, 1, 2, 3, 4, 5],       [0, 1, 2, 3, 4, 5],       [0, 1, 2, 3, 4, 5]])



### Numpy二维数组之间的运算--向量


```python
a = np.array([[1,2,3],[4,5,6]])b = np.array([[4,5,6],[1,2,3]])
```

#### 向量与向量之间

加------add()  +

减------subtract()  -

乘法-----mulitply    *

除法-----divide   /

点乘----dot   


```python
np.add(a,b)
```




    array([[5, 7, 9],       [5, 7, 9]])




```python
np.subtract(a,b)
```




    array([[-3, -3, -3],       [ 3,  3,  3]])




```python
np.multiply(a,b)
```




    array([[ 4, 10, 18],       [ 4, 10, 18]])




```python
np.divide(a,b)
```




    array([[0.25, 0.4 , 0.5 ],       [4.  , 2.5 , 2.  ]])




```python
a = np.array([[1,2,3],[4,5,6]])b = np.array([4,5,6])np.dot(a,b)     
```




    array([32, 77])



#### 向量与标量之间

加  +

减  -

乘法  *   

取余  %

转置  T

矩阵的逆     inv


```python
a = np.array([[1,2,3],[4,5,6]])
```


```python
a + 1
```




    array([[2, 3, 4],       [5, 6, 7]])




```python
a  - 1
```




    array([[0, 1, 2],       [3, 4, 5]])




```python
a * 2
```




    array([[ 2,  4,  6],       [ 8, 10, 12]])




```python
a % 2
```




    array([[1, 0, 1],       [0, 1, 0]])




```python
a.T
```




    array([[1, 4],       [2, 5],       [3, 6]])




```python
import numpy as npimport numpy.linalg as lga = np.array([[1,2,3],[4,5,6],[7,8,9]])lg.inv(a)
```




    array([[ 3.15251974e+15, -6.30503948e+15,  3.15251974e+15],       [-6.30503948e+15,  1.26100790e+16, -6.30503948e+15],       [ 3.15251974e+15, -6.30503948e+15,  3.15251974e+15]])



### 数组的切片与索引


```python
import numpy as npa  = np.array([np.arange(9)])a
```




    array([[0, 1, 2, 3, 4, 5, 6, 7, 8]])




```python
a[3:6]
```




    array([], shape=(0, 9), dtype=int64)




```python
a[:7:2]
```




    array([[0, 1, 2, 3, 4, 5, 6, 7, 8]])




```python
a[::-1]
```




    array([[0, 1, 2, 3, 4, 5, 6, 7, 8]])




```python
a=np.array([[1,2,3],[4,3,2]])a[1][0] 
```




    4




```python
a[1,:2]   #获取第1维的前2个元素
```




    array([4, 3])



### 数组的堆叠

#### 改变数组的形状

**reshape() **

**ravel()  **

**flatten()  ** 

**shape()  **

**transpose()  **



```python
import numpy as npb = np.arange(24).reshape(2,3,4)b
```




    array([[[ 0,  1,  2,  3],        [ 4,  5,  6,  7],        [ 8,  9, 10, 11]],       [[12, 13, 14, 15],        [16, 17, 18, 19],        [20, 21, 22, 23]]])




```python
b.ravel()
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,       17, 18, 19, 20, 21, 22, 23])




```python
b.flatten()
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,       17, 18, 19, 20, 21, 22, 23])



#### 数组的堆叠

从深度看，数组既可以横向叠放，也可以竖向叠放。因此，我们我们对数组进行堆叠，Numpy数组对堆叠包含以下几个函数


```python
a = np.arange(9).reshape(3,3)a
```




    array([[0, 1, 2],       [3, 4, 5],       [6, 7, 8]])




```python
b = a * 2b
```




    array([[ 0,  2,  4],       [ 6,  8, 10],       [12, 14, 16]])




```python
np.hstack((a,b))
```




    array([[ 0,  1,  2,  0,  2,  4],       [ 3,  4,  5,  6,  8, 10],       [ 6,  7,  8, 12, 14, 16]])




```python
np.vstack((a,b))
```




    array([[ 0,  1,  2],       [ 3,  4,  5],       [ 6,  7,  8],       [ 0,  2,  4],       [ 6,  8, 10],       [12, 14, 16]])




```python
np.dstack((a,b))
```




    array([[[ 0,  0],        [ 1,  2],        [ 2,  4]],       [[ 3,  6],        [ 4,  8],        [ 5, 10]],       [[ 6, 12],        [ 7, 14],        [ 8, 16]]])



### Numpy的拆分


```python
a = np.arange(9).reshape(3,3)a
```




    array([[0, 1, 2],       [3, 4, 5],       [6, 7, 8]])




```python
np.hsplit(a,3)
```




    [array([[0],        [3],        [6]]), array([[1],        [4],        [7]]), array([[2],        [5],        [8]])]




```python
np.vsplit(a,3)
```




    [array([[0, 1, 2]]), array([[3, 4, 5]]), array([[6, 7, 8]])]



深度拆分。

深度拆分要求数组的秩大于等于3


```python
a = np.arange(27).reshape(3,3,3)a
```




    array([[[ 0,  1,  2],        [ 3,  4,  5],        [ 6,  7,  8]],       [[ 9, 10, 11],        [12, 13, 14],        [15, 16, 17]],       [[18, 19, 20],        [21, 22, 23],        [24, 25, 26]]])




```python
np.dsplit(a,3)
```




    [array([[[ 0],         [ 3],         [ 6]],         [[ 9],         [12],         [15]],         [[18],         [21],         [24]]]), array([[[ 1],         [ 4],         [ 7]],         [[10],         [13],         [16]],         [[19],         [22],         [25]]]), array([[[ 2],         [ 5],         [ 8]],         [[11],         [14],         [17]],         [[20],         [23],         [26]]])]



## Pandas初体验

### 了解数据处理对象---series

Pandas是为了解决数据分析任务而创建的，纳入了大量的库和标准数据模型，提供了高效地操作大型数据集所需的工具

#### Pandas中的数据结构

Series: 一维数组，类似于Python中的基本数据结构list，区别是Series只允许存储相同的数据类型，这样可以更有效的使用内存，提高运算效率。就像数据库中的列数据；

DataFrame: 二维的表格型数据结构。很多功能与R中的data.frame类似。可以将DataFrame理解为Series的容器；

Panel：三维的数组，可以理解为DataFrame的容器

Series是一个一维的类似的数组对象，包含一个数组的数据（任何NumPy的数据类型）和一个与数组关联的数据标签，被叫做索引 。最简单的Series是由一个数组的数据构成


```python
from pandas import Seriesdata = Series([3,-1,9,11])data
```




    0     31    -12     93    11dtype: int64



Series的交互式显示的字符串表示形式是索引在左边，值在右边。因为我们没有给数据指定索引，一个包含整数0到N-1这里N是数据的长度）的默认索引被创建。你可以分别的通过它的values和index属性来获取 Series的数组表示和索引对象


```python
data.values
```




    array([ 3, -1,  9, 11])




```python
data.index
```




    RangeIndex(start=0, stop=4, step=1)



通常，需要创建一个带有索引来确定每一个数据点的Series


```python
n = Series([1,-3,9,22],index=["a",'b','c','d'])n
```




    a     1b    -3c     9d    22dtype: int64



如果你有一些数据在一个Python字典中，你可以通过传递字典来从这些数据创建一个Series，只传递一个字典的时候，结果Series中的索引将是排序后的字典的键


```python
human = {"name":"wuhan","age":20,"identy":"student"}man  = Series(human)man
```




    name        wuhanage            20identy    studentdtype: object



### 了解数据处理对象----DataFrame

DataFrame是一个表格型的数据结构，是以一个或多个二维块存放的数据表格（层次化索引），DataFrame既有行索引还有列索引，它有一组有序的列，每列既可以是不同类型（数值、字符串、布尔型）的数据，或者可以看做由Series组成的字典


```python
from pandas import Series,DataFrameimport pandas as pddictionary = {'state':['0hio','0hio','0hio','Nevada','Nevada'],             'year':[2000,2001,2002,2001,2002],             'pop':[1.5,1.7,3.6,2.4,2.9]}frame = DataFrame(dictionary)frame
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>state</th>
      <th>year</th>
      <th>pop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0hio</td>
      <td>2000</td>
      <td>1.5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0hio</td>
      <td>2001</td>
      <td>1.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0hio</td>
      <td>2002</td>
      <td>3.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Nevada</td>
      <td>2001</td>
      <td>2.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Nevada</td>
      <td>2002</td>
      <td>2.9</td>
    </tr>
  </tbody>
</table>

</div>




```python
data  = {'周一':["上班"],        '周二':["上班"],        "周末":["休息"]}data_f = DataFrame(data)data_f
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>周一</th>
      <th>周二</th>
      <th>周末</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
  </tbody>
</table>

</div>



修改行名字


```python
data_f=DataFrame(data,index=['20岁','30岁','100岁'])data_f
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>周一</th>
      <th>周二</th>
      <th>周末</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
    <tr>
      <th>30岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
    <tr>
      <th>100岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
  </tbody>
</table>

</div>



添加/修改


```python
data_f["添加"] :['上班']data_f
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>周一</th>
      <th>周二</th>
      <th>周末</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
    <tr>
      <th>30岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
    <tr>
      <th>100岁</th>
      <td>上班</td>
      <td>上班</td>
      <td>休息</td>
    </tr>
  </tbody>
</table>

</div>



### 读取CSV格式数据

#### 读取CSV


```python
from pandas import Series,DataFrameimport pandas# Reading a csv into Pandas.# 如果数据集中有中文的话，最好在里面加上 encoding = 'gbk' ，以避免乱码问题。后面的导出数据的时候也一样。df = pd.read_csv('uk_rain_2014.csv', header=0)
```

我们从csv文件里导入了数据，并储存在DataFrame中。这一步非常简单，你只需要调用read_csv然后将文件的路径传进去就行了。header 关键字告诉Pandas哪些是数据的列名。如果没有列名的话就将它设定为 None

前5行，后5行


```python
df.head(5)
```


```python
df.tail(5)
```

总行数

len(df)

修改列名


```python
# Changing column labels.    df.columns = ['water_year','rain_octsep','outflow_octsep','rain_decfeb', 'outflow_decfeb', 'rain_junaug', 'outflow_junaug']
```

### 对数据进行排序

#### 对索引进行排序

Series用sort_index()按索引排序，sort_values()按值排序；

DataFrame也是用sort_index()和sort_values()


```python
a = Series(range(4),index=['c','b','d','a'])a
```




    c    0b    1d    2a    3dtype: int64




```python
a.sort_index()
```




    a    3b    1c    0d    2dtype: int64




```python
a.sort_values()
```




    c    0b    1d    2a    3dtype: int64




```python
b = DataFrame(np.arange(8).reshape(2,4),index=['one','two'],columns=['b','d','c','a'])b
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>b</th>
      <th>d</th>
      <th>c</th>
      <th>a</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>one</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>two</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
  </tbody>
</table>

</div>




```python
frame = DataFrame({'b':[4, 7, -3, 2], 'a':[0, 1, 0, 1]})frame.sort_index(by='b') #DataFrame必须传一个by参数表示要排序的列
```


    ---------------------------------------------------------------------------TypeError                                 Traceback (most recent call last)<ipython-input-72-fc7a0e2118b8> in <module>      1 frame = DataFrame({'b':[4, 7, -3, 2], 'a':[0, 1, 0, 1]})----> 2 frame.sort_index(by='b') #DataFrame必须传一个by参数表示要排序的列


    TypeError: sort_index() got an unexpected keyword argument 'by'


### 删除数据

#### 删除指定轴上的项


```python
 ser = Series([4.5,7.2,-5.3,3.6], index=['d','b','a','c']) ser.drop('c')
```




    d    4.5b    7.2a   -5.3dtype: float64




```python
df = DataFrame(np.arange(9).reshape(3,3), index=['a','c','d'], columns=['oh','te','ca'])df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>oh</th>
      <th>te</th>
      <th>ca</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>

</div>




```python
df.drop('a')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>oh</th>
      <th>te</th>
      <th>ca</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>

</div>



删除列


```python
df.drop('oh',axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>te</th>
      <th>ca</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>

</div>



### 算术运算


```python
df1 = DataFrame(np.arange(12).reshape((3,4)),columns=list('abcd'))df2 = DataFrame(np.arange(20).reshape((4,5)),columns=list('abcde'))df1+df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>d</th>
      <th>e</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>4.0</td>
      <td>6.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>9.0</td>
      <td>11.0</td>
      <td>13.0</td>
      <td>15.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>18.0</td>
      <td>20.0</td>
      <td>22.0</td>
      <td>24.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>

</div>



如果没有共同的元素，则用NaN代替。

也可指定默认的填入值


```python
df1 = DataFrame(np.arange(12).reshape((3,4)),columns=list('abcd'))df2 = DataFrame(np.arange(20).reshape((4,5)),columns=list('abcde'))df1.add(df2,fill_value=0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>d</th>
      <th>e</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>4.0</td>
      <td>6.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>9.0</td>
      <td>11.0</td>
      <td>13.0</td>
      <td>15.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>18.0</td>
      <td>20.0</td>
      <td>22.0</td>
      <td>24.0</td>
      <td>14.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>15.0</td>
      <td>16.0</td>
      <td>17.0</td>
      <td>18.0</td>
      <td>19.0</td>
    </tr>
  </tbody>
</table>

</div>



### 去重


```python
df1.duplicated()
```




    0    False1    False2    Falsedtype: bool




```python
df1.drop_duplicates()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>d</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8</td>
      <td>9</td>
      <td>10</td>
      <td>11</td>
    </tr>
  </tbody>
</table>

</div>



### 层次化索引


```python
from pandas  import Series,DataFrameimport pandasimport numpy as npdata = Series(np.random.randn(10), index = [['a', 'a', 'a', 'b', 'b', 'b', 'c', 'c', 'd', 'd' ],                                            [1,2,3,1,2,3,1,2,2,3]])data
```




    a  1   -1.780762   2    0.434031   3    1.421023b  1    0.898220   2   -0.523384   3    0.447893c  1    0.276676   2    0.095662d  2   -0.133373   3    1.269817dtype: float64



使得可以在轴上拥有多个索引级别


```python
data['b':'d']
```




    b  1    0.898220   2   -0.523384   3    0.447893c  1    0.276676   2    0.095662d  2   -0.133373   3    1.269817dtype: float64



#### 内层选取


```python
data[:,1]
```




    a   -1.780762b    0.898220c    0.276676dtype: float64



#### 数据重塑

将Series转化成DataFrame


```python
data.unstack()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }


    .dataframe tbody tr th {    vertical-align: top;}.dataframe thead th {    text-align: right;}

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>-1.780762</td>
      <td>0.434031</td>
      <td>1.421023</td>
    </tr>
    <tr>
      <th>b</th>
      <td>0.898220</td>
      <td>-0.523384</td>
      <td>0.447893</td>
    </tr>
    <tr>
      <th>c</th>
      <td>0.276676</td>
      <td>0.095662</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>d</th>
      <td>NaN</td>
      <td>-0.133373</td>
      <td>1.269817</td>
    </tr>
  </tbody>
</table>

</div>



## Python机器学习软件包Scikit-Learn的学习与使用

### 使用Scikit-learn导入数据集

scikit-learn 包括一些标准数据集，不需要从外部下载，可直接导入使用，比如与分类问题相关的Iris数据集和digits手写图像数据集，与回归问题相关的波士顿房价数据集


```python
 #加载并返回波士顿房价数据集（回归）load_boston([return_X_y])#加载并返回iris数据集（分类）load_iris([return_X_y])             #加载并返回糖尿病数据集（回归）load_diabetes([return_X_y])          #加载并返回数字数据集（分类）load_digits([n_class, return_X_y]) #加载并返回linnerud数据集（多分类）   load_linnerud([return_X_y])   
```

这些标准数据集采用类字典的对象格式存储,

比如.data表示原始数据，是一个(n_samples,n_features)二维数组，通过.shape可以得到二维数组大小，

.target表示存储数据类别即标签

利用datasets加载数据集digits作为示例


```python
from sklearn import datasetsdigits = datasets.load_digits()print(digits.data)print(digits.data.shape)print(digits.target)
```

    [[ 0.  0.  5. ...  0.  0.  0.] [ 0.  0.  0. ... 10.  0.  0.] [ 0.  0.  0. ... 16.  9.  0.] ... [ 0.  0.  1. ...  6.  0.  0.] [ 0.  0.  2. ... 12.  0.  0.] [ 0.  0. 10. ... 12.  1.  0.]](1797, 64)[0 1 2 ... 8 9 8]


### 数据预处理--标准化

原始数据存在的几个问题：不一致、重复、含噪声、维度高。数据挖掘中，数据预处理包含数据清洗、数据集成、数据变换和数据归约几种方法，在这里不过多叙述预处理方法细节。接下来将简单介绍，如何通过调用 sklearn 中的模块进行数据预处理。

sklearn.preprocessing 模块提供很多公共的方法，将原始不规整的数据转化为更适合分类器的具有代表性的数据。一般说来，使用标准化后的数据集训练学习模型具有更好的效果。

数据标准化的方法有很多种，常用的有“最小—最大标准化”、“Z-score标准化”等等。经过上述标准化处理，各属性值都处于同一个数量级别上，可以进行综合数据分析。

#### Z-score标准化

这种方法基于原始数据的均值（mean）和标准差（standard deviation）进行数据的标准化。将 A 的原始值 x 使用 Z-score 标准化到 x'。
Z-score 标准化方法适用于属性A的最大值和最小值未知的情况，或有超出取值范围的离群数据的情况，

其公式为：
新数据=（原数据-均值）/标准差

sklearn.preprocessing.scale函数，可以直接将给定数据进行标准化。


```python
from sklearn import preprocessingimport numpy as npx_train = np.array([[-1,1,2],                   [0,1,0],                   [2,0,-1]])x_scale = preprocessing.scale(x_train)x_scale
```




    array([[-1.06904497,  0.70710678,  1.33630621],       [-0.26726124,  0.70710678, -0.26726124],       [ 1.33630621, -1.41421356, -1.06904497]])




```python
#标准化处理后，数据的均值和方差print(x_scale.mean(axis=0))print(x_scale.std(axis=0))
```

    [7.40148683e-17 7.40148683e-17 0.00000000e+00][1. 1. 1.]


sklearn.preprocessing.StandardScaler类实现了 Transformer 接口，可以保存训练数据中的参数（均值 mean_、缩放比例 scale_），并能将其应用到测试数据的标准化转换中。


```python
scaler = preprocessing.StandardScaler().fit(x_train)scaler
```




    StandardScaler()




```python
scaler.mean_
```




    array([0.33333333, 0.66666667, 0.33333333])




```python
scaler.scale_
```




    array([1.24721913, 0.47140452, 1.24721913])




```python
scaler.transform(x_train)
```




    array([[-1.06904497,  0.70710678,  1.33630621],       [-0.26726124,  0.70710678, -0.26726124],       [ 1.33630621, -1.41421356, -1.06904497]])




```python
#将标准化转换器应用到新的测试数据：x_test = [[-1,0,1]]scaler.transform(x_test)
```




    array([[-1.06904497, -1.41421356,  0.53452248]])



#### min-max 标准化

min-max 标准化方法是对原始数据进行线性变换。设 minA 和 maxA 分别为属性 A 的最小值和最大值，将 A 的一个原始值 x 通过 min-max 标准化，映射成在区间[0,1]中的值 x'，

其公式为：
新数据=（原数据-极小值）/（极大值-极小值）

sklearn.preprocessing.MinMaxScaler将属性缩放到一个指定的最大和最小值（通常是1-0）之间。
MinMaxScaler 中可以通过设置参数feature_range=(min, max)指定最大最小区间。其具体的计算公式为

X_std = (X - X.min(axis=0)) / (X.max(axis=0) - X.min(axis=0))
X_scaled = X_std * (max - min) + min


```python
X_train = np.array([[1,-1,2],                   [2,0,0],                   [0,1,-1]])min_max_scale = preprocessing.MinMaxScaler()X_train_min_max =  min_max_scale.fit_transform(X_train)X_train_min_max
```




    array([[0.5       , 0.        , 1.        ],       [1.        , 0.5       , 0.33333333],       [0.        , 1.        , 0.        ]])




```python
#将标准化缩放，应用到新的测试数据X_test = [[-3 ,-1 ,4]]X_test_min_max = min_max_scale.transform(X_test)X_test_min_max
```




    array([[-1.5       ,  0.        ,  1.66666667]])



### 文本特征数据的提取

对于文本数据，我们无法直接将原始文本作为训练数据，需通过特征提取将其转化为特征向量。本关卡，将学习提取文本数据特征的基本操

文本分析是机器学习算法的一个主要应用领域。文本分析的原始数据无法直接输入算法，因为大部分算法期望的输入，是固定长度的数值特征向量，而不是可变长的文本数据。
为了解决这个问题，sklearn 提供了一些实用工具，用最常见的方式从文本内容中抽取数值特征。比如说：

分词（tokenizing），对句子分词后，为每一个词（token）分配的一个整型 id，通常用空格和标点符号作为分词的分割符；
计数（counting），计算某个词在文本中的出现频率；
归一化权重(nomalizating and weighting)， 降低在大多数样本/文档中都出现的词的权重。
在文本特征提取中，特征和样本的定义如下：

将每个词出现的频率作为特征；

将给定文档中所有词的出现频率所构成的向量看做一个样本。

因此，整个语料库可以看做一个矩阵，矩阵的每行代表一个文档，每列代表一个分词。我们将文档集合转化为数值特征向量的过程称为向量化。这一整套策略被称为词袋模型，用词频描述文档，完全忽略词在文档中出现的相对位置信息。



#### sklearn 中提取数据特征值的方法：

CountVectorizer模块实现了分词和计数，该方法包含许多参数，


```python
from sklearn.feature_extraction.text import CountVectorizervectorizer = CountVectorizer()dir(vectorizer)
```




    ['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setstate__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', '_char_ngrams', '_char_wb_ngrams', '_check_n_features', '_check_stop_words_consistency', '_check_vocabulary', '_count_vocab', '_get_param_names', '_get_tags', '_limit_features', '_more_tags', '_repr_html_', '_repr_html_inner', '_repr_mimebundle_', '_sort_features', '_validate_data', '_validate_params', '_validate_vocabulary', '_warn_for_unused_params', '_white_spaces', '_word_ngrams', 'analyzer', 'binary', 'build_analyzer', 'build_preprocessor', 'build_tokenizer', 'decode', 'decode_error', 'dtype', 'encoding', 'fit', 'fit_transform', 'get_feature_names', 'get_params', 'get_stop_words', 'input', 'inverse_transform', 'lowercase', 'max_df', 'max_features', 'min_df', 'ngram_range', 'preprocessor', 'set_params', 'stop_words', 'strip_accents', 'token_pattern', 'tokenizer', 'transform', 'vocabulary']



> 常见参数：

    input : 指定输入格式；tokenizer : 指定分词器；stop_words : 指定停止词，比如当设置 stop_words="english"时，将会使用内建的英语停用词列表；max_df : 设置最大词频，若为浮点数且范围在[0,1]之间，则表示频率，若为整数则表示频数；min_df : 设置最小词频；max_features: 设置最大的特征数量；vocabulary: 指定语料库，即指定词和特征索引间的映射关系表。

属性:

vocabulary_ : 字典类型，返回词和特征索引间的映射关系表
得到到词汇映射表




```python
#得到词汇映射表vocab = vectorizer.vocabulary_#字典结构，返回特征值‘document’对应的下标索引vectorizer.vocabulary_.get('document')
```

stop_words_ : set 集合，停止词集合。

方法:

fit(raw_documents[, y]) : 从原文本数据得到词汇-特征索引间的映射关系；

transform(raw_documents) :将原文本集合转换为特征矩阵；

fit_transform(raw_documents[, y]): 结合 fit 和 transform 方法，返回特征矩阵，如下图所示：


```python
lis  = ['this is me',       'this is you']x = vectorizer.fit_transform(lis)x
```




    <2x4 sparse matrix of type '<class 'numpy.int64'>'	with 6 stored elements in Compressed Sparse Row format>



build_analyzer():返回预处理和分词的引用；
下图表示对“This is a text document to analyze.”进行分词并验证结果。


```python
analyz = vectorizer.build_analyzer()analyz('this is a text to analyz') == ('this','is','a','text','to','analyz')
```




    False



get_feature_names():返回特征索引id对应的特征名字（下标对应的某个词）


```python
vectorizer.get_feature_names() == (['this','is','a','text'])
```




    False




```python
x.toarray()
```




    array([[1, 1, 1, 0],       [1, 0, 1, 1]])




```python
#将向量化转换器应用到新的测试数据vectorizer.transform(['something is good']).toarray()
```




    array([[1, 0, 0, 0]])



> transform函数的返回结果是一个矩阵（sparse matrix），为了更好的表示数据，采用toarray()将数据转化为 numpy 数组

在文本语料库中，一些词非常常见（例如，英文中的“the”，“a”，“is”），但是有用信息含量不高。如果我们将词频直接输入分类器，那些频繁出现的词会掩盖那些很少出现，但是更有意义的词，将达不到比较好的预期效果。为了重新计算特征的计数权重，通常都会进行 TFIDF 转换。
TFIDF 的主要思想是：如果某个词或短语在一篇文章中出现的频率高，并且在其他文章中很少出现，则认为此词或者短语具有很好的类别区分能力，适合用来分类。TFIDF 实际上是：TF * IDF，TF 词频(Term Frequency)，IDF 反文档频率(Inverse Document Frequency)。TF 词频(Term Frequency)指的是某一个给定的词语在该文件中出现的次数。IDF 反文档频率(Inverse Document Frequency)是指如果包含词条的文档越少，IDF 越大，则说明词条具有很好的类别区分能力。

sklearn 中的 TfidfVectorizer 模块，实现了 TFIDF 思想。该模块的参数、属性及方法与 CountVectorizer 类似，可参考 CountVectorizer 的调用方式。

### 使用scikit-learn分类器SVM对digits数据分类

在 scikit-learn 中，对于分类问题的估计器是一个实现了fit(X, y) 和predict(T)方法的 Python 对象。估计器的实例很多，例如实现了支持向量分类的类sklearn.svm.svc。估计器的结构可以通过初始化模型时设置的参数决定，但目前，我们将估计器看做一个黑盒子，先不关心具体的参数设置。
digits 数据集中包含大量的数字图片，如下图所示，我们希望给定其中的一张图片，能识别图中代表的数字，这是一个分类问题，数字 0…9 代表十个分类，目标是希望能正确估计图中样本属于哪一个数字类别。

digits 的原始图像采用一个(8,8)的二维数组表示


```python
from sklearn import datasetsdigits = datasets.load_digits()digits.images[0]
```




    array([[ 0.,  0.,  5., 13.,  9.,  1.,  0.,  0.],       [ 0.,  0., 13., 15., 10., 15.,  5.,  0.],       [ 0.,  3., 15.,  2.,  0., 11.,  8.,  0.],       [ 0.,  4., 12.,  0.,  0.,  8.,  8.,  0.],       [ 0.,  5.,  8.,  0.,  0.,  9.,  8.,  0.],       [ 0.,  4., 11.,  0.,  1., 12.,  7.,  0.],       [ 0.,  2., 14.,  5., 10., 12.,  0.,  0.],       [ 0.,  0.,  6., 13., 10.,  0.,  0.,  0.]])




```python
digits.data
```




    array([[ 0.,  0.,  5., ...,  0.,  0.,  0.],       [ 0.,  0.,  0., ..., 10.,  0.,  0.],       [ 0.,  0.,  0., ..., 16.,  9.,  0.],       ...,       [ 0.,  0.,  1., ...,  6.,  0.,  0.],       [ 0.,  0.,  2., ..., 12.,  0.,  0.],       [ 0.,  0., 10., ..., 12.,  1.,  0.]])




```python
digits.target
```




    array([0, 1, 2, ..., 8, 9, 8])




```python
digits.data.shape
```




    (1797, 64)




```python
import matplotlib.pyplot as plt# 导入数据集，分类器相关包from sklearn import datasets, svm, metrics# 导入digits数据集digits = datasets.load_digits()n_samples = len(digits.data)data = digits.data# 使用前一半的数据集作为训练数据，后一半数据集作为测试数据train_data,train_target = data[:n_samples // 2],digits.target[:n_samples // 2]test_data,test_target = data[n_samples // 2:],digits.target[n_samples // 2:]def createModelandPredict():    '''    创建分类模型并对测试数据预测    返回值：    predicted - 测试数据预测分类值    '''    predicted = None    #   请在此添加实现代码   #    #********** Begin *********#    classifier = svm.SVC()    classifier.fit(train_data,train_target)    predicted = classifier.predict(test_data)        #********** End **********#    return predicted
```

### 模型持久化

当数据量很大的时候，训练一个模型需要消耗很大的时间成本，每次都重新训练模型预测，是非常冗余且没有必要的。我们可以将训练模型存储下来，每当要预测新数据的时候，只需加载该模型。
训练模型的持久化需要调用 Python 的内建模块pickle，pickle可以用来将 Python 对象转化为字节流存储至磁盘，也可以逆向操作将磁盘上的字节流恢复为 Python 对象


```python
#将对象obj写到文件file中pickle.dump(obj, file[, protocol])#从文件file读取数据流并将其重建返回原始对象pickle.load(file)
```


```python
# 导入数据集，分类器相关包from sklearn import datasets, svm, metricsimport pickle# 导入digits数据集digits = datasets.load_digits()n_samples = len(digits.data)data = digits.data# 使用前一半的数据集作为训练数据，后一半数据集作为测试数据train_data,train_target = data[:n_samples // 2],digits.target[:n_samples // 2]test_data,test_target = data[n_samples // 2:],digits.target[n_samples // 2:]def createModel():    classifier = svm.SVC()    classifier.fit(train_data,train_target)    return classifierlocal_file = 'dumpfile'def dumpModel():    '''    存储分类模型    '''    clf = createModel()    # 请在此处补全模型存储语句 #    #********** Begin *********#    f_model = open(local_file, 'wb')    pickle.dump(clf, f_model)    #********** End **********#def loadModel():    '''    加载模型，并使用模型对测试数据进行预测，返回预测值    返回值：    predicted - 模型预测值    '''    predicted = None    # 请在此处补全模型加载语句，并对预测数据分类返回预测值#    #********** Begin *********#    fw = open(local_file, 'rb')    classifier = pickle.loads(fw.read())    predicted = classifier.predict(test_data)    #********** End **********#    return predicted
```

### 模型评估--量化预测效果

sklearn 中有三种不同的 API 来评估模型的预测质量：

Estimator score method ：在评估器（比如一个分类模型）中有score函数提供默认的评估标准，比如支持向量机sklearn.svm.SVC中的score函数，通过计算预测准确率来评估模型


Scoring parameter：cross-validation的模型评估工具比如model_selection.GridSearchCV，可通过设置类的参数scoring来指定评估模型


Metric functions: metrics 模块实现了一些函数，用来评估预测误差，并且针对不同的目标（分类、回归或聚类问题等）有不同的评估类，


前两种评估方法可以在具体的评估器和交叉验证工具中设置，在这里不过多讨论。我们主要关注 metrics 模块，旨在让同学们学会如何使用常见的指标对分类结果分析评价。



#### accuracy_score(y_true, y_pred, normalize=True, sample_weight=None)* 

计算分类精度，示例如下图所示：


```python
import numpy as npfrom sklearn.metrics import accuracy_scorex_date = [0,2,1,3]x_pre = [0,1,2,3]accuracy_score(x_date,x_pre)
```




    0.5




```python
#其中 normalize=True时返回正确分类的比例，设为 False 时返回正确分类的样本个数print(accuracy_score(x_date,x_pre,normalize=True))print(accuracy_score(x_date,x_pre,normalize=False))
```

    0.52


#### recall_score(y_true, y_pred, labels=None, pos_label=1, average=’binary’, sample_weight=None)

返回模型分类的召回率

参数：
y_true：实际值；
y_pred：预测值；
pos_label： 仅当 average=’binary’ 时该参数才有效，即仅对二分类有效。参数的值为正类标签或负类标签，指定计算的是正类还是负类；
average：当涉及到二分类/多分类/多标签等不同的问题时，可以通过设置该参数指定计算方式，可取的值包括[None, ‘binary’ (default), ‘micro’, ‘macro’, ‘samples’, ‘weighted’]。  

f1_score、precision_score 的使用方式和 recall_score类似


```python
from sklearn.metrics import recall_scorerecall_score(x_date,x_pre,average="macro")
```




    0.5



#### confusion_matrix

计算混淆矩阵


```python
from sklearn.metrics import confusion_matrix
confusion_matrix(x_date,x_pre)
```




    array([[1, 0, 0, 0],
           [0, 0, 1, 0],
           [0, 1, 0, 0],
           [0, 0, 0, 1]])



#### classification_report 

该函数建立了一份文本报告展示主要的分类度量指标，比如准确率、召回率、f 值等


```python
from sklearn.metrics import classification_report
classname = ['0','1','2']
classification_report(x_date,x_pre,target_names=classname)
```

precision_recall_fscore_support 
为每个类别计算准确率、召回率、f 值、support 值


```python
from sklearn.metrics import precision_recall_fscore_support
x_true = ['pig','dog','pig','cat','cat','dog']
x_pre = ['cat','cat','dog','dog','pig','pig']
precision_recall_fscore_support(x_true,x_pre,average='micro')
```




    (0.0, 0.0, 0.0, None)




```python
from sklearn.metrics import accuracy_score,precision_score,f1_score,precision_recall_fscore_support
from sklearn.svm import LinearSVC,SVC
def bin_evaluation(X_train, y_train, X_test, y_test):
    '''
    评估二分类模型
    :param X_train: 训练数据集
    :param y_train: 训练集类别
    :param X_test: 测试数据集
    :param y_test: 测试集实际类别
    :return:
    correct_num - 正确分类的样本个数
    prec - 正类的准确率
    recall - 正类的召回率
    f_score - 正类的f值
    '''
    classifier = LinearSVC()
    correct_num, prec, recall, fscore = None, None, None, None
    #   请在此添加实现代码   #
    # ********** Begin *********#
    classifier.fit(X_train, y_train)
    y_pred = classifier.predict(X_test)

    correct_num = accuracy_score(y_test, y_pred, normalize=False)
    prec, recall, fscore, support = precision_recall_fscore_support(y_test, y_pred, average="binary", pos_label=1)

    return correct_num, prec, recall, fscore
    # ********** End **********#
def multi_evaluation(X_train,y_train,X_test,y_test):
    '''
    评估多分类模型
    :param X_train: 训练数据集
    :param y_train: 训练集类别
    :param X_test: 测试数据集
    :param y_test: 测试集实际类别
    :return:
    acc - 模型的精度
    prec - 准确率
    f_score - f值
    '''
    #初始化
    acc,prec,f_score = None,None,None
    classifier = SVC(kernel='linear')
    #   请在此添加实现代码   #
    # ********** Begin *********#
    classifier.fit(X_train, y_train)
    y_pred = classifier.predict(X_test)

    acc = accuracy_score(y_test, y_pred)
    prec, zhaohui, f_score, sp_score = precision_recall_fscore_support(y_test, y_pred, average='macro')

    return acc,prec,f_score
    # ********** End **********#

```


```python

```
