# Python入门

把Python环境搭建完成之后，就可以尝试运行Python程序了。运行Python程序有两种方式，第一种是直接通过命令行编写代码运行，第二种是通过编辑器编写代码运行。

对于程序员来说，学习一门新的语言，第一步是通过这门语言向世界问好：“Hello World”，那么我们也通过Python向世界问好吧。

### **使用终端运行Python程序**

1. 打开命令行窗口（通过快捷键`Win+R`打开运行窗口，输入`cmd`即可进入命令行窗口）
2. 输入`python`进入python运行环境（正确的python运行环境会有`>>>`的提示）
3. 输入你的第一行Python代码`print('Hello World')`，回车即可运行，第一次运行，有几个需要注意的地方：
   - 注意在`Hello World`前后都有单引号`'`
   - `print`和`>>>`不可以有空格
   - 注意`(`、`)`、`'`、`'）`均为英文字符

正确的输出结果如下：

![image-20210929115353676](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210929115353676.png)

可以尝试修改单引号里面的内容，输出你喜欢的内容。

### **使用编辑器运行Python程序**

随着Python热门起来，现在越来越多的编辑器支持Python代码的编写了。
常见的编辑器包括`Sublime Text3`，`Visual Code`，`PyCharm`等。

#  Python变量和数据类型

## Python基础数据类型

计算机顾名思义就是可以做数学计算的机器，因此，计算机程序理所当然地可以处理各种数值。但是，计算机能处理的远不止数值，还可以处理文本、图形、音频、视频、网页等各种各样的数据，不同的数据，需要定义不同的数据类型。

学习编程，认识不同编程中的数据类型是必要的，在Python中，能够直接处理的数据类型有以下几种：

### **整数**

整数和我们生活中定义的整数是一个概念，例如：`1`,`2`,`3`,`10`,`100`,`1000`,`-1000` 等等，都是整数，Python可以处理任意大小的整数。

对于整数，除了生活中常用的十进制以外，计算机由于使用二进制，所以，在计算机中也常用二进制或者十六进制表示整数。相比十进制数，在Python中使用以下方式表示二进制数和十六进制数。

二进制数只使用数字0、1表示，在Python中，二进制整数使用前缀`0b`表示，比如：`0b0110`，`0b1100`。

十六进制数除了0~9十个数字以外，还使用a、b、c、d、e、f，在Python中，十六进制使用前缀`0x`，比如：`0x12ef`，`0xde2431af`。

十进制数、二进制数和十六进制数之间是可以相互转换的，如果感兴趣的同学，可以学习[《编程必备基础知识》](https://coding.imooc.com/learn/list/355.html)了解更多转换的细节。

### **浮点数**

浮点数对应我们生活的是小数，例如：`0.1`,`0.5`, `12.34`, `3.1415926`等，都是浮点数。

为什么小数在计算机领域被称为浮点数呢？这是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的（浮动的），比如，`1.23x10^9`和`12.3x10^8`是相等的，因此称为浮点数。

浮点数可以用数学写法，如`1.23`，`3.14`，`-9.01`。但是对于很大或很小的浮点数，就必须用科学计数法表示，在Python中，把10用e替代，比如：`1.23x10^9`就是`1.23e9`，或者`12.3e8`，`0.000012`可以写成`1.2e-5`，同学可以自行举出更多的例子。

这里有必要提醒一点就是，整数和浮点数在计算机内部存储的方式是不同的，整数运算永远是精确的，而浮点数运算则可能会有四舍五入的误差，如何检验，可以在Python终端中输入以下内容`0.1 + 0.2`，看看可以得到你期望的结果`0.3`吗？真实结果可能让你失望了。

![image-20210929115440831](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210929115440831.png)

同样的，这里涉及的原理同学也可以学习上面提到的课程进行进一步原理层面的理解。

### **字符串**

字符串对应生活中的就是非数字类型的内容，比如一个句子，一段话，在Python中就是字符串，在Python中，字符串是以''或""括起来的任意文本，比如'abc'，"xyz"等等。请注意，''或""本身只是一种表示方式，不是字符串的一部分，因此，字符串'abc'只有a，b，c这3个字符。

比如之前练习过的第一个Python程序：`print('Hello World')`，其中的`Hello World`就是字符串。

### **布尔值**

布尔值对应于生活中的就是`对`和`错`，在计算机的世界里，大部分判断都是非错则对的，布尔值和布尔代数的表示完全一致，一个布尔值只有True、False两种值，要么是True，要么是False，在Python中，可以直接用True、False表示布尔值（请注意大小写，不需要使用字符串符号括起来），也可以通过布尔运算计算出来。

布尔值可以用`and`、`or`和`not`运算（注意`and`,`or`,`not`都是Python语言本身的关键字）。

`and`运算是与运算，只有所有都为 True，and运算结果才是 True。

`or`运算是或运算，只要其中有一个为 True，or 运算结果就是 True。

`not`运算是非运算，它是一个单目运算符，把 True 变成 False，False 变成 True。

### **空值**

空值是Python里一个特殊的值，用`None`表示。

注意，None和0是不一样的，None不能理解为0，因为0是有意义的，比如我有0个苹果表示我没有苹果，0表达的是数值0的意思，而不能表示为我有None个苹果，None是一个特殊的空值。

此外，Python还提供了列表、字典等多种数据类型，还允许创建自定义数据类型，我们后面会展开介绍。

## Python定义变量的方法

### **什么是变量**

在Python中，变量的概念基本上和初中代数的方程变量是一致的。例如，对于方程式 y=x*x ，x就是变量。当x=2时，计算结果是4，当x=5时，计算结果是25。

### **合法的变量名**

只是在计算机程序中，变量不仅可以是数字，还可以是任意数据类型（字符串、布尔值、空值、字典等）。在Python中，定义一个变量需要遵循一定的约束，否则，Python可能识别不出它是一个变量。

1. 变量名由大小写英文字母、数字和下划线`_`组成
2. 变量不能用数字开头
3. 变量尽量不要和Python关键字重合（比如前面学习过的：and、or、not，否则可能导致Python原有关键字发挥不出作用）

以下这些变量的定义都是合法的。

```
num, count, _none, min_value
```

他们都满足上面的三个条件。

以下这些变量的定义都是不合法的。

```
1num, 666, 1_cd, and
```

### **定义变量**

定义变量的方式很简单，通过`变量名` = `数据`，即可定义一个变量。
举个例子：

```
a = 1
```

在这个例子里面，`a`就是变量，它的值是一个整数1。

```
hello = 'Hello'
```

在这个例子里面，`hello`就是变量，它的值是一个字符串'Hello'。
在Python里面，一个变量可以先后存储多种不同类型的数据。

```
a = 1 # 这个时候a存储的是整数类型
print(a)
a = 'ABC' # 这个时候a存储的是字符串类型
print(a)
```

这是Python这类语言特有的特性，我们称之为动态语言，与之对应的是静态语言，Python、Javascript等等都是动态语言，Java、C、C++等等属于静态语言。

## Python的整数与浮点数

在Python中，整数和浮点数虽然属于不同的数值类型，但是在运算上是可以一起运算的，这从生活经验出发，也是可以理解的。

### **四则运算**

整数、浮点数可以直接进行四则运算。

```
# 加法
num1 = 10
num2 = 0.5
result = num1 + num2
print(result) # ==> 10.5
# 减法
result = num1 - num2
print(result) # ==> 9.5
# 乘法
result = num1 * num2
print(result) # ==> 5.0
# 除法
result = num1 / num2
print(result) # ==>20.0
```

从上面可以发现一个规律，整数和浮点数运算后 ，得到的结果不管小数点后是否有值，结果都变成浮点数了，这是合理的，浮点数可以表达整数的结果，但是整数不能表达浮点数的结果。
**注意：在Python2使用除法可能和Python3得到不一样的结果**

```
# python2
num1 = 10
num2 = 3
result = num1 / num2
print(result) # ==> 3
# python3
num1 = 10
num2 = 3
result = num1 / num2
print(result) # ==> 3.3333333333333335
```

可以看到在python2，得到的是一个整数的结果，这是因为除数和被除数都是整数时，得到的结果也默认保存为整数了，这是非常不科学的，因此在python3，改进了这一点。

### **取模运算**

Python数字支持取模运算，使用百分号`%`表示取模。

```
print(3 % 2) # ==> 1
print(33 % 10) # ==> 3
print(99 % 30) # ==> 9
```

恰当使用取模运算，可以判断一个数是否为偶数，当一个数对2取模结果为0时，则这个数为偶数，否则为奇数。

```
print(3 % 2) # ==> 1 因此3为奇数
print(33 % 2) # ==> 1 因此33为奇数
print(100 % 2) # ==> 0 因此100为偶数
```

### **地板除**

Python除了普通除法以外，还有一个特殊的除法被称为`地板除`，对于`地板除`，得到的结果会忽略纯小数的部分，得到整数的部分，地板除使用`//`进行。

```
10//4 # ==> 2
10//2.5 # ==> 4.0
10//3 # ==> 3
```

### **小数点位数**

使用Python计算小数的时候，经常需要保留小数点后若干位，可以使用round()函数来处理，这里先了解round的调用方式，使用两个参数，第一个是需要保留小数点位数的数值，第二个是保留的位数。

```
num = 10 / 3
print(num) # ==> 3.3333333333333335
# 使用round保留两位小数
round(num, 2) # ==> 3.33
```

## Python的布尔类型

前面我们了解到，布尔类型是Python的基础数据类型，布尔类型只有True和False两种值，本节课我们学习布尔类型的集中运算。

### **与运算**

只有两个布尔值都为 True 时，计算结果才为 True。

```
True and True # ==> True
True and False # ==> False
False and True # ==> False
False and False # ==> False
```

### **或运算**

只要有一个布尔值为 True，计算结果就是 True。

```
True or True # ==> True
True or False # ==> True
False or True # ==> True
False or False # ==> False
```

### **非运算**

把True变为False，或者把False变为True：

```
not True # ==> False
not False # ==> True
```

这些运算有什么用呢？计算机程序是由无数的逻辑分支组成的，通过布尔运算，可以在计算机中实现条件判断，根据计算结果为True或者False，计算机可以自动执行不同的后续代码，因此学习布尔运算也是非常有必要的。

在Python中，布尔类型还可以与其他数据类型（字符串，数字等）做 and、or和not运算，请看下面的代码：

```
a = True
print(a and 0 or 99) # ==> 99
```

得到的计算结果不是布尔类型，而是数字99，这是为什么呢？

因为Python把0、空字符串和None看成False，其他数值和非空字符串都看成True，所以：

`True and 0`计算结果是0 
继续计算`0 or 99`计算结果是 99 
因此，结果是99。
需要注意的是，not计算的优先级是高于and和or的。

```
True and not False # ==> True
```

在上述布尔计算中，先计算`not False = True`，然后再计算`True and True`，因此得到True的结果。

### **短路计算**

1. 在计算`a and b`时，如果 a 是 False，则根据与运算法则，整个结果必定为 False，因此返回 a；如果 a 是 True，则整个计算结果必定取决与 b，因此返回 b。
2. 在计算`a or b`时，如果 a 是 True，则根据或运算法则，整个计算结果必定为 True，因此返回 a；如果 a 是 False，则整个计算结果必定取决于 b，因此返回 b。

所以Python解释器在做布尔运算时，只要能提前确定计算结果，它就不会往后算了，直接返回结果。

## Python的字符串

前面我们讲解了什么是字符串。字符串可以用`' '`或者`" "`括起来表示。

如果字符串本身包含`'`怎么办？比如我们要表示字符串 `I'm OK `，这时，可以用`" "`括起来表示：

```
"I'm OK"
```

类似的，如果字符串包含`"`，我们就可以用`' '`括起来表示：

```
'Learn "Python" in imooc'
```

但是，如果字符串既包含`'`又包含`"`怎么办？

这个时候，就需要对字符串中的某些特殊字符进行“转义”，Python字符串用`\`进行转义。

要表示字符串`Bob said "I'm OK"`
由于`'`和`"`会引起歧义，因此，我们在它前面插入一个`\`表示这是一个普通字符，不代表字符串的起始，因此，这个字符串又可以表示为

```
'Bob said \"I\'m OK\".'
```

注意：转义字符 `\`不计入字符串的内容中。

常用的转义字符还有：

`\n`表示换行
`\t` 表示一个制表符
`\\`表示 `\` 字符本身

## Python中raw字符串与多行字符串

如果一个字符串包含很多需要转义的字符，对每一个字符都进行转义会很麻烦。为了避免这种情况，我们可以在字符串前面加个前缀`r`，表示这是一个 raw 字符串，里面的字符就不需要转义了。例如：

```
r'\(~_~)/ \(~_~)/'
```

但是`r'...'`表示法不能表示多行字符串，也不能表示包含`'`和 `"`的字符串。

如果要表示多行字符串，可以用`'''...'''`表示：

```
'''Line 1
Line 2
Line 3'''
```

上面这个字符串的表示方法和下面的是完全一样的：

'Line 1\nLine 2\nLine 3'

还可以在多行字符串前面添加`r`，把这个多行字符串也变成一个raw字符串：

```python
r'''Python is created by "Guido".
It is free and easy to learn.
Let's start learn Python in imooc!'''
```

## Python的字符串format

字符串是Python程序重要的数据类型，到目前为止，我们输出的字符串的内容都是固定的，但有时候通过字符串输出的内容不是固定的，这个时候需要使用format来处理字符串，输出不固定的内容。
字符串format由两个部分组成，字符串模板和模板数据内容组成，通过大括号`{}`，就可以把模板数据内容嵌到字符串模板对应的位置。

```
# 字符串模板
template = 'Hello {}'
# 模板数据内容
world = 'World'
result = template.format(world)
print(result) # ==> Hello World
```

如果模板中`{}`比较多，则容易错乱，那么在format的时候也可以指定模板数据内容的顺序。

```
# 指定顺序
template = 'Hello {0}, Hello {1}, Hello {2}, Hello {3}.'
result = template.format('World', 'China', 'Beijing', 'imooc')
print(result) # ==> Hello World, Hello China, Hello Beijing, Hello imooc.
# 调整顺序
template = 'Hello {3}, Hello {2}, Hello {1}, Hello {0}.'
result = template.format('World', 'China', 'Beijing', 'imooc')
print(result) # ==> Hello imooc, Hello Beijing, Hello China, Hello World.
```

除了使用顺序，还可以指定对应的名字，使得在format过程更加清晰。

```
# 指定{}的名字w,c,b,i
template = 'Hello {w}, Hello {c}, Hello {b}, Hello {i}.'
world = 'World'
china = 'China'
beijing = 'Beijing'
imooc = 'imooc'
# 指定名字对应的模板数据内容
result = template.format(w = world, c = china, b = beijing, i = imooc)
print(result) # ==> Hello World, Hello China, Hello Beijing, Hello imooc.
```

## Python的字符串编码

在python2中，字符串的编码问题是使用python2必经历的门槛，所幸到了python3，python3从编程语言的层面就减少了很多编码的问题，但是学习字符串编码还是很有必要的。

### **为什么有编码问题**

因为计算机只能处理数字，如果要处理文本，就必须先把文本转换为数字才能处理。最早的计算机在设计时采用8个比特（bit）作为一个字节（byte），所以，一个字节能表示的最大的整数就是255（二进制11111111=十进制255），0 - 255被用来表示大小写英文字母、数字和一些符号，这种编码方式被称为ASCII编码，比如大写字母 A 的编码是65，小写字母 z 的编码是122。
如果要表示中文，显然一个字节是不够的，至少需要两个字节，而且还不能和ASCII编码冲突，所以，中国制定了GB2312编码，用来把中文编进去。
类似的，日文和韩文等其他语言也有这个问题。为了统一所有文字的编码，Unicode应运而生。Unicode把所有语言都统一到一套编码里，这样就不会再有乱码问题了。
Unicode通常用两个字节表示一个字符，原有的英文编码从单字节变成双字节，只需要把高字节全部填为0就可以。

### **python3的编码**

在python3中，默认使用UTF-8 Unicode来进行编码，因此我们可以在python中输入任意形式的Unicode字符串，都不会遇到像python2中遇到的问题（在python2中，需要显式指明该字符串是Unicode字符串），如果没有了解过python2，则完全可以忽略这一点，python3提供了更加简单易懂的编码方式。

```
s1 = '这是中文字符串'
s2 = 'this is an English string'
print(s1)
print(s2)
```

在python3中，中文字符串和英文字符串无异。

## Python的字符串切片

字符串由一个个字符组成，每一个字符都有一个唯一的位置。比如字符串`'ABC'`，第一个字符是`A`，第二个字符是`B`，第三个字符是`C`。
因此我们可以使用位置的方式取出字符串中特定位置的字符，按照位置取字符串的方式使用中括号`[]`访问，这个时候可以把字符串看作是一个列表（一种新的数据类型，在后面会继续学习），**不过需要注意的是，在程序的世界中，计数是从**`0`**开始的，使用**`0`**来表示第一个。**

```
s = 'ABC'
a = s[0] # 第一个
b = s[1] # 第二个
c = s[2] # 第三个
print(a) # ==> A
print(b) # ==> B
print(c) # ==> C
```

有时候，我们会想获取字符串的一部分（子串），这个时候我们采取切片的方式获取，切片需要在中括号`[]`中填入两个数字，中间用冒号分开，表示子串的开始位置和结束位置，并且这是半闭半开区间，不包括最后的位置。

```
ab = s[0:2] # 取字符串s中的第一个字符到第三个字符，不包括第三个字符
print(ab) # ==> AB
```

我们定义一个更长的字符串，了解切片更多的细节。

```
s = 'ABCDEFGHIJK'
abcd = s[0:4] # 取字符串s中的第一个字符到第五个字符，不包括第五个字符
print(abcd) # ==> ABCD
cdef = s[2:6] # 取字符串s中的第三个字符到第七个字符，不包括第七个字符
print(cdef) # ==> CDEF
```

#  Python语言的控制流程

## Python之if语句

计算机之所以能做很多自动化的任务，因为它可以自己做条件判断，通过条件判断，选择做什么样的逻辑（当然，逻辑是需要我们提前写好的），我们称之为条件分支判断。
举个例子，在100分试卷的考试中，小于60分我们认为是不及格的，因此，我们可以使用程序自动判断考试是否及格。

```
score = 59
if score < 60:
    print('抱歉，考试不及格')
# ==> 抱歉，考试不及格
```

这里，因为`score = 59 < 60`，所以if的判断是`True`，因此就会执行`print('抱歉，考试不及格')`。
这里有几个需要注意的地方：

1. 可以看到`print('抱歉，考试不及格')`这行代码明显比上一行代码缩进了，这是因为这行代码是if判断的一个子分支，因此需要缩进，在Python规范中，一般使用4个空格作为缩进
2. 在if语句的最后，有一个冒号`:`，这是条件分支判断的格式，在最后加入冒号`:`，表示接下来是分支代码块

## Python之if-else语句

使用if判断，可以在当if条件为True时，执行if的子逻辑分支，但有时候，也想在if条件不为True时，执行别的子逻辑分支。
比如：在上一节课的例子中，我希望当分数小于60分时输出，`抱歉，考试不及格`，否则，输出`恭喜你，考试及格`，这个时候可以使用if-else语句。

```
score = 59
if score < 60:
    print('抱歉，考试不及格')
else:
    print('恭喜你，考试及格')
```

这个时候，程序就会根据score的值，走不同的子逻辑分支，同学可以改变score的值试一试。
在这里，同样需要注意两个地方，第一个是冒号`:`，在else中，同样需要冒号；其次是缩进，在else的子逻辑分支，同样需要缩进。

## Python之if-elif-else语句

在100分的考试当中，分数达到或超过90分是顶尖的，达到或超过80分是优秀的，如果想对达到或者超过60分的学生进行不同的分类，使用if-else进行判断，代码如下：

```
score = 59
if score < 60:
    print('抱歉，考试不及格')
else:
    if score >= 90:
        print('恭喜你，拿到卓越的成绩')
    else:
        if score >= 80:
            print('恭喜你，拿到优秀的成绩')
        else:
            print('恭喜你，考试及格')
```

在这个程序里，我们做了多次分类，第一次，我们把低于60分和大于等于60分的分开，第二次，我们把大于等于90分和小于90分的分开，第三次，我们把大于等于80分和小于80分的分开。
这样写，我们得到一个两层嵌套的if-else语句，这样的实现可以满足我们的要求，但是如果继续增加条件，比如继续判断高于70分和低于70分的话，那么这个代码将会缩进越来越多，代码逻辑看起来也不够清晰。
我们可以使用if-elif-else语句来简化以上的逻辑。其中elif就是else if的意思。

```
score = 59
if score < 60:
    print('抱歉，考试不及格')
elif score >= 90:
    print('恭喜你，拿到卓越的成绩')
elif score >= 80:
    print('恭喜你，拿到优秀的成绩')
else:
    print('恭喜你，考试及格')
```

这样，我们就可以写出代码结构非常清晰的一系列条件判断了。
**特别注意: 这一系列条件判断会从上到下依次判断，如果某个判断为 True，执行完对应的代码块，后面的条件判断就直接忽略，不再执行了。**
请思考以下代码将会输出什么？为什么不输出`恭喜你，拿到卓越的成绩`。

```
score = 95
if score < 60:
    print('抱歉，考试不及格')
elif score >= 80:
    print('恭喜你，拿到优秀的成绩')
elif score >= 90:
    print('恭喜你，拿到卓越的成绩')
else:
    print('恭喜你，考试及格')
```

## Python之for循环

for循环在Python语言的流程控制中是非常重要的，在编程中有很多场景需要使用到for循环。举个例子，当我们需要把字符串中的每一个字符打印出来的时候，我们怎么实现呢？
我们当然可以使用之前学习的指定位置的方式让每个字符打印出来。

```
s = 'ABCD'
print(s[0])
print(s[1])
print(s[2])
print(s[3])
```

但是，这是字符串s比较短的情况下可以实现的，当s拥有成千上万个字符的时候，难道我们要为此书写上万行代码吗？这个时候for循环就可以派上用场了。

```
s = 'ABCD'
for ch in s:
    print(ch) # 注意缩进
```

在上述代码中，`ch`是在for循环中定义的，意思是把字符串`s`中的每一个元素依次赋值给ch，然后再把ch打印出来，直到打印出字符串s的最后一个字符为止。

## Python之while循环

和 for 循环不同的另一种循环是 while 循环，while循环可以继续进行下去的条件更加简单，只需要判断while循环的条件是否为True即可，当条件为True时，即继续运行下去。
比如：

```
while True:
    print(1)
```

在上述代码中，由于while的条件一直为True，所以这个代码将会无限的输出`1`**，同学们不要轻易尝试。**
我们可以把while循环的条件设置得复杂一些，在运行一定次数后，条件可以自动变为False从而跳出while循环。
比如计算1~100的和。

```
num = 1
sum = 0
while num <= 100:
    sum = sum + num # 注意缩进
    num = num + 1 # 注意缩进
print(sum) # ==> 5050
```

在上述代码中，while的判断条件是`num <= 100`，当num小于或者等于100时，循环会继续下去，但当num > 100时，将跳出循环；因为在while循环里面num不断加1，所以num最终会大于100，因此while循环不会无限进行下去。

## Python之break跳出循环

用 for 循环或者 while 循环时，如果要在循环体内直接退出循环，可以使用 break 语句。
比如在前面的无限循环里面，只要在恰当的时机，我们使用break跳出循环，也可以求出1~100的和。

```
num = 1
sum = 0
while True:
    if num > 100:
        break
    sum = sum + num
    num = num + 1
print(sum)
```

同样的，对于字符串s = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'，假如希望输出s的前20个字符，而不是所有字符，我们也可以使用break。

```
s = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
num = 1
for ch in s:
    if num > 20:
        break
    print(ch)
    num = num + 1
```

## Python之continue继续循环

使用continue，我们可以控制循环继续下去，并跳过continue后面的逻辑，比如，对于字符串s = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'，假如希望输出字符串s中第10个以后的字符，而不是所有字符，这个时候， 我们可以使用continue跳过前面的9个字符。

```
s = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
num = 1
for ch in s:
    if num < 10:
        num = num + 1
        continue # 当num < 10时，跳过后续循环代码，继续下一次循环
    print(ch)
    num = num + 1
```

## Python之嵌套循环

就像多层if-else嵌套一样，python的循环也支持嵌套。
我们使用两层嵌套循环输出字符串'ABC'中每个字符和字符串'123'每个字符的排列。

```
s1 = 'ABC'
s2 = '123'
for x in s1:
    for y in s2:
        print(x + y)
```

在上述代码中，对于外层循环，外层每循环1次，内层就会循环3次，因此，我们将会得到如下结果：

```
A1
A2
A3
B1
B2
B3
C1
C2
C3
```

# Python的List容器

## 什么是容器、什么是list

### **容器**

生活中，容器指的是可以容纳物品的收纳器，在程序中，容器是一种可以把多个元素放在一起的数据结构，容器中的元素可以逐个地迭代获取，可以用in, not in等关键字判断某个元素是否包含在容器中。
在Python中，包括列表(list)、元组(tuple)、字典(dict)、集合(set)等，他们都可以放入多个元素，因此都可以算作是容器，这些容器是Python编程中非常重要的数据结构，我们接下来重点学习这些数据结构。

### **list**

列表(list)是一种有序的容器，放入list中的元素，将会按照一定顺序排列。构造list的方法非常简单，使用中括号`[]`把需要放在容器里面的元素括起来，就定义了一个列表。
比如列出所有同学们的成绩：

```
scores = [45, 60, 75, 86, 49, 100]
```

列出所有同学们的名字：

```
names = ['Alice', 'Bob', 'David', 'Ellena'] # 注意，字符串元素仍需要引号
```

正如我们看到的，list可以放入数字、字符串等数据类型，list不对放入其中的类型进行判断，也就是说，list可以同时放入任意类型的数据，这是Python这门语言决定的，因为Python是动态语言。

```
L = ['Alice', 66, 'Bob', True, 'False', 100]
```

对于list，我们可以直接把list的内容打印出来。

```
L = ['Alice', 66, 'Bob', True, 'False', 100]
print(L)
```

## Python按顺序访问list

列表是有序的，因此我们可以按顺序访问列表中的元素。

```
L = ['Alice', 66, 'Bob', True, 'False', 100]
for item in L:
    print(item)
```

回想一下，在前面，我们学习过字符串，这里使用for循环访问列表中的每一个元素和使用for循环访问字符串中的每一个字符是非常类似的。
事实上字符串也可以看作是一种特殊的列表，它只能按顺序存放多个字符。通过for循环访问列表每一个元素的方式，我们称为迭代。
而对于一个空的列表，使用for循环访问，将不会打印任何东西。

```
L = []
for item in L:
    print(item)
```

## Python按索引访问list

由于列表list是一个有序的容器，所以在list里面，每一个元素都有一个唯一的位置，我们称之为索引(index)，这和字符串是类似的，因此我们也可以通过位置的方式获取list中的元素，回顾一下前面学习的，我们通过中括号`[]`来按位置访问对应的元素。
**注意，这里要注意区分，列表的定义也是通过中括号**`[]`**来定义的，但这和通过索引访问列表里面的元素并不冲突**

```
names = ['Alice', 'Bob', 'David', 'Ellena']
print(names[0])
print(names[1])
print(names[2])
print(names[3])
```

由于names只有四个元素，所以我们最多只能通过索引3访问到最后一个元素。试想一下，如果我们print(names[4])，会怎么样？

```
names = ['Alice', 'Bob', 'David', 'Ellena']
print(names[4])
```

事实上，这会引起Python运行的错误，提示索引访问超出范围。

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

因此，我们在使用索引的方式访问列表时，一定要特别注意不要越界。
同时，列表和字符串一样，也支持切片，通过切片的方式，获取到列表的子列表。

```
names = ['Alice', 'Bob', 'David', 'Ellena']
sub_names = names[0:2]
print(sub_names)
```

这里需要注意一下，如果我们越界切片的话，不会出现Python运行错误，但是按照这样的下标去切片，获取不到任何元素。

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
sub_names = names[5:10]
print(sub_names) # ==> []
```

## Python倒序访问list

Python的列表，除了支持正向顺序索引获取列表中的每一个元素以外，也支持倒序访问list中的每一个元素。

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
```

对于names列表，`Ellena`的名字排在最后，也就是我们所说的倒数第一个，在Python中，可以使用`-1`来表示最后一个元素。

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
print(names[-1]) # ==> Ellena
```

同样的道理，我们可以通过`-2`，打印出`David`的名字，通过`-3`，打印出`Bob`的位置。

```python
print(names[-2]) # ==> David
print(names[-3]) # ==> Bob
```

注意，如果我们使用`-5`的话，因为不存在倒数第五个名字，因此这也是一种越界，同样会报错。

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
print(names[-5])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

## Python向list添加新的元素

现在班里面有4名同学：

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
```

今天，班里转来一名新同学Candy，如何把新同学添加到现有的列表当中呢？
在Python中，list提供了一系列的方法可以让我们操作list中的元素，其中也包含了添加元素的方法。
第一个办法是用`append()`方法，把新同学追加到列表的末尾：

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
names.append('Candy')
print(names) # ==> ['Alice', 'Bob', 'David', 'Ellena', 'Candy']
```

**注意，`append()`方法总是将元素添加到list的尾部。** 
如果上面的列表需要按照首字母排序的话，那么Candy应该是排在第三的位置的，这怎么办呢？
这就需要使用list的`insert()`方法，insert()方法和append()方法不一样，insert()方法需要两个参数，分别是需要插入的位置，以及需要插入的元素。

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
names.insert(2, 'Candy')
print(names) # ==> ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
```

**注意，将Candy插入到第三的位置之后，原来的名字，都将自动往后移动一位，这个时候再使用相同的索引获取后面的元素，将会得到不一样的结果**

```python
names = ['Alice', 'Bob', 'David', 'Ellena']
print(names[2]) # ==> David
names.insert(2, 'Candy')
print(names[2]) # ==>Candy
```

## Python从list删除元素

如果Ellena因为家庭原因需要转学，那么我们如何把Ellena从已有的列表里面删除呢？
这个时候我们可以使用列表的pop()方法，pop()方法默认删除列表的最后一个元素，并返回。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
name = L.pop()
print(name) # ==> Ellena
print(L) # ==> L = ['Alice', 'Bob', 'Candy', 'David']
```

对于Ellena，由于Ellena恰好位于列表的最后，所以可以直接使用pop()方法把Ellena从列表的最后删除，假如需要转学的不是Ellena，而是Candy，这个时候应该怎么办呢？
pop()方法，除了可以删除最后一个元素以外，pop()还可以接收一个参数，指定需要删除的元素的位置。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
name = L.pop(2)
print(name) # ==> Candy
print(L) # ==> ['Alice', 'Bob', 'David', 'Ellena']
```

对于列表，除了可以向列表添加元素，删除列表元素以外，列表已有的元素，也是可以修改的，通过索引指定位置，并赋值新的元素，即可替换列表中原有的元素。
假如班上同学Candy需要转走了，同时有一个新的同学Canlina转入，那么按照字母排序，Canlina的位置恰好是Candy的位置。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
L[2] = 'Canlina'
print(L)
```

我们也可以使用倒序索引来完成同样的功能。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
L[-3] = 'Canlina'
print(L)
```

注意，如果替换一个不存在的下标，则同样会引起Python运行错误。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
L[6] = 'Canlina'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list assignment index out of range
```

## Python二维list

有时候，一维list并不能满足所有的要求（上述所有list均为一维list），这个时候需要二维list甚至更高维的list。
比如：
Alice最近的三次成绩分别是`[100, 89, 92]`
Bob最近的三次成绩分别是`[70, 65, 81]`
Candy最近的三次成绩分别是`[88, 72, 77]`
如果需要用一个列表存放三个同学的成绩，则需要这样：

```python
alice_scores = [100, 89, 92]
bob_scores = [70, 65, 81]
candy_scores = [88, 72, 77]
all_scores = [alice_scores, bob_scores, candy_scores]
print(all_scores) # ==> [[100, 89, 92], [70, 65, 81], [88, 72, 77]]
```

这个时候得到的就是一个二维list，对于二维list，列表里面的每一个元素仍然是一个列表。这个时候，如果需要从二维list all_scores获取Bob最近第三次考试的成绩，可以这样写

```python
alice_scores = [100,89,92]
bob_scores = [70,65,81]
candy_scores = [88,72,77]
all_scores = [alice_scores, bob_scores, candy_scores]
score = all_scores[1][2] # ==> 81
```

其中`all_scores[1]`得到Bob的最近三次成绩的列表，再通过下标`[2]`，则可以得到Bob第三次的成绩

# Python的tuple容器

## 什么是tuple

元组(tuple)和list一样，也是一个有序容器，在元组中，同样可以包含0个或者多个元素，并且也支持索引访问、切片等操作。
定义元组的方式是使用小括号`()`将元组内的元素括起来。

```python
T = ('Alice', 'Bob', 'Candy', 'David', 'Ellena')
# 通过下标的方式访问元素
print(T[0]) # ==> Alice
print(T[4]) # ==> Ellena
# 切片
print(T[1:3]) # ==> ('Bob', 'Candy')
```

元组数据类型可以把不是元组的容器转换为元组，比如将列表转换成元组。

```python
L = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
print(L) # ==> ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
T = tuple(L)
print(T) # ==> ('Alice', 'Bob', 'Candy', 'David', 'Ellena')
```

同样的，对于列表数据类型，也可以把元组转换成列表。

```python
T = ('Alice', 'Bob', 'Candy', 'David', 'Ellena')
print(T) # ==> ('Alice', 'Bob', 'Candy', 'David', 'Ellena')
L = list(T)
print(L) # ==> ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
```

但是，tuple和list不一样的是，tuple是固定不变的，一旦变成tuple，tuple中的每一个元素都不可被改变，同时也不能再往tuple中添加数据，而list是可以的。

```python
T = ('Alice', 'Bob', 'Candy', 'David', 'Ellena')
# 替换元素
T[1] = 'Boby'
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

请注意，元组(tuple)的这个特性是非常重要的，在运行上tuple的性能是list的数倍。

## 访问tuple元素的其他方法

由于tuple一旦定义之后便不可修改，所以在实际编程中，tuple经常用于存放固定不变的数据。
因此在使用上，tuple提供了便捷的方法可以访问tuple中的数据。

### **count()方法**

count()方法用来统计tuple中某个元素出现的次数。

```
T = (1, 1, 2, 2, 3, 3, 1, 3, 5, 7, 9)
print(T.count(1)) # ==> 3
print(T.count(5)) # ==> 1
```

对于不存在的元素，count方法不会报错，而是返回0，这是合理的，因为元组里面有0个不存在的元素。

```
T = (1, 1, 2, 2, 3, 3, 1, 3, 5, 7, 9)
print(T.count(10)) # ==> 0
```

### **index()方法**

index()方法可以返回指定元素的下标，当一个元素多次重复出现时，则返回第一次出现的下标位置。

```
T = (1, 1, 2, 2, 3, 3, 1, 3, 5, 7, 9)
T.index(9) # ==> 10
T.index(5) # ==> 8
T.index(1) # ==> 0 # 多次出现，返回第一次出现的位置
```

注意，index()方法和count()方法不一样，当指定的元素不存在时，使用index()方法Python会报错。

```
T = (1, 1, 2, 2, 3, 3, 1, 3, 5, 7, 9)
T.index(100)
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: tuple.index(x): x not in tuple
```

## Python创建单个元素的tuple

tuple和list一样，可以包含 0 个、1个和任意多个元素。
包含多个元素的 tuple，前面我们已经创建过了。

包含 0 个元素的 tuple，也就是空tuple，直接用`()`表示：

```
T = ()
print(T) # ==> ()
```

接着，我们创建包含一个元素的tuple。

```
T = (1)
print(T) # ==> 1
```

这和我们期望的输出有些差异，为什么包含一个元素的元组打印出来之后没有小括号，而是只有一个数字1呢？
回顾一下前面数字的四则运算。

```
result = 3 * 4 - 2
print(result) # ==> 10
# 改变优先级，先运算减法
result = 3 * (4 - 2)
print(result) # ==> 6
```

可以看到，改变优先级我们是通过`()`来实现的，这和元组的定义有冲突，这就解释了前面只有一个元素的元组，为什么打印出来却得到一个数字的结果了。
因为`()`既可以表示tuple，又可以作为括号表示运算时的优先级，结果`(1)`被Python解释器计算出结果 1，导致我们得到的不是tuple，而是整数 1。
因此，要定义只有一个元素的tuple，需要在元素后面添加一个逗号`,`。

```
T = (1, )
print(T) # ==> (1, )
```

而对于多个元素的tuple，则加和不加这个逗号，效果是一样的。

```
>>> T = (1, 2, 3,)
>>> print(T) # ==> (1, 2, 3)
```

## Python的可变tuple

前面我们学习了，对于tuple，它和list一个最大的不同点就是tuple是不可变的，tuple里面的元素，也是不可替换的。但是这针对的是仅包含基础数据类型（数字类型、布尔类型、字符串类型）的数据，对于组合数据类型，则不受这个约束。

```
T = (1, 'CH', [3, 4])
```

这里T有三个元素，第一个元素是数字类型，第二个元素是字符串类型，第三个元素是列表类型的，我们尝试修改第三个元素的数据。

```
T = (1, 'CH', [3, 4])
L = T[2]
print(L) # ==> [3, 4]
# 尝试替换L中的元素
L[1] = 40
print(L) # ==> [3, 40]
print(T) # ==> (1, 'CH', [3, 40])
```

这个时候，我们发现，元组T中的第三个元素已经成功被改变了，这就有悖前面的定义，元组是不可改变的。那么这到底是为什么呢？
这是因为虽然tuple中的list元素改变了，但是tuple本身指向的list仍然是同一个list，list本身并没有改变，改变的只是list里面的一个元素，这是tuple所约束不到的范围。

![image-20210929130653053](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210929130653053.png)

```
T = (1, 'CH', [3, 4])
L2 = [3, 40]
# 尝试替换tuple中的list
T[2] = L2
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

如果我们直接替换list，这也是不行的。

# Python的Dict容器

## 什么是dict

我们已经知道，List 和 tuple 可以用来表示顺序集合，例如，班里同学的名字：

```
['Alice', 'Bob', 'Candy', 'David', 'Ellena'] # List
('Alice', 'Bob', 'Candy', 'David', 'Ellena') # tuple
```

或者考试的成绩：

```
[45, 60, 75, 86, 49] # list
(45, 60, 75, 86, 49) # tuple
```

如果同学名字的列表和同学成绩的列表是一一对应的，那么通过下标，我们也可以找到每个同学的成绩。

```
names = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
scores = [45, 60, 75, 86, 49]
index = 0
for name in names:
    score = scores[index]
    print('name = {}, score = {}'.format(name, score))
    index = index + 1
```

事实上，我们可以得到这样的映射。

```
'Alice' ==> 45
'Bob' ==> 60
'Candy' ==> 75
'David' ==> 86
'Ellena' ==> 49
```

但是使用两个list，始终有些麻烦的，尤其是需要变换一个列表的顺序后，另外一个列表也需要做同样的变换，否则就可能出现对应不上的问题。
python的dict就是专门保存这种映射的，使用dict可以方便的保存“名字”->“成绩”的映射。
在dict中，每一项包含一个key和一个value，key和value是一一对应的，在解决上面的问题中，我们可以使用名字作为key，成绩作为value，那么dict的定义如下：

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
```

在定义里，我们使用花括号`{}`表示这是一个dict，然后key和value之间使用冒号`:`分割，并且每一组`key:value`的最后，以逗号`,`表示这一组的结束。
我们也可以使用以下的方式定义一个dict。

```
d = dict()
print(d) # ==> {}
```

不过这种定义方式，默认得到的是一个空dict，需要调用函数往里面添加数据，我们后面会继续学习。

## Python读取dict元素

我们现在可以创建一个dict，保存名字和成绩的对应关系。

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49,
    'Gaven': 86
}
```

此时，如果想通过名字来查询某个同学的成绩，也就是通过key来查询value，这个时候怎么办呢？
dict提供通过key找到对应value的功能，通过`d[key]`的形式，就可以得到对应的value。

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49,
    'Gaven': 86
}
print(d['Bob']) # ==> 60
print(d['Alice']) # ==> 45
```

这和list通过下标找到对应位置的元素是类似的。
回顾一下前面使用下标的方式访问list元素的时候，当下标不存在时，就会引发错误，在dict中，也是一样的，当对应的key不存在时，也会引发错误。

```python
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49,
    'Gaven': 86
}
print(d['Dodo'])
# 抛出异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Dodo'
```

它的意思是key不存在，因此我们在需要通过key找到value时，一定要先判断key存不存在，然后才使用上面的方式获取对应的value，以避免错误。

```
if 'Alice' in d:
    print(d['Alice']) # ==> 45
if 'Dodo' in d: # Dodo不存在，所以不会走下面的逻辑
    print(d['Dodo'])
```

除了使用这种方法，还有一种方法可以通过key来获取对应的value，这种方法不会引起错误，dict本身提供get方法，把key当作参数传递给get方法，就可以获取对应的value，当key不存在时，也不会报错，而是返回None。

```
print(d.get('Alice')) # ==> 45
print(d.get('Dodo')) # ==> None
```

因为通过get方法在代码实现上更加简单，且不会引起错误，因此更加推荐使用get方法来获取dict的元素。

## Python添加dict元素

dict和tuple不一样，dict是可变的，我们随时可以往dict中添加新的key-value，比如对于上节课的成绩dict：

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
```

需要往里面添加Dodo、Mimi的成绩时，可以使用赋值语句往里面添加元素：

```
d['Mimi'] = 72
d['Dodo'] = 88
print(d)
```

实际上，value可以是任意类型的元素，可以是list、tuple等，假如Mimi近两次成绩分别是72，73，Dodo近两次的成绩分别是88，90，则可以使用赋值语句往dict中添加list元素。

```
d['Mimi'] = [72, 73]
d['Dodo'] = [88, 90]
print(d)
```

此后，如果Mimi、Dodo的第三次成绩也出来了，分别是75，90，则可以先通过key把对应的value查询出来，然后再往类型是list的value中添加第三次的成绩。

```
d['Mimi'].append(75)
d['Dodo'].append(90)
print(d)
```

## Python更新dict元素

上一节课我们学习了往dict中添加元素的方法，通过赋值语句就可以把元素添加到dict中去，但是赋值的时候，我们并不确定key是否已经在dict里面了，如果dict里面已经有对应的key了，那将会发生什么呢？

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
d['Bob'] = 75
print(d)
# ==> {'Alice': 45, 'Bob': 75, 'Candy': 75, 'David': 86, 'Ellena': 49}
```

这个时候我们发现，原来Bob的成绩是60，现在变成75了，因为`d['Bob'] = 75`的缘故。
因此我们发现这个赋值语句其实有两个功能：

1. 当key不存在时，往dict中添加对应的key: value元素。
2. 当key存在时，会更新dict，用新的value替换原来的value。

因此，在使用赋值语句往dict中添加元素时，为了避免不必要的覆盖问题，我们需要先判断key是否存在，然后再做更新。

## Python删除dict元素

当同学转校时，我们需要把同学的成绩从已有的成绩dict中删除，这个时候我们就需要学习如何删除dict中的元素。
dict提供便捷的`pop()`方法，允许我们快速删除元素，pop()方法需要指定需要删除的元素的key，并返回对应的value。
假设Alice转校了，需要把Alice的成绩删除，可以这样写：

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
print(d) # ==> {'Alice': 45, 'Bob': 60, 'Candy': 75, 'David': 86, 'Ellena': 49}
alice_score= d.pop('Alice')
print(alice_score) # ==> 45
print(d) # ==> {'Bob': 60, 'Candy': 75, 'David': 86, 'Ellena': 49}
```

需要注意的是，pop()方法的参数是dict中的key，当key不存在时，同样会引起错误。比如在上述操作中，已经把Alice的成绩删除了，假如再次pop('Alice')，将会引发错误。

```
d.pop('Alice')
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Alice'
```

## Python dict的特点

### **查找速度快**

dict的第一个特点是查找速度快，无论dict有10个元素还是10万个元素，查找速度都一样。而list的查找速度随着元素增加而逐渐下降。
不过dict的查找速度快不是没有代价的，dict的缺点是占用内存大，还会浪费很多内容，list正好相反，占用内存小，但是查找速度慢。

### **有序与无序**

在Python3.5之前，dict中的元素是无序的，也就是dict中元素的插入顺序和打印顺序未必一致，比如使用Python3.5之前的版本执行以下代码：

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
print(d) # ==> {'Bob': 60, 'Ellena': 49, 'Alice': 45, 'Candy': 75, 'David': 86}
```

可以看到，打印的顺序和定义的顺序并不一致。
但是在Python3.6、Python3.7版本中，却得到了有序的结果。

```
print(d) # ==> {'Alice': 45, 'Bob': 60, 'Candy': 75, 'David': 86, 'Ellena': 49}
```

为什么在不同的版本中，会得到不一样的结果呢？这是因为底层的实现发生了改变，我们可以认为在Python3.6的版本以后，dict是有序的，但是一般而言，为了避免不必要的误解，一般在需要有序的dict时，我们会使用一种叫做Ordereddict的字典，来确保有序。

### **key不可变**

对于基础数据类型，字符串、数字等，这些都是不可变的，可以作为dict的key，而对于复杂数据类型，经过前面的学习，我们知道tuple是不可变的，list是可变的，因此tuple可以作为dict的key，但是list不可以作为dict的key，否则将会报错。

```
key = (1, 2, 3) # 以tuple作为key
d[key] = True
key = [1, 2, 3]
d[key] = True
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

如上所示，如果将list作为dict的key，将会引起错误。
由于dict是按 key 查找，所以，在一个dict中，key不能重复。

## **Python遍历dict**

通过直接`print(d)`，我们打印出来的是完整的一个dict；有时候，我们需要把dict中m一定条件的元素打印出来，比如成绩超过60的，在这种情况下，我们需要则需要遍历dict（这种时候需要使用for循环），并通过条件判断把满足条件的打印出来。
遍历dict有两种方法， 第一种是遍历dict的所有key，并通过key获得对应的value。

```
d = {
    'Alice': 45,
    'Bob': 60,
    'Candy': 75,
    'David': 86,
    'Ellena': 49
}
for key in d: # 遍历d的key
    value = d[key]
    if value > 60:
        print(key, value)
# ==> Candy 75
# ==> David 86
```

第二种方法是通过dict提供的`items()`方法，`items()`方法会返回dict中所有的元素，每个元素包含key和value。

```
for key, value in d.items():
    if value > 60:
        print(key, value)
# ==> Candy 75
# ==> David 86
```

## Python操作dict的其他方法

除了前面学习的增删改查，dict还提供了非常多的工具函数帮助我们方便快捷的使用dict。

### **获取dict的所有key**

dict提供keys()函数，可以返回dict中所有的key。

```
d = {'Alice': [50, 61, 66], 'Bob': [80, 61, 66], 'Candy': [88, 75, 90]}
for key in d.keys():
    print(key)
# ==> Alice
# ==> Bob
# ==> Candy
```

### **获取dict所有的value**

dict提供values()函数，可以返回dict中所有的value。

```
d = {'Alice': [50, 61, 66], 'Bob': [80, 61, 66], 'Candy': [88, 75, 90]}
for key in d.values():
    print(key)
# ==> [50, 61, 66]
# ==> [80, 61, 66]
# ==> [88, 75, 90]
```

### **清除所有元素**

dict提供clear()函数，可以直接清除dict中所有的元素。

```
d = {'Alice': [50, 61, 66], 'Bob': [80, 61, 66], 'Candy': [88, 75, 90]}
print(d) # ==> {'Alice': [50, 61, 66], 'Bob': [80, 61, 66], 'Candy': [88, 75, 90]}
d.clear()
print(d) # ==> {}
```

# Python的Set容器

## 什么是set

在前面，我们学习了dict，知道dict的key是不重复的，当我们往dict里添加一个相同key的value时，新的value将会覆盖旧的value。
有的时候，我们只想要 dict 的 key，不关心 key 对应的 value，目的就是保证这个集合的元素不会重复，这时，set就派上用场了。
set和list类似，拥有一系列元素，但是set和list不一样，set里面的元素是不允许重复的，而list里面可以包含相同的元素；set与list的另一个区别是，set里面的元素是没有顺序的。
创建set的方式是使用`set()`，并传入一个list，list的元素将会被转换成set的元素。

```
s = set([1, 4, 3, 2, 5])
print(s) # ==> set([1, 2, 3, 4, 5])
```

需要注意的是，上述打印的形式类似 list， 但它不是 list，仔细看还可以发现，打印的顺序和原始 list 的顺序有可能是不同的，因为set内部存储的元素是无序的。
另外，set不能包含重复的元素，我们传入重复的元素看看会发生什么。

```
s = set([1, 4, 3, 2, 5, 4, 2, 3, 1])
print(s) # ==> set([1, 2, 3, 4, 5])
```

可以看到，在传入set()的list中，包含了重复的元素，但是打印的时候，相同的元素只保留了一个，重复的元素都被去掉了，这是set的一个重要特点。

## Python读取set元素

由于set里面的元素是没有顺序的，因此我们不能像list那样通过索引来访问。访问set中的某个元素实际上就是判断一个元素是否在set中，这个时候我们可以使用in来判断某个元素是否在set中。
比如，存储了班里同学名字的set。

```
names = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
name_set = set(names)
```

请问'Alice'是班里面的同学吗？

```
'Alice' in name_set # ==> True
```

请问'Bobby'是班里面的同学吗？

```
'Bobby' in name_set # ==>False
```

请问'bob'是班里面的同学吗？

```
'bob' in name_set # ==> False
```

这个时候是否输出了不符合预期的结果？'Bob'是在name_set里面的，为什么输出了False呢？这是因为set元素是区分大小写的，必须大小写完全匹配，才能判断该元素在set里面。

## Python添加set元素

我们通过set()传入list的方法创建了set，如果set在使用过程中需要往里面添加元素，这个时候应该怎么添加呢？
set提供了add()方法，我们可以使用add()方法，往set里面添加元素。
比如，班里面来了新的同学，名字叫Gina。

```
names = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
name_set = set(names)
name_set.add('Gina')
print(name_set) # ==> set(['Gina', 'Alice', 'Candy', 'David', 'Ellena', 'Bob'])
```

可以看到，'Gina'已经添加到name_set里面去了。对于set，如果添加一个已经存在的元素，不会报错，也不会改变什么。

```
names = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
name_set = set(names)
name_set.add('Alice')
print(name_set) # ==> set(['Bob', 'Ellena', 'Alice', 'Candy', 'David'])
```

有些时候需要批量往set里面添加元素，如果一个一个add是比较麻烦的，有没有批量往set里面添加元素的方法呢？
set提供了update()方法，可以一次性给set添加多个元素。
比如，新来了一批同学，名字分别是['Hally', 'Isen', 'Jenny', 'Karl']，则可以使用update()方法，批量往set中添加。

```
names = ['Alice', 'Bob', 'Candy', 'David', 'Ellena']
new_names = ['Hally', 'Isen', 'Jenny', 'Karl']
name_set = set(names)
name_set.update(new_names) # ==> set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
print(name_set)
```

## Python删除set元素

和list、dict一样，有时候我们也需要考虑删除set的元素。
set提供了remove()方法允许我们删除set中的元素。

```
name_set = set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.remove('Jenny')
print(name_set) # ==> set(['Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
```

需要注意的是，如果remove的元素不在set里面的话，那么将会引发错误。

```
name_set = set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.remove('Jenny')
print(name_set) # ==> set(['Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.remove('Jenny') # ==> 重复remove 'Jenny'
# 引起错误
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Jenny'
```

因此，使用remove()方法，我们需要格外小心，需要提前判断要remove()的元素是否在set里面，确保存在后，再进行remove。

## Python 操作set的其他方法

### **不会报错的删除方法discard()**

除了使用remove()方法删除元素以外，还可以使用discard()方法删除元素，并且，和remove()不同的是，当元素不存在时，使用discard()并不会引发错误，所以使用discard()是更加高效的一个方法。

```
name_set = set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.discard('Jenny')
print(name_set) # ==> set(['Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.discard('Jenny')
print(name_set) # ==> set(['Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl']
```

### **清除所有元素的方法clear()**

和dict一样，set也提供了clear()方法，可以快速清除set中的所有元素。

```
name_set = set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
print(name_set) # ==> set(['Jenny', 'Ellena', 'Alice', 'Candy', 'David', 'Hally', 'Bob', 'Isen', 'Karl'])
name_set.clear()
print(name_set) # ==> set([])
```

### **集合的子集和超集**

set提供方法判断两个set之间的关系，比如两个集合set，判断其中一个set是否为另外一个set的子集或者超集。

```
s1 = set([1, 2, 3, 4, 5])
s2 = set([1, 2, 3, 4, 5, 6, 7, 8, 9])
# 判断s1是否为s2的子集
s1.issubset(s2) # ==> True
# 判断s2是否为s1的超集
s2.issuperset(s1) # ==> True
```

### **判断集合是否重合**

有时候需要判断两个集合是否有重合的地方，如果使用传统的方法，需要使用for循环一个一个的去判断，非常麻烦，set提供`isdisjoint()`方法，可以快速判断两个集合是否有重合，如果有重合，返回False，否则返回True。

```
s1 = set([1, 2, 3, 4, 5])
s2 = set([1, 2, 3, 4, 5, 6, 7, 8, 9])
s1.isdisjoint(s2) # ==> False，因为有重复元素1、2、3、4、5
```

# Python的函数

## 什么是函数

对于什么是函数，其实在前面的学习过程当中，已经多次接触到函数了，比如在set里面，使用remove()函数进行元素的删除，使用add()函数添加元素，使用update()函数批量添加元素，但是至今为止，我们都没有对函数有个充分的认识。本章，我们将具体学习函数。
我们知道圆的面积计算公式为：

```
S = πr²
```

当我们知道半径r的值时，就可以通过公式计算出面积，假设我们需要计算3个不同大小的圆的面积：

```
r1 = 12.34
r2 = 9.08
r3 = 73.1
s1 = 3.14 * r1 * r1
s2 = 3.14 * r2 * r2
s3 = 3.14 * r3 * r3
```

可以看到，在上述代码中，出现了几乎完全重复的代码，每次计算圆的面积的时候我们都是通过`3.14*x*x`（其中x是圆的半径）的方式计算出来的，这样写不仅非常麻烦，而且，当我们需要提高圆周率的精度时，把3.14改成3.14159265359的时候，我们需要修改涉及到的三行代码。
因此，我们可以使用函数，把重复的逻辑代码封装起来，这样子，我们就不需要每次计算的时候，都写`3.14*x*x`这样的代码了；当我们使用函数的时候，我们只需要定义一次，就可以多次使用。
我们把封装重复逻辑代码的过程就做抽象，抽象是数学中非常常见的概念。
比如：计算数列的和，比如：1 + 2 + 3 + ... + 100，写起来十分不方便，于是数学家发明了求和符号∑，可以把1 + 2 + 3 + ... + 100记作：

![image-20210929133727917](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210929133727917.png)

这种抽象记法非常强大，因为我们看到∑就可以理解成求和，而不是还原成低级的加法运算。
而且，这种抽象记法是可扩展的，比如：

![image-20210929133743234](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210929133743234.png)

还原成加法运算就变成了：

```
(1 x 1 + 1) + (2 x 2 + 1) + (3 x 3 + 1) + ... + (100 x 100 + 1)
```

可见，借助抽象，我们才能不关心底层的具体计算过程，而直接在更高的层次上思考问题。
写计算机程序也是一样，函数就是最基本的一种代码抽象的方式。
Python不但能非常灵活地定义函数，而且本身内置了很多有用的函数，可以直接调用。

## **Python调用函数**

Python内置了很多有用的函数，我们可以直接调用。比如前面求list的长度len()函数等等，都是Python内置的函数，我们经常会使用到它们。
在这个文档里面，列举了Python内置的大部分函数，同学们有兴趣可以参考看看。

```
https://docs.python.org/3/library/functions.html
```

要调用一个函数，需要知道函数的名称和参数，比如求绝对值的函数 abs()，它接收一个参数。
对于abs()函数，abs就是函数的名称，括号()内，就是函数的参数，当函数没有参数时，默认就是一个空括号。**abs接收一个参数，这个参数就是需要求绝对值的数，这个参数可以是整数，也可以是浮点数**

```
abs(-100) # ==> 100
abs(20) # ==> 20
abs(-3.14159) # ==> 3.14159
```

需要注意的是，传递的参数数量一定要和函数要求的一致，不然将会引起错误，比如，如果在abs()函数中传入两个参数。

```
abs(1, 2)
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: abs() takes exactly one argument (2 given)
```

在错误提示中，清晰的说明了abs()函数只接收一个参数，但是却传递了两个参数，所以引起了错误。
其次，如果传入的参数数量是对的，但是参数的类型不能被函数所接受，也会引起错误，比如：求绝对值的函数abs()，只有数字才拥有绝对值，如果传递一个字符串进去，将会引起错误。

```
abs('3.1415926')
# 报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: bad operand type for abs(): 'str'
```

这里错误提示说，str类型是错误的参数类型。
除了abs()函数，还有很多常见的函数，比如cmp()函数，可以比较两个数的大小，这个时候，cmp()函数就接收两个参数。
对于cmp(x, y)，如果x < y 返回 -1，如果x == y 函数返回0，如果x > y函数返回1。

```
cmp(1, 2) # ==> -1
cmp(2, 1) # ==> 1
cmp(3, 3) # ==> 0
```

还有基础数据类型的转换函数，int()函数可以将合法的其它类型数据转换为整数，str()函数可以将其它类型的数据转换为字符串。

```
int('123') # ==> 123
int(12.34) # ==> 12

str(123) # ==> '123'
str(1.23) # ==> '1.23'
```

在学习Python的过程中，我们将会接触到越来越多的Python内置函数，这些内置函数提供了非常有用的功能，大大降低我们编程的难度。

## Python定义函数

除了使用Python内置的函数以外，在编程过程中，我们也经常需要自己定义函数。
在Python中，定义一个函数要使用 def 语句，依次写出函数名、括号()、括号中的参数和冒号:，然后，在缩进块中编写函数体，函数的返回值用 return 语句返回。
我们以定义一个求绝对值的函数my_abs函数为例：

```
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x
```

请注意，return表示返回的意思，函数体内部的语句在执行时，一旦执行到return时，函数就执行完毕，并将结果返回。因此，函数内部通过条件判断和循环可以实现非常复杂的逻辑。
我们继续定义一个求列表list所有元素的和的函数：

```
def list_sum(L):
    result = 0
    for num in L:
        result = result + num
    return result
```

这样子我们就定义了一个sum_list()的函数，注意，在最后return，我们把求和的结果result返回了，这样就可以在外部调用函数后获得result。

```
L = [1, 3, 5, 7, 9, 11]
result =list_sum(L) # 调用定义的sum_list函数并获得return返回的结果
print(result)
```

## Python函数返回值

在上一节课中，我们在函数里面使用return返回了计算的结果，在外部调用这个函数的时候，就可以接收到结果。
有时候函数是没有返回结果的，这个时候从函数获取到的是一个空值None。
我们对list_sum()这个函数进行简单的修改，在函数内把结果打印出来，不通过return返回结果。

```
def list_sum(l):
    result = 0
    for num in l:
        result = result + num
    print('result is {}'.format(result))
    return

l = [1, 3, 5, 7, 9, 11]
result =list_sum(l) # 调用定义的sum_list函数并获得return返回的结果
print(result) # ==> None
```

在`print(result)`中，我们得到`None`的结果，这是合理的，因为在函数内部，我们把结果打印出来了，但是没有把结果返回。
除了返回None、一个值以外，函数也可以返回多个值，在函数中，如果需要返回多个值，多个值之间使用逗号分隔即可，但是需要注意顺序。
比如，定义一个函数data_of_square，接收边长一个参数，同时返回正方形的周长和面积。

```
def data_of_square(side):
    C = 4 * side
    S = side * side
    return C, S

C, S = data_of_square(16)
print('周长 = {}'.format(C)) # ==> 周长 = 64
print('面积 = {}'.format(S)) # ==> 面积 = 256
```

也可以使用一个值存储函数返回的多值结果。

```
result = data_of_square(16)
print(result) # ==> (64, 256)
```

注意打印的result，其实它是tuple类型，如果我们需要取出结果中的周长或者面积，使用对应位置的下标就可以获得对应的结果。

```
result = data_of_square(16)
C = result[0]
S = result[1]
print('周长 = {}'.format(C)) # ==> 周长 = 64
print('面积 = {}'.format(S)) # ==> 面积 = 256
```

## Python递归函数

在函数内部，还可以调用其他函数，比如实现函数data_of_square的时候，它接收边长一个参数，同时返回正方形的周长和面积，而求周长和求面积是完全独立的逻辑，可以定义成两个新的函数，然后在data_of_square函数中再调用这两个函数，得到结果并返回。

```
def square_area(side):
    return side * side

def square_perimeter(side):
    return 4 * side

def data_of_square(side):
    C = square_perimeter(side)
    S = square_area(side)
    return C, S
```

在函数内部调用其他函数，是非常常见的，通过合理拆分逻辑，可以降低程序的复杂度。如果在一个函数内部调用其自身，这个函数就是递归函数。
举个例子，我们来计算阶乘 n! = 1 * 2 * 3 * ... * n，用函数 fact(n)表示，可以看出：

```
fact(n) = n! = 1 * 2 * 3 * ... * (n-1) * n = (n-1)! * n = fact(n-1) * n
```

所以，fact(n)可以表示为 n * fact(n-1)，只有n=1时需要特殊处理。
于是，fact(n)用递归的方式写出来就是：

```
def fact(n):
    if n==1:
        return 1
    return n * fact(n - 1)
```

这个fact(n)就是递归函数，可以试试计算得到的结果。

```
fact(1) # ==> 1
fact(5) # ==> 120
```

我们可以拆解fact(5)计算的详细逻辑

```
===> fact(5)
===> 5 * fact(4)
===> 5 * (4 * fact(3))
===> 5 * (4 * (3 * fact(2)))
===> 5 * (4 * (3 * (2 * fact(1))))
===> 5 * (4 * (3 * (2 * 1)))
===> 5 * (4 * (3 * 2))
===> 5 * (4 * 6)
===> 5 * 24
===> 120
```

递归函数的优点是定义简单，逻辑清晰。理论上，所有的递归函数都可以写成循环的方式，但循环的逻辑不如递归清晰。
使用递归函数需要注意防止栈溢出。在计算机中，函数调用是通过栈（stack）这种数据结构实现的，每当进入一个函数调用，栈就会加一层栈帧，每当函数返回，栈就会减一层栈帧。由于栈的大小不是无限的，所以，递归调用的次数过多，会导致栈溢出。可以试试计算 fact(10000)。

```
Traceback (most recent call last):
RecursionError: maximum recursion depth exceeded in comparison
```

## Python函数参数

函数参数是需要传递给函数内部的数据，在前面，我们已经简单接触了函数的参数，现在我们正式来认识它。
函数参数可以是任意的数据类型，只要函数内部逻辑可以处理即可。

```
def print_param(param):
    print(param)
```

对于print_param函数，由于函数的逻辑是直接打印参数，并没有做任何别的逻辑，所以这个函数可以接受整数、浮点数、list、tuple、dict等等的数据类型。

```
print_param(1)
print_param('3.1415926')
print_param([1, 2, 3, 4, 5])
```

但是，有时候由于函数的实现关系，需要特定的参数，就比如前面实现的求绝对值的函数my_abs()，如果传递一个字符串，就会引起错误。

```
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x

my_abs('str param')
# 报错
TypeError: '>=' not supported between instances of 'str' and 'int'
```

为了保证函数的正常运行，有时候需要对函数入参进行类型的校验，Python提供isinstance()函数，可以判断参数类型，它接收两个参数，第一个是需要判断的参数，第二个是类型。

```
isinstance(100, int) # ==> True
isinstance(100.0, int) # ==> False
isinstance('3.1415926', str) # ==> True
```

有了isinstance，就可以优化my_abs函数，不在里面运行出错了。

```
def my_abs(x):
    if not isinstance(x, int) or not isinstance(x, float):
        print('param type error.')
        return None
    if x >= 0:
        return x
    else:
        return -x
```

## Python函数使用默认参数

定义函数的时候，还可以有默认参数，默认参数的意思是当这个参数没有传递的时候，参数就使用定义时的默认值。
例如Python自带的 int() 函数，其实就有两个参数，我们既可以传一个参数，又可以传两个参数：

```
int('123') # ==> 123
int('123', 8) # ==> 83
```

int()函数的第二个参数是转换进制base，如果不传，默认是十进制 (base=10)，如果传了，就用传入的参数。
可见，函数的默认参数的作用是简化调用，你只需要把必须的参数传进去。但是在需要的时候，又可以传入额外的参数来覆盖默认参数值。
我们来定义一个计算 x 的N次方的函数:

```
def power(x, n):
    s = 1
    while n > 0:
        n = n - 1
        s = s * x
    return s
```

假设计算平方的次数最多，我们就可以把 n 的默认值设定为 2：

```
def power(x, n=2):
    s = 1
    while n > 0:
        n = n - 1
        s = s * x
    return s
```

这样一来，计算平方就不需要传入两个参数了：

```
power(5) # ==> 25
```

另外需要注意的是，由于函数的参数按从左到右的顺序匹配，所以默认参数只能定义在必需参数的后面，否则将会出现错误。

```
# 错误的定义
def power(n=2, x):
    s = 1
    while n > 0:
        n = n - 1
        s = s * x
    return s
```

## Python函数使用可变参数

除了默认参数，Python函数还接收一种参数叫做可变参数，可变参数即任意个参数的意思，可变参数通常使用`*args`来表示。

```
def func(*args):
    print('args length = {}, args = {}'.format(len(args), args))

func('a') # ==> args length = 1, args = ('a',)
func('a', 'b') # ==> args length = 2, args = ('a', 'b')
func('a', 'b', 'c') # ==> args length = 3, args = ('a', 'b', 'c')
```

注意，在使用上，Python会把可变参数定义为一个tuple，所以在函数内部，把可变参数当作tuple来使用就可以了，比如可以通过位置下标取出对应的元素等。
定义可变参数的目的也是为了简化调用。假设我们要计算任意个数的平均值，就可以定义一个可变参数：

```
def average(*args):
    sum = 0
    for item in args:
        sum += item
    avg = sum / len(args)
    return avg
```

这样，在调用的时候，我们就可以这样写：

```
average(1, 2) # ==> 1.5
average(1, 2, 2, 3, 4) # ==> 2.4
average()
# 报错
Traceback (most recent call last):
ZeroDivisionError: division by zero
```

在执行`average()`的时候，却报错了，这是因为在使用可变参数时，没有考虑周全导致的，因为可变参数的长度可能是0，当长度为0的时候，就会出现除0错误。因此需要添加保护的逻辑，这是同学在使用过程中需要特别注意的。

## Python函数使用可变关键字参数

可变参数在使用上确实方便，函数会把可变参数当作tuple去处理，tuple在使用上有一定的局限性，比如有时候想找到特定位置的参数，只能通过下标的方式去寻找，如果顺序发生变化得时候，下标就会失效，函数逻辑就得重新修改实现。
Python函数提供可变关键字参数，对于可变关键字参数，可以通过关键字的名字key找到对应的参数值，想想这和我们之前学习过的什么类似？是的没错，dict，Python会把可变关键字参数当作dict去处理；对于可变关键字参数，一般使用**kwargs来表示。
例如，想要打印一个同学的信息，可以这样处理：

```
def info(**kwargs):
    print('name: {}, gender: {}, age: {}'.format(kwargs.get('name'), kwargs.get('gender'), kwargs.get('age')))

info(name = 'Alice', gender = 'girl', age = 16)
```

对于一个拥有必需参数，默认参数，可变参数，可变关键字参数的函数，定义顺序是这样的：

```
def func(param1, param2, param3 = None, *args, **kwargs):
    print(param1)
    print(param2)
    print(param3)
    print(args)
    print(kwargs)

func(100, 200, 300, 400, 500, name = 'Alice', score = 100)
# ==> 100
# ==> 200
# ==> 300
# ==> (400, 500)
# ==> {'name': 'Alice', 'score': 100}
```

当然，这么多类型的参数，很容易导致出错，在实际使用上，不建议定义这么多的参数。

# Python面向对象编程

## Python类的定义与实例化

 

在Python中，通过class关键字定义一个类，比如我们需要定义一个人的类。按照 Python 的编程习惯，类名以大写字母开头。因此可以这样定义：

```
 class Person:  pass
```

注意，在这个Person类的定义里面，并没有继承任何类，除了这样定义以外，还可以有以下两种定义方式。

```
 class Person(): pass  class Person(object):  pass
```

这三种情况有什么区别呢？在Python3中，是没有区别的，但是在Python2中，则有一定的区别。
在Python2中，对于第一种定义的方法，Person类只有有限的几个内建函数'__doc__', '__module__', 'name'，而对于第二种、第三种定义的方法，则会继承Python object对象的更多的内建函数，可以更便捷的操作对象。这是Python2版本的差异。在Python3中，我们只需要知道这三种方式都可以定义一个类即可。


定义了类之后，就可以对类进行实例化了，实例化是指，把抽象的类，赋予实物的过程。比如，定义好Person这个类后，就可以实例化多个Person出来了。
创建实例使用类名+()，类似函数调用的形式创建：

```
 class Person(object):  pass xiaohong = Person() xiaoming = Person()
```

## Python实例属性的定义

虽然前面我们已经通过Person类创建出xiaoming、xiaohong等实例，但是这些实例看上去并没有任何区别。在现实世界中，一个人拥有名字、性别、年龄等等的信息，在Python中，可以通过以下的方式赋予实例这些属性，并且把这些属性打印出来。

```
xiaohong.name = 'xiaohong'
xiaohong.sex = 'girl'
xiaohong.age = 13

print(xiaohong.name)
print(xiaohong.sex)
print(xiaohong.age)
```

除此以外，这些属性也可以和普通变量一样进行运算。比如xiaohong长大了一岁：

```
xiaohong.age = xiaohong.age + 1
```

## Python实例属性的初始化

通过前面的方式定义一个实例的属性非常方便，但也有一些问题。
首先，如果定义属性的过程中使用了不同的属性名字，比如性别，前者使用了sex，后者使用了gender，那对于一个类的不同实例，存储一个信息就用了两个不同的属性，在后面将会难以维护。
其次，名字、性别、年龄等等，都是人的基本信息，在抽象一个类的时候，理应包含这些信息。
在定义 Person 类时，可以为Person类添加一个特殊的__init__()方法，当创建实例时，__init__()方法被自动调用，我们就能在此为每个实例都统一加上以下属性：

```
class Person(object):
    def __init__(self, name, sex, age):
        self.name = name
        self.sex = sex
        self.age = age
```

需要注意的是，__init__() 方法的第一个参数必须是 self（也可以用别的名字，但建议使用习惯用法），后续参数则可以自由指定，和定义函数没有任何区别。
定义类后，就可以相应的实例化对象了，需要注意的是，在实例化的时候，需要提供除self以外的所有参数。

```
xiaoming = Person('Xiao Ming', 'boy', 13)
xiaohong = Person('Xiao Hong', 'girl', 14)
```

而访问这些属性的方式和之前的一样：

```
print(xiaohong.name)
print(xiaohong.sex)
print(xiaohong.age)
# 但当访问不存在的属性时，依然会报错
print(xiaohong.birth)
```

要特别注意的是，初学者定义__init__()方法常常忘记了 self 参数，比如如下的定义：

```
class Person(object):
    def __init__(name, sex, age):
        pass
```

这种情况下，如果还是如下实例化，将会报错。

```
xiaoming = Person('Xiao Ming', 'boy', 13)
xiaohong = Person('Xiao Hong', 'girl', 14)

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: __init__() takes 3 positional arguments but 4 were given
```

## Python类属性

类和实例对象是有区别的，类是抽象，是模板，而实例则是根据类创建的对象，比如类：动物，只是一个抽象，并没有动物的详细信息，而猫、狗等，则是具体的动物，是类的对象。


在前面，实例对象绑定的属性只属于这个实例，绑定在一个实例上的属性不会影响其它实例；同样的，类也可以绑定属性，但是类的属性不属于任何一个对象，而是属于这个类。如果在类上绑定一个属性，则所有实例都可以访问类的属性，并且，所有实例访问的类属性都是同一个！也就是说，实例属性每个实例各自拥有，互相独立，而类属性有且只有一份。


定义类属性可以直接在 class 中定义，比如在前面的Animal类中，加入地域的类属性：

```
class Animal(object):
    localtion = 'Asia'
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

在上面的代码中，localtion就是属于Animal这个类的类属性，此后，通过Animal()实例化的所有对象，都可以访问到localtion，并且得到唯一的结果。

```
dog = Animal('wangwang', 1)
cat = Animal('mimi', 3)
print(dog.localtion) # ==> Asia
print(cat.localtion) # ==> Asia
# 类属性，也可以通过类名直接访问
print(Animal.localtion) # ==> Asia
```

类属性也是可以动态添加和修改的，需要注意的是，因为类属性只有一份，所以改变了，所有实例可以访问到的类属性都会变更：

```
Animal.localtion = 'Africa'
print(cat.localtion) # ==>Africa
print(dog.localtion) # ==>Africa
```

## Python类属性和实例属性的优先级

可以看到，属性可以分为类属性和实例属性，那么问题就来了，如果类属性和实例属性名字相同时，会怎么样，这就涉及Python中类属性和实例属性的优先级的问题了。
我们可以做一个实验，在前面类定义的基础上，在实例属性中，也初始化一个localtion的属性。

```
class Animal(object):
    localtion = 'Asia'
    def __init__(self, name, age, localtion):
        self.name = name
        self.age = age
        self.localtion = localtion
```

接着我们初始化两个实例，并把localtion打印出来。

```
dog = Animal('wangwang', 1, 'GuangDong')
cat = Animal('mimi', 3, 'ChongQing')
print(dog.localtion) # ==> GuangDong
print(cat.localtion) # ==> ChongQing
print(Animal.localtion) # ==> Asia
```

可见，在类属性和实例属性同时存在的情况下，实例属性的优先级是要高于类属性的，在操作实例的时候，优先是操作实例的属性。
另外，当实例没有和类同名的时候，通过实例对象，依然可以访问到类属性。

```
class Animal(object):
    localtion = 'Asia'
    def __init__(self, name, age):
        self.name = name
        self.age = age

cat = Animal('mimi', 3)
print(cat.localtion) # ==> Asia
```

那通过实例，可不可以修改类属性呢？我们来尝试一下：

```
cat.localtion = 'Africa'
print(Animal.localtion) # ==> Asia
```

这里依然打印了Asia，可见通过实例是无法修改类的属性的，事实上，通过实例方法修改类属性，只是给实例绑定了一个对应的实例属性：

```
# 新增的实例属性
print(cat.localtion) # ==> Africa
```

因此，需要特别注意，尽量不要通过实例来修改类属性，否则很容易引发意想不到的错误。

## Python中的访问限制

并不是所有的属性都可以被外部访问的，这种不能被外部访问的属性称为私有属性。私有属性是以双下划线'__'开头的属性。

```
# 类私有属性
class Animal(object):
    __localtion = 'Asia'

print(Animal.__localtion)

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: type object 'Animal' has no attribute '__localtion'
```

 

```
# 实例私有属性
class Animal(object):
    def __init__(self, name, age, localtion):
        self.name = name
        self.age = age
        self.__localtion = localtion

dog = Animal('wangwang', 1, 'GuangDong')
print(dog.name) # ==> wangwang
print(dog.age) # ==> 1
print(dog.__localtion)

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Animal' object has no attribute '__localtion'
```

在外部访问私有属性将会抛出异常，提示没有这个属性。
虽然私有属性无法从外部访问，但是，从类的内部是可以访问的。私有属性是为了保护类或实例属性不被外部污染而设计的。

## Python定义实例方法

上一节课提到，私有属性没有办法从外部访问，只能在类的内部操作；那如果外部需要操作私有属性怎么办？这个时候可以通过定义类或者实例的方法来操作私有属性，本节课先来介绍实例方法。
实例的方法指的就是在类中定义的函数，实例方法的第一个参数永远都是self，self是一个引用，指向调用该方法的实例对象本身，除此以外，其他参数和普通函数是完全一样的。

```
class Person(object):

    def __init__(self, name):
        self.__name = name

    def get_name(self):
        return self.__name
```

在上面的定义，**name是实例的私有属性，从外部是无法访问的，而get_name(self) 就是一个实例方法，在实例方法里面是可以操作私有属性的，注意，它的第一个参数是self。**
**另外，**__init__(self, name)其实也可看做是一个特殊的实例方法。
通过定义get_name(self)方法，在外部就可以通过这个方法访问私有属性了。

```
p = Person('Alice')
print(p.get_name()) # ==> Alice
```

注意，在外部调用实例方法时，是不需要显式传递self参数的。
另外，通过定义实例方法来操作私有属性的这种方法是推荐的，这种数据封装的形式除了能保护内部数据一致性外，还可以简化外部调用的难度。
当然，实例方法并不仅仅是为私有属性服务的，我们可以把和类的实例有关的操作都抽象成实例方法，比如：打印实例的详细信息等等。

```
class Animal(object):
    def __init__(self, name, age, localtion):
        self.name = name
        self.age = age
        self.localtion = localtion

    def get_info(self):
        return 'name = {}, age = {}, localtion = {}'.format(self.name, self.age, self.localtion)

dog = Animal('wangwang', 1, 'GuangDong')
print(dog.get_info())
```

## Python定义类方法

在上一节课，为了操作实例对象的私有属性，我们定义了实例方法；同样的，如果需要需要操作类的私有属性，则应该定义类的方法。
默认的，在class中定义的全部是实例方法，实例方法第一个参数 self 是实例本身。
要在class中定义类方法，需要这么写：

```
class Animal(object):
    __localtion = 'Asia'
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def set_localtion(cls, localtion):
        cls.__localtion = localtion

    @classmethod
    def get_localtion(cls):
        return cls.__localtion

print(Animal.get_localtion()) # ==> Asia
Animal.set_localtion('Afica')
print(Animal.get_localtion()) # ==> Africa
```

和实例方法不同的是，这里有两点需要特别注意：

1. 类方法需要使用@classmethod来标记为类方法，否则定义的还是实例方法
2. 类方法的第一个参数将传入类本身，通常将参数名命名为 cls，上面的 cls.__localtion 实际上相当于Animal.__localtion。

​    因为是在类上调用，而非实例上调用，因此类方法无法获得任何实例变量，只能获得类的引用。