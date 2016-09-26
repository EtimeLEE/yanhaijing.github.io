---
layout: post
title: 重拾编程乐趣——我的Python笔记
category : program
tagline: "原创"
tags : [program]
keywords: [python, note]
description: 本文是《父与子的编程之旅：与小卡特一起学Python》的读书笔记，同时也是对学习python的笔记。
---
{% include JB/setup %}

早就想学学python了，但是一直没有勇气，一个偶然的机会，感谢图灵教育送了我一本《[父与子的编程之旅：与小卡特一起学Python][2]》，让我有激情、有动力学下去。

而我也很争气，很神奇的读完了这本书，要知道我现在很少读web相关外的技术书籍的，我给这本书的评价是5星，很棒的一本入门书，浅显易懂，非常适合新手来阅读，而且这不是一本讲python的书，而是一本讲编程的书。

感谢这本书，感谢python让我重新找回了编程的乐趣，终于又有了那种刚刚学习C语言时候的感觉了，所以我决定写下这篇文章，算是我的读书笔记吧，也是给自己做个备忘，主要是对这本书和python的总结。

![]({{BLOG_IMG}}295.jpg)

正文从这里开始，下面的内容都会按照书的目录结构来进行记录。

## 出发吧

### 安装python
学习[python][1]的第一步是安装python，可以到python的[官网下载](https://www.python.org/downloads/)，这里有很多版本，选择合适的版本和平台下载即可

我选择是2.x，我下载时最新的版本是2.7.12，windows平台的安装就是一路下一步即可安装好。

### 交互模式
在开始菜单搜索或找到python安装目录，打开IDLE(Python GUI)，即进入了python的交互模式，

![]({{BLOG_IMG}}296.png)

交互模式的意思就是，你可以输入一行代码，然后按下回车，python会立马告诉你执行结果，这个特别好用。

    print "Hello World"

上面代码的执行结果就是打印出Hellow World，print是python的输出语句。

### 第一个程序
打开菜单->File->New File（ctrl + N），就可以进入文本编辑模式，这里可以输入多行代码，比如键入如下代码：

    print "Hello World";
    print 22 + 10;

然后保存到某个目录，名字为xxx.py，菜单->Run->Run Module（F5），即可执行上面的代码。

## 记住内存和变量
每个程序都是由下面三个部分组成：

- 输入（input）
- 处理输入（process）
- 输出（ouput）

### 名字
在python中声明变量像下面这样，python中的变量都类似于引用，也是没有类型的。

    num = 123;
    str = "123";

## 基本数学运算
python可以完成基本的数学运算，当初python设计出来就是为了完成数学运算。

### 四大基本运算
python可以完成四大基础运算，如下所示：

    print 3 + 2 # 4
    print 3 - 2 # 1
    print 3 * 2 # 6

    print 3 / 2 # 1
    print 3.0 / 2 # 1.5

在前面的`3 + 2`中，3 和 2称为操作数，+ 称为操作符。

python的运算顺序和数学中一样，乘除高于加减，如果要改变运算顺序，和数学中一样的，需要添加括号。

    print 3 + 1 * 2 # 6
    print (3 + 1) * 2 # 8 
    
### 指数和求余数
在python中指数可以像下面这样表示

    print 3 ** 5 # 3 * 3 * 3 * 3 * 3 = 243

求余数使用%，像下面这样，注意和除法区分开

    print 7 % 2 # 1
    print 7 / 2 # 3

### 自增和自减
python中没有想c++中的自增和自减（i++），要实现一个数的自增的像下面这样

    num = 2
    num += 1 # 3
    num -= 1 # 2

上面的代码和下面的代码效果是一样的

    num = 2
    num = num + 1 # 3
    num = num - 1 # 2

## 数据的类型
python中的变量虽然没有类型，但是值是有类型的。

### 改变类型
可以通过下面的函数来改变数据类型

- float() 从一个字符串或整数创建浮点数
- int() 从一个字符串或浮点数创建一个新的整数
- str() 从一个书或其他任何类型创建一个新的字符串

三个函数都会返回一个新的值，而不会改变原来的值，因为值是不可变的

    a = 24
    b = float(a) # 24.0

    c = 38.0
    d = int(c) # 38

### 类型检查
python中的变量是没有类型，那么如何检查一个变量当前的值是什么类型的呢？答案就是type函数。

    a = 24
    type(a) # <type 'int'>

    b = 24.0
    type(b) # <type 'float'>

    c = 'str'
    type(c) # <type 'str'>

## 输入
对一个程序来说最重要的一点就是输入了，如果电脑不能响应输入，那么就一点用处都没有了。

### raw_input
raw_input函数可以从用户哪里得到一个字符串
    
    print "请输入："
    some = raw_input();
    print "你的输入是：", some

上面的程序会输出你输入的任何字符

raw_input还可以接受一个参数，这个参数会被作为输出，上面的程序可以简化为下面这样

    some = raw_input("请输入：")
    print "你的输入是：", some

### print
print用来给打印输出，简单点说就是向控制台打印一些东西

    print "yan"
    print "yan"
    print "yan"

上面的三条语句会得到下面的输出

    yan
    yan
    yan

如果想在同一行打印的话可以在结尾加上逗号

    print "yan",
    print "yan",
    print "yan"

上面的语句会得到下面的输出

    yan yan yan

中间会有一个空格，print还支持多个参数，中间用逗号分隔

    print "yan", "yan", "yan"

上面的语句会得到下面的输出，中间也有一个空格

    yan yan yan

### 来自互联网的输入
可以python的内置库，可以获得从互联网的而输入，下面的代码可以输出我的博客内容

    import urllib2
    file = urllib2.urlopen("http://yanhaijing.com")
    msg = file.read()
    print msg

## 判断在判断
每次程序执行都输出一样的东西没什么意思，需要有判断分支才有意思。

### 测试，测试
人之所以有智能是因为人能够思考，面对选择是能做出选择，那么如何让计算机也能够做出选择呢？那就是测试，我们需要做一些测试，然后决定接下来做什么。这些测试可能包括如下问题：

- 这两个东西相等吗？
- 其中一个是不是小于另一个？
- 其中一个是不是大于另一个？

完成测试并更根据结果做出测试称之为分支，在python中使用if来进行测试：

    if a == 1

python中的代码块比较奇葩，不是靠大括号而是缩进来确定范围的，声明一个代码块时就加一个冒号，就像下面这样：

    if a == 1:
        print "a等于1"
        print "代码块"
    print "这里不是代码块了"

python中的elseif和else像下面这样：

    if a == 1:
        print "a等于1"
    elif a == 2:
        print "a等于2"
    else:
        print "a等于其他值"

### 比较操作符
python中的比较操作符不只有等于还有其他，比如大于小于等，完整的列表如下

- == （等于）
- < （小于）
- > （大于）
- <= （小于等于）
- >= （大于等于）
- != （不等于）

### 逻辑运算符
python中也可以表达逻辑演算中的与 或 非，分别用下面的符号表示

- and
- or
- not

逻辑运算符的用例如下

    if a != 1 and a != 2:
        print "a不等于1和2"

## 转圈圈
来说说循环，循环分为两种，计数循环和条件循环。

## 计数循环
python中的计数循环使用for in，语法如下所示，和c语言有很大差别

    for looper in [1, 2, 3, 4]:
        print looper

`[1, 2, 3, 4]`是列表，python中类似数组的东西，如果循环次数很多，可以用range来代替

    for looper in range(1, 5):
        print looper

range还可以之传入一个参数，比如`range(5)`等同于 `range(0, 5)`

如果改变循环的步长，可以传入第三个参数，`range(0, 6, 2)`等同于 `[0, 2, 4]`，其中2就是步长

步长还可以是负数，`range(6, 0, -2)`，等同于`[6, 4, 2]`

## 条件循环
条件循环的意思就是判断某个条件是否为真，如果为真就一直循环下去，使用while关键字

    while 1 == 1:
        print "永远也不会停下来"

### 跳出循环
跳出循环可以使用break和continue，分别是退出循环和退出本次循环。

## 全是为了你——注释
对于程序而言注释必不可少，python的注释和类c语言不一样，是使用#号，#号后面的都被当作注释，像下面这样

    # 我是注释我是注释
    print 213 # 行末注释

python中没有多行注释，只能用单行注视模拟多行注释，像下面这样

    # ***********
    # 多行注释
    # 多行注释
    # ***********

## 收集起来——列表和字典
python中存取数据有两种类型的东西，一种叫做列表，一种叫做字典。

### 列表
python中的列表和数组很像，创建列表的语法如下所示：

    list = [1, 2, 3, 4]
    print list[0] # 1

可以用append向列表添加一个元素

    list = []
    list.append(1)
    print list # 1

### 列表分片
python中想从列表中获取列表片段，需要用到分片(slicing)

    list = ['a', 'b', 'c', 'd']
    print list[1:3]

    >>> ['b', 'c'] 

分片的语法可以简写，可以省略冒号前后的数字

    list = [1, 2, 3, 4, 5]

    print list[:]
    >>> [1, 2, 3, 4, 5]

    print list[3:]
    >>> [4, 5]
    
    print list[:3]
    >>> [1, 2, 3]

需要注意分片会返回一个新的列表，不会修改原列表。

### in关键字
要查找摸个元素是否在列表中，可以使用in

    list = ['a']

    print 'a' in list
    >>> True

### del关键字
del 从列表删除指定位置元素

    list = ['a', 'b', 'c']
    del list[0]
    print list
    >>> ['b', 'c']

### 列表方法
列表有很多方法，上面的append就是其中之一

- append
- extend
- insert
- remove
- pop 
- index
- sort
- reverse
- sorted

append用来在列表末尾添加一个元素

    list = [1]
    list.append(2)
    print list
    >>> [1, 2]

extend在列表末尾添加多个元素

    list = [1]
    list.extend([2, 3])
    print list
    >>> [1, 2, 3]

insert在指定位置插入元素

    list = [1, 2, 3]
    list.insert(1, 'a')
    print list
    >>> [1, 'a', 2, 3]

remove从列表中删除指定元素，如果删除的元素不在列表中会报错，可以和in关键字配合使用

    list = [1, 2, 3]
    list.remove(2)
    print list
    >>> [1, 3]

**注意：**和del区分，del用来删除指定的索引位置元素

pop去除列表中最后一个元素

    list = [1, 2, 3]
    a = list.pop()
    print a
    print list
    >>> 3
    >>> [1, 2]

index查找指定元素在列表中的索引，如果删除的元素不在列表中会报错，可以和in关键字配合使用

    list = [1, 2, 3]
    print list.index(3)
    >>> 2

**注意：**和in区分开，in会返回布尔值，index会返回索引

sort用来给列表排序

    list = [4, 2, 1]
    list.sort()
    print list
    >>> [1, 2, 4] 

如果想倒叙排列列表，可以给sort传一个参数

    list = [1, 2, 3]
    list.sort(reverse = True)
    print list
    >>> [3, 2, 1]

**注意：**sort会修改原来的列表，而不是创建一个新的列表，所以下面的操作不正确

    print list.sort() # 不正确的做法
    >>> None
    
    list.sort() # 需要分两步
    print list

reverse翻转列表，逆序排序数组还可以用这个

    list = [1, 2, 3]
    list.reverse()
    print list
    >>> [3, 2, 1]

sorted输一个系统函数，而不是数组函数，可以得到一个列表的有序副本，而不会影响原来的列表

    list = [3, 2, 1]
    nlist = sorted(list)
    print list
    print nlist
    >>> [3, 2, 1]
    >>> [1, 2, 3]

### 循环列表
列表可用for循环来遍历

    for i in [1, 2, 3]:
        print i
    >>> 1
    >>> 2
    >>> 3

### 不可变的列表
pythton中的列表是可变类型，python中有一种不可变的列表——元组，元组的语法如下

    tuple = (1, 2, 3) # 不可增删改

### 字典
python中的另一个种集合类型就是字典，类似其他语言中的关联数组或哈希表，分为键和值，通过键来存取值。

    phoneNumbers = {'yan': 133}
    print phoneNumbers['yan']
    >>> 133

    phoneNumbers['hai'] = 666;
    print phoneNumbers['hai']
    >>> 666

### 字典方法
字典也有一些方法

- keys
- values
- clear

keys方法可以列出字典总的全部键值

    dic = {'yan': 1, 'hai': 2}
    print dic.keys()
    >>> ['hai', 'yan']

values方法返回字典中的全部值
    
    dic = {'yan': 1, 'hai': 2}
    print dic.values()
    >>> [2, 1]

如果需要字典返回有序的键值，可以对返回的键值列表进行排序

clear用来删除字典中的而所有条目

    dic = {'yan': 1, 'hai': 2}
    dic.clear()
    print dic
    >>> {}

### del & in
del用来删除字典中的数据

    dic = {'yan': 1}
    del dic['yan']
    print dic
    >>> {}

检查某个关键字是否在字典中使用in

    dic = {'yan', 1}
    print 'yan' in dic
    >>> True

## 函数
当程序变大以后就需要一些方法来把程序分解成更小的部分，在python中主要有三种方法：

- 函数——就像代码的积木，可以反复的使用
- 对象——把程序中的各个部分描述为自包含的单元
- 模块——包含程序各部分的独立文件

创建一个函数需要使用def关键字

    def hello():
        print 'hello world'
    
    hello()
    >>> 'hello world'

函数可以有多个参数，中间用逗号分隔

    def hello(who):
        print 'hello', who
    hello()
    >>> hello yan

函数可以有返回值

    def add(x, y):
        return x + y

    add(1, 2)
    >>> 3

函数内部的变量都是局部变量，在函数外部不能访问

    def test():
    x = 1
    print x

    x = 10
    print x
    test()
    >>> 10
    >>> 1

在函数中可以访问全局变量，但不可修改，修改会创建一个局部变量

    def test2():
        y = 10
        print y

    y = 1
    test2()
    print y
    >>> 10
    >>> 1

在函数内部想强制访问全局变量，需要使用global

    def test3():
        global z
        z = 10
        print z

    z = 1
    test3()
    print z
    >>> 1
    >>> 10
    >>> 10

## 对象
对象可以把函数和数据收集在一起。对象可以包含属性和动作。

举个例子就是球，可以操作一个球，踢球，捡球，这些操作成为动作；球的颜色，大小称为球的属性。

python中称为对象的属性和方法。

### 创建对象
python中创建对象分为两步，第一步是创建对象的描述——类；第二步使用类来创建一个真正的对象。
    
    # 定义对象描述
    # __init__ 初始化对象方法
    # setColor 对象的方法

    class Ball:
        def __init__(self, color):
            self.color = color

        def setColor(self, color):
            self.color = color
    
    # 实例化对象
    ball = Ball('red');
    print ball.color

    ball.setColor('green')
    print ball.color

    # python中的对象可动态添加属性，这一点和java不一样
    ball.size = 'big'

    >>> red
    >>> green

### “魔法”方法
python中对象有一些魔法方法，上面的__init__就是，还有一个魔法方法是__str__，可以自定义对象的打印文本

    class Ball:
        def __str__():
            return 'yanhaijing.com'

    ball = Ball()
    print ball

    >>> yanhaijing.com

### self
python的对象方法调用时，的第一个参数表示调用的对象，self是约定俗成的做法，不是必须的。

### 隐藏数据
python也不支持私有的属性，这一点和js一样。

### 继承
在面向对象编程中，类可以从其他类继承属性和方法。

    class People:
        __init__(self, name):
            self.name = name

        talk():
            # pass作为占位符，可以表示为空函数
            pass
    
    # 继承People
    class Teacher(People):
        __init__(self, name):
            # 调用父类方法
            People.__init__(self, name)

## 模块
如果一个东西可以由几部分组成，我们就可以说这个东西是模块化的。乐高积木是最直观的例子了。

python中每个文件都是一个模块，模块意味着分治，可以把一个复杂的系统拆分成由简单的部分组成，这在大型程序中是非常有意义的。

模块是更高维度的抽象，可以把一组功能类似的函数，都放到一个模块中，一个复杂的模块也可以由更多简单的模块组成。

### 创建模块
模块就是一个文件，文件中的函数，变量都可以被别的模块引用，也就是说模块的一切的公开的

    # module1.py
    qiu = 1
    def hello():
        return 'hello'

上面定义了一个模块，有一个公开的属性qiu和一个公开的函数hello。

### 使用模块
在其他文件中可以用import关键字引用模块。

    import module1

    print module1.qiu
    print module1.hello()

    >>> 1
    >>> hello

还可以换一种写法

    from module1 import hello

    print hello()

    >>> hello

### 标准模块
python中内置了很多系统函数，要使用这些函数需要引用相应的模块，比如：

- time
- 随机数

time模块能够获取你的计算机时钟的信息，其中比较常用的就是sleep可以用来让程序暂停一会

    import time
    time.sleep(1)

random模块用于生成随机数

    import random

    print random.randint(0, 100) # 1-100之间随机数
    print random.random() # 0-1之间随机数
    >>> 4
    >>> 0.5456454545

## 打印格式化与字符串
这一章讲了如何打印出格式化的内容。

### 换行
可以在字符串中插入换行

    print "hello \nworld"
    
    >>> hello
    >>> world

### 水平间隔——制表符
看了这本书我才知道制表符还有这个功能，一个制表符会占据8个字符的间隔，但是会和前面的字符串合并

    print 'aaa\txyz'
    print 'aaaa\txyz'
    print 'aaaaa\txyz'
    
    >>> aaa     xyz
    >>> aaaa    xyz
    >>> aaaaaa  xyz

### 字符串插入变量
python中在字符串中插入变量称为格式化字符串，使用百分号(%)。

    str = '3'
    print '1%s3' % str

    >>> 123

%s表示插入字符串，还可以用%i用来表示整数，%f表示浮点数，都成为格式化字符串，用来指示如何显示 变量。

### 数字格式化
数字格式化可能是最复杂的部分了

%d和%i用来格式化整数，如果传入的是小数，则会进行截断

    number = 12.55

    print '%i' % numver
    print '%d' % numver

    >>> 12
    >>> 12

%f或%F用来格式化浮点数

    number = 12.1234

    print '%f' % number # 默认显示六位小数
    >>> 12.123400

    print '%.2f' # 显示两位小数，末尾四舍五入
    >>> 12.12

    print '%+f' % number #强制显示证号
    >>> +12.123400

    # 如果希望正负数的列表对齐，但是整数前没有正号，可使用空格
    
    number1 = -98.12
    number = 98.12
    print '% .2f' % number1
    print '% .2f' % number2

    >>> -98.12
    >>>  98.12

%e和%E用来格式化E记法的数字

    number = 12.1234
    print '%e' % number
    >>> 1.212340e+01

    print '%.2e'
    >>>> 1.2e+01


%g和%G用来自动表示为浮点数或E记法

    number1 = 12
    number2 = 1234567890

    print '%g' % number1
    print '%g' % number2

    >>> 12
    >>> 1.23456e+09

如果有多个格式化的字符串，需要使用元组

    n1 = 1
    n2 = 2

    print '%i-%i' % (n1, n2)

    >>> 1-2

还可以把格式化的字符串赋值给变量

    str = '%.2f' % 12.123

    print str
    >>> 12.12

### 格式化新方法
python2.6中引入了格式化的新方法，format函数

    print '{0:.1f}-{1:.1f}'.format(12.12, 11.12)

    >> 12.1-11.1

格式化的符号用大括号括起来，冒号前面代表参数的索引。

### 更多字符串处理
如果想分解字符串使用split

    list = '1,2,3,4'.split(',')
    print list

    >>> ['1', '2', '3', '4'] 

连接字符串使用join方法

    list = [1, 2, 3, 4]
    str = ''.join(list)

    print str
    >>> 1 2 3 4

搜索字符串的方法有很多

- startswith()
- endswith()
- in
- index()

下面来距离各个方法的用法

    'abc'.startswith('a')
    >>> True

    'abc'.endswith(c)
    >>> True

    'b' in 'abc'
    >>> True

    'abc'.index('b')
    >>> 1

删除字符串的一部分使用strip

    str = 'abcdef'

    print str.strip('a')

    >>> bcdef

    str = '  abc  '

    print str.strip() # 没有参数删除空格
    >>> abc

改变大小写使用lower和upper

    print 'abc'.upper()
    >>> 'ABC'

    print 'ABC'.lower()
    >>> 'abc'

## 文件输入与输出
这一章讲了python如何读写文件。

文件的属性包括文字，类型，位置和大小等。

将一组文件组织在一起得东西称为目录，目录还可以组织目录，称为子目录。

### 打开文件
对文件进行操作之前需要先打开文件

    file = open('test.txt', 'r'); # 读文件
    file = open('test.txt', 'w'); # 写文件
    file = open('test.txt', 'a'); # 追加文件

### 读文件
读文件之前需要先打开文件，然后使用readlines将文件读到列表中，列表的每一项是文件中的一行

    file = open('test.txt', 'r'); # 读文件
    lines = file.readlines()
    print lines
    file.close() # 一定不要忘记关闭文件

    >>> ['line1\n', 'line2\n', 'line3']

还可以使用readline每次读取一行文件
    
    file = open('test.txt', 'r'); # 读文件
    line1 = file.readline()
    line2 = file.readline()
    
    print line1
    print line2

    file.close()
    >>> line1
    >>> line2

如果想改变文件当前读到了第几行，可以使用seek

    file = open('test.txt', 'r'); # 读文件
    line1 = file.readline()
    file.seek()
    line2 = file.readline()
    
    print line1
    print line2

    file.close()

    >>> line1
    >>> line1

### 文本文件和二进制文件
文件分为文本文件和二进制文件，打开文本文件和二进制文件的方式有些区别

    file1 = open('text.txt', 'r') # 打开文本文件
    file2 = open('music.mp3', 'rb') # 打开二进制文件

### 写文件
写文件两种方式，第一种是覆盖现有文件，第二种是追加现有文件。

    file1 = open('text.txt', 'w') # 打开文件，后续可写
    file2 = open('text.txt', 'a') # 打开文本，后续可追加

打开文件后可以使用write函数来往文件写内容

    file = open('text.txt', 'w')
    file.write('\nline1')
    file.write('\nline1')

    file.close()

还可以用print函数进行写文件

    file = open('text.txt', 'w')
    print >> file, "\nline1"

    file.close()

上面的`>>`符号的意思是重定向输出，即把输出重定向到文件，而不是显示器

### 在文件中保存内容：pickle
python中为在文件中存取对象提供了一个方便的模块——pickle

存储文件的过程如下：

    import pickle

    list = ['12', '12', '12', '12']
    
    file = open('temp.pkl', 'w')

    pickle.dump(list, file);

    file.close()

还原的过程如下：

    import pickle

    file = open('temp.pkl', 'r')
    
    list = pickle.load(file)

    file.close()

    print list
    >>> ['12', '12', '12', '12']

## 游戏
书中还提到了很多小游戏，其中也介绍了很多制作游戏和UI的库，比如easyui，pygame等

举一个猜拳游戏的小例子：

    import random

    secret = random.randint(1, 99)

    guess = 0
    tries = 0

    print "helow, guess"
    print "number from 1 to 99, 6 times"

    while guess != secret and tries < 6:
        guess = input("guess is:")
        if guess < secret:
            print "too low"
        elif guess > secret:
            print "too high"

        tries = tries + 1

    if guess == secret:
        print "success"
    else:
        print "fail"
        print "secret is ", secret

## 总结
这是我读《[父与子的编程之旅：与小卡特一起学Python][2]》后记录总结的一些笔记，书中还介绍了很多其他内容，如果你没看过我强烈建议你看一看这本书，如果看过了可以看这篇笔记用来快速回忆里面的内容。

最后感谢你的阅读。

[1]: https://www.python.org/
[2]: http://www.amazon.cn/gp/product/B0153174GS/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=536&creative=3200&creativeASIN=B0153174GS&linkCode=as2&tag=yanhaijing-23
