



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
print(s1)、
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
        continue # 当num < 10 时，跳过后续循环代码，继续下一次循环
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

func(100, 200, 300, 400, 500, name = 'Alice', score = 100)0
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

#  Python类的继承

## Python继承类

对人类的抽象可以定义为Person类，而学生、老师等，也都是人类，所以，在Python当中，如果定义学生Student的类，可以继承Person类。

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender
```

接着定义Student类，在定义Student类的时候，由于继承了Person类，所以Student类自动拥有name、gender属性，因此，在定义Student类的时候，只需要把额外的属性加上即可。

```
class Student(Person):
    def __init__(self, name, gender, score):
        super(Student, self).__init__(name, gender)
        self.score = score

student = Student('Alice', 'girl', 100)
print(student.name) # ==> Alice
print(student.gender) # ==> girl
print(student.score) # ==> 100
```

在定义继承类的时候，有几点是需要注意的：

1. class Student()定义的时候，需要在括号内写明继承的类Person
2. 在__init__()方法，需要调用super(Student, self).__init__(name, gender)，来初始化从父类继承过来的属性

## Python判断类型

随着我们学习步伐的前进，我们的程序会出现越来越多的类型，有我们自己定义的类，也有Python自有的str、list、dict等，他们的本质都是都是Python中的一种数据类型，这时有必要去判断数据的类型，通过函数isinstance()可以判断一个变量的类型。

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender

class Student(Person):
    def __init__(self, name, gender, score):
        super(Student, self).__init__(name, gender)
        self.score = score

class Teacher(Person):
    def __init__(self, name, gender, course):
        super(Teacher, self).__init__(name, gender)
        self.course = course

p = Person('Tim', 'Male')
s = Student('Bob', 'Male', 88)
t = Teacher('Alice', 'Female', 'English')
```

当我们拿到变量 p、s、t 时，可以使用 isinstance 判断类型：

```
>>> isinstance(p, Person)
True # p是Person类型
>>> isinstance(p, Student)
False # p不是Student类型
>>> isinstance(p, Teacher)
False # p不是Teacher类型
```

这说明在继承链上，一个父类的实例不能是子类类型，因为子类比父类多了一些属性和方法。
我们再考察 s：

```
>>> isinstance(s, Person)
True # s是Person类型
>>> isinstance(s, Student)
True # s是Student类型
>>> isinstance(s, Teacher)
False # s不是Teacher类型
```

s 是Student类型，不是Teacher类型，这很容易理解。但是，s 也是Person类型，因为Student继承自Person，虽然它比Person多了一些属性和方法，但是，把 s 看成Person的实例也是可以的。

这说明在一条继承链上，一个实例可以看成它本身的类型，也可以看成它父类的类型。

isinstance也可以用于Python自有数据类型的判断。

```
s = 'this is a string.'
n = 10
isinstance(s, int) # ==> False
isinstance(n, str) # ==> False
```

## Python中的多态

类具有继承关系，并且子类类型可以向上转型看做父类类型，如果我们从 Person 派生出 Student和Teacher ，并都写了一个who() 方法：

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender
    def who(self):
        return 'I am a Person, my name is %s' % self.name

class Student(Person):
    def __init__(self, name, gender, score):
        super(Student, self).__init__(name, gender)
        self.score = score
    def who(self):
        return 'I am a Student, my name is %s' % self.name

class Teacher(Person):
    def __init__(self, name, gender, course):
        super(Teacher, self).__init__(name, gender)
        self.course = course
    def who(self):
        return 'I am a Teacher, my name is %s' % self.name
```

接着，我们分别把不同类型的who()函数结果打印出来：

```
p = Person('Tim', 'Male')
s = Student('Bob', 'Male', 88)
t = Teacher('Alice', 'Female', 'English')
```

运行结果：

```
I am a Person, my name is Tim
I am a Student, my name is Bob
I am a Teacher, my name is Alice
```

这种行为称为多态。从定义上来讲，Student和Teacher都拥有来自父类Person继承的who()方法，以及自己定义的who()方法。但是在实际调用的时候，会首先查找自身的定义，如果自身有定义，则优先使用自己定义的函数；如果没有定义，则顺着继承链向上找。

```
class Boss(Person):
    def __init__(self, name, gender,company):
        super(Boss, self).__init__(name, gender)
        self.company = company

b = Boss('Bob', 'Male', 'Alibaba')
b.who() # ==> I am a Person, my name is Bob
```

在Boss的定义类，没有定义who方法，所以会顺着继承链向上找到父类的who方法并且调用。

## **Python中的多重继承**

除了从一个父类继承外，Python允许从多个父类继承，称为多重继承。多重继承和单继承没有特别大的差异，只是在括号内加入多个需要继承的类的名字即可。

```
class A(object):
    def __init__(self, a):
        print ('init A...')
        self.a = a

class B(A):
    def __init__(self, a):
        super(B, self).__init__(a)
        print ('init B...')

class C(A):
    def __init__(self, a):
        super(C, self).__init__(a)
        print ('init C...')

class D(B, C):
    def __init__(self, a):
        super(D, self).__init__(a)
        print ('init D...')
```

多重继承的继承链就不是一棵树了，它像这样：



![image-20211001205026047](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20211001205026047.png)

从上图可知，A类被继承了连词，那么A的__init__()方法，是否会被调用两次呢？

```
>>> d = D('d')
init A...
init C...
init B...
init D...
```

实践证明，在多重继承里，A虽然被继承了两次，但是__init__()的方法只调用一次。

多重继承的目的是从两种继承树中分别选择并继承出子类，以便组合功能使用。
举个例子，Python的网络服务器有TCPServer、UDPServer、UnixStreamServer、UnixDatagramServer，而服务器运行模式有 多进程ForkingMixin 和 多线程ThreadingMixin两种。
要创建多进程模式的 TCPServer：

```
class MyTCPServer(TCPServer, ForkingMixin)
    pass
```

要创建多线程模式的 UDPServer：

```
class MyUDPServer(UDPServer, ThreadingMixin):
    pass
```

如果没有多重继承，要实现上述所有可能的组合需要 4x2=8 个子类。

## Python获取对象信息

在前面，我们通过isinstance()方法，可以判断一个对象是否是某个类型，从某种意义上来讲，通过isinstance()方法，我们获取到了一个对象的一些信息，那有没有别的方法可以获取到对象更多的信息呢？
通过type()函数，可以获得变量的类型。

```
n = 1
s = 'this is a string'
type(n) # ==> <class 'int'>
type(s) # ==> <class 'str'>
```

 

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender

class Student(Person):
    def __init__(self, name, gender, score):
        super(Student, self).__init__(name, gender)
        self.score = score

p = Person('Alice', 'Female')
s = Student('Bob', 'Male', 100)
type(p) # ==> <class '__main__.Person'>
type(s) # ==> <class '__main__.Student'>
```

通过dir()方法，可以获取变量的所有属性：

```
>>> n = 1
>>> dir(n)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', ...]
>>> s = 'this is a string'
>>> dir(s)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', ...]
```

在dir列出的属性中，有很多是以下划线开头和结尾的，这些都是特殊的方法，称为内建方法，在后面，我们还会学习这些方法。
而对于自定义对象：

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender
    def who(self):
        return 'I am a Person, my name is {}'.format(self.name)

p = Person('Alice', 'Female')
dir(p)

['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'gender', 'name', 'who']
```

对于实例变量，dir()返回所有实例属性，包括__class__这类有特殊意义的属性。注意到方法who也是p的一个属性。
dir()返回的属性是字符串列表，如果已知一个属性名称，要获取或者设置对象的属性，就需要用 getattr() 和 setattr( )函数了。

```
>>> getattr(p, 'name') # 获取name属性
'Alice'
>>> setattr(p, 'name', 'Adam') # 设置新的name属性
>>> s.name
'Adam'
>>> getattr(s, 'age') # 获取age属性，但是属性不存在，报错：
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Person' object has no attribute 'age'
>>> getattr(s, 'age', 20) # 获取age属性，如果属性不存在，就返回默认值20：
20
```

## Python类的__str__ 和 __repr__方法

对于Python的内建对象，比如int、dict、list等，通过str()方法，可以把这些对象转换为字符串对象输出。

```
num = 12
str(num) # ==> '12'
d = {1: 1, 2: 2}
str(d) # ==> '{1: 1, 2: 2}'
l = [1,2,3,4,5]
str(l) # ==> '[1, 2, 3, 4, 5]'
```

对于自定义对象，通过str()方法，同样可以得到对象所对应的字符串结果，只不过结果会有些难理解。

```
class Person:
    pass

bob = Person()
str(bob) # ==> '<__main__.Person object at 0x7fc77b859c50>'
```

<__main__.Person object at 0x7fc77b859c50>这个结果其实是Animal的实例cat在内存中的地址，这是相当难以理解的，不过引发思考的是，通过str()打印的数据，是怎么来的呢？
这其实是对象的内建方法__str__返回的。
通过dir()方法，我们可以把对象的所有方法打印出来。

```
>>> dir(list)
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

可以看到，int、dict、list等的内建对象都实现了自己的__str__()方法，可以把相应的字符串返回，如果我们的类也想把容易理解的字符串输出的话，那么我们也需要实现类的__str__()方法。

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender
    def __str__(self):
        return 'name: {}, gender: {}'.format(self.name, self.gender)

bob = Person('Bob', 'Male')
str(bob) # ==> 'name: Bob, gender: Male'
```

但是，对于直接在终端输入变量bob，得到的依然是这样结果。

```
>>> bob
<__main__.Person object at 0x7fc77b859cc0>
```

而对于int、list等的对象，直接输入变量也可得到可读的结果。

```
>>> num = 12
>>> str(num)
'12'
>>> d = {1: 1, 2: 2}
>>> d
{1: 1, 2: 2}
```

**__str__()函数似乎没有在自定义类Person中生效，这是为什么呢？**
这是因为 Python 定义了__str()__和__repr__()两种方法，__str()__用于显示给用户，而__repr__()用于显示给开发人员，当使用str()时，实际调用的是__str__()方法，而直接输入变量，调用的是__repr__()方法。

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender
    def __str__(self):
        return 'name: {}, gender: {}'.format(self.name, self.gender)
    def __repr__(self):
        return 'name: {}, gender: {}'.format(self.name, self.gender)

bob = Person('Bob', 'Male')
str(bob) # ==> 'name: Bob, gender: Male'
>>> bob
'name: Bob, gender: Male'
```

## Python类的__len__方法

对于列表List或者元组Tuple，通过内建方法len()，可以得出列表或者元组中元素的个数。如果一个类表现得像一个list，想使用len()函数来获取元素个数时，则需要实现__len__()方法。
比如我们实现一个班级Class的类，初始化把班级的同学名字列表传进去，希望len()函数可以返回班级同学的数量时，可以这样实现。

```
class Class:
    def __init__(self, students):
        self.students = students
    def __len__(self):
        return len(self.students)

students = ['Alice', 'Bob', 'Candy']
class_ = Class(students)
len(class_) # ==> 3
```

通过自定义__len__()方法，可以让len()函数返回相关的结果，如果没有定义__len__()方法的类使用len()函数获取长度时，将会引起异常。

```
class Class:
    def __init__(self, students):
        self.students = students

class_ = Class(students)
len(class_)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'Class' has no len()
```

## Python类的数学运算

事实上，Python很多的操作都是通过内建函数来实现的，比如最熟悉的加减乘除，都是通过内建函数来实现的，分别是`__add__`、`__sub__`、`__mul__`、`__truediv__`。因此，只要我们的自定义类实现了相关的内建函数，我们的类对象，也可以做到加减乘除。
对于有理数，我们可以使用Rational类来表示：

```
class Rational(object):
    def __init__(self, p, q):
        self.p = p
        self.q = q
```

其中，p、q 都是整数，表示有理数 p/q。
如果要让Rational进行加法运算，需要正确实现__add__：

```
class Rational(object):
    def __init__(self, p, q):
        self.p = p
        self.q = q
    def __add__(self, r):
        return Rational(self.p * r.q + self.q * r.p, self.q * r.q)
    def __str__(self):
        return '{}/{}'.format(self.p, self.q)
```

定义好后，就可以尝试一下有理数的加法了：

```
>>> r1 = Rational(1, 2)
>>> r2 = Rational(2, 3)
>>> print(r1 + r2)
7/6
```

需要注意__add__()函数，它有一个参数，表示的是运算的第二个操作数，比如：r1 + r2，那么在__add__()方法中的参数，r指的就是r2，这个参数是运算符重载的时候传递的。
另外，细心的同学可能注意到了，相比加减乘的特殊方法，除法的特殊方法名字较长__truediv__，并且含有true这样的描述，这其实和Python除法是有关系的。
Python的除法可以分为地板除（你没看错，就是地板）和普通除法，地板除的特殊方法是__floordiv__，普通除法是__truediv__。
地板除法和普通除法不一样，地板除法的结果只会向下取整数。

```
>>> num = 5
>>> num.__truediv__(3)
1.6666666666666667
>>> num.__floordiv__(3)
1 # 向下取整
>>> num = 7
>>> num.__floordiv__(3)
2
```

在运算中，普通除法使用/表示，而地板除使用//表示。

```
>>> 5 / 3
1.6666666666666667
>>> 5 // 3
1
```

## Python类的__slots__方法

由于Python是动态语言，任何实例在运行期都可以动态地添加属性。比如：

```
class Student(object):
    def __init__(self, name, gender, score):
        self.name = name
        self.gender = gender
        self.score = score
```

此时，Student类有三个属性，name、gender、score，由于是动态语言，在运行时，可以随意添加属性。

```
student = Student('Bob', 'Male', 99)
student.age = 12 # ==> 动态添加年龄age属性
```

如果要限制添加的属性，例如，Student类只允许添加 name、gender和score 这3个属性，就可以利用Python的一个特殊的__slots__来实现。

```
class Student(object):
    __slots__ = ('name', 'gender', 'score')
    def __init__(self, name, gender, score):
        self.name = name
        self.gender = gender
        self.score = score
```

使用__slots__ = ('name', 'gender', 'score') 限定Student类的属性，这个时候在外部再次添加动态属性age，将会报错。

```
>>> student = Student('Bob', 'Male', 99)
>>> student.age = 12 # ==> 动态添加年龄age属性
Traceback (most recent call last):
AttributeError: 'Student' object has no attribute 'age'
```

__slots__的目的是限制当前类所能拥有的属性，避免因为外部属性的操作导致类属性越来越难以管理。

## Python类的__call__方法

在Python中，函数其实是一个对象，我们可以将一个函数赋值给一个变量，而不改变函数的功能。

```
>>> f = abs
>>> f
<built-in function abs>
>>> abs
<built-in function abs>
>>> f.__name__
'abs'
>>> f(-123)
123
```

把内建函数abs()赋值给变量f之后，可以看到f就和abs一样，都是。
由于 f 可以被调用，所以，f 被称为可调用对象，而事实上，所有的函数都是可调用对象。
如果把一个类实例也变成一个可调用对象，可以实现一个特殊的方法__call__()。
例如，我们把Person类变成一个可调用对象：

```
class Person(object):
    def __init__(self, name, gender):
        self.name = name
        self.gender = gender

    def __call__(self, friend):
        print('My name is {}...'.format(self.name))
        print('My friend is {}...'.format(friend))
```

接着我们初始化一个Person对象，并对这个对象通过函数的方式调用：

```
>>> p = Person('Bob', 'Male')
>>> p('Alice') # ==> 用函数的方式调用Person类的实例p
My name is Bob...
My friend is Alice...
```

# Python的模块

## Python定义模块

Python语言本身提供了非常多的模块，比如数学模块math、cmath、decimal、statistics；文件模块pathlib、stat、shutil等；除了使用官方模块，有时候也需要自定义模块。
如果我们需要创建一个tools模块，用来实现众多的工具函数，那么我们可以创建一个tools.py的文件，并在这个文件里面实现一些函数，如：say_hello()函数、say_goodbye()函数。

```
# tools.py
def say_hello():
    print('hello')

def say_goodbye():
    print('goodbye')
```

这样就定义了一个叫tools的模块，接着就可以使用这个模块了，在使用之前，我们需要先导入模块，导入模块在下一节课会详细的学习。

## Python导入模块

要使用一个模块，我们必须首先导入该模块。Python使用import语句导入一个模块，Python官方提供很多有用的模块，比如：os模块、sys模块、time模块、math模块等等。
导入官方模块，不需要考虑路径的问题，例如，导入系统自带的模块 math，直接导入即可。如果是导入自定义模块，则需要考虑路径问题，我们下节课继续学习。
导入官方模块math：

```
import math
```

导入以后，你就可以认为math是一个指向已导入模块的变量，通过该变量，我们可以访问math模块中所定义的所有公开的函数、变量和类：

```
# 属性：圆周率
>>> import math
>>> math.pi
3.141592653589793

# 函数：次方
>>> math.pow(2, 3)
8.0
```

如果希望导入模块的指定部分属性或函数，那么使用from...import...语句。

```
>>> from math import pi
>>> print(pi)
3.141592653589793
```

这个时候，由于pow()函数没有导入，所以是不能使用pow()函数的。
如果希望导入模块里面的所有内容，那么使用from ...import *语句。

```
>>> from math import *
>>> print(pi)
3.141592653589793
>>> pow(2, 3)
8.0
```

如果从一个模块导入函数，有可能会遇到导入的函数与本文件的函数冲突的情况。例如：本文件定义了一个pow()函数，同时从math模块也导入了一个pow()函数，这种情况下就会引起冲突；事实上，这种冲突的情况经常发生。
有两种方法可以解决这个问题，第一种是直接导入模块，不指定导入模块里面的具体内容；第二种方法就是使用from ... import as ...语句，as类似重命名，可以把导入的函数或属性重命名为别的名字。

```
>>> from math import pow as mathpow
>>> mathpow(2, 3)
8.0
```

## Python模块导入的路径

导入官方模块的时候，不需要考虑路径问题，这是因为在搜索模块的时候，会默认包含官方模块的路径，所以导入官方模块不需要考虑路径的问题。
如果需要导入自定义模块，则需要了解Python导入模块搜索的路径。
通过sys模块，可以知道导入模块的路径。

```
>>> import sys
>>> sys.path
['', '/data/miniconda3/lib/python3.8', '/data/miniconda3/lib/python3.8/site-packages']
```

它返回的是一个列表，表示的是在搜索Python模块时，会搜索的路径，在示例中，返回了四个路径。我们分析一些关键路径：
第一个路径是''，它是一个空字符串，表达的是当前路径的意思。
第二个路径是/data/miniconda3/lib/python3.8，它是Python默认模块的存放的路径，在这个路径下，可以发现有os、sys等模块的代码。
第三个路径是/data/miniconda3/lib/python3.8/site-packages，它是第三方模块代码的存放路径，在这个路径下，存放的是需要安装的第三方模块。

那如何使用我们前面定义的tools.py模块呢？
我们在tools.py同级目录，创建main.py文件：

```
# main.py

import tools # 导入模块

tools.say_hello() # 调用模块里面的say_hello()函数
tools.say_goodbye() # 调用模块里面的say_goodbye()函数
```

就可以运行了。
因为在搜索包的路径时，会搜索当前路径（上述：sys.path结果的第一项），因此在同一个目录内的tools.py模块，可以被搜索到，所以能够import进来。

## Python安装第三方模块的方法

尽管Python的官方模块已经提供了非常强大的能力，但是仍有大量热心开发者提供了非常好用的第三方库，在实际开发中，也会经常使用，比如Web开发框架，Django、Flask，异步任务框架：Celery等。
在安装Python的时候，Python环境提供了安装第三方模块的工具：pip，通过这个工具，可以非常快捷的安装第三方模块。
安装Django模块：

```
pip install django
```

卸载Django模块：

```
pip uninstall django
```

# Python读写文件

## 向Python程序输入内容

到目前为止，我们编写的程序都是直接运行的，在运行过程中并没有接收程序外部的输入。比如，通过Python程序，我们可以快速算出从1到100的乘法结果。

```
result = 1
for i in range(1, 101):
    result = result * i

print(result)
```

但是如果需要计算从1到200的乘法结果，则只能通过修改程序去实现。

```
result = 1
for i in range(1, 201):
    result = result * i

print(result)
```

如果可以通过输入，改变计算的范围，那就好了，input()函数可以接收外部的输入。

```
>>> num = input('please input number: ')
please input number: 201
>>> print(num) 
201
```

因此，通过input()函数，则可以改变上面程序运行的范围，注意：输入的是字符串，需要转型为数字类型。

```
num = input('please input number: ')

num = int(num)
result = 1
for i in range(1, num):
    result = result * i

print(result)
```

## Python打开文本文件

通过print()可以从数据输出数据，通过input()可以向程序输入数据，但这些都是标准屏幕上的操作，本节课学习文件的读写操作。
Python 提供了open()函数，可以打开一个文件，得到一个文件file对象，而file对象提供相关的方法对文件内容进行读写等操作。
open()函数有若干个参数，比较重要的是以下三个参数：

1. 文件路径：指定需要打开的文件的文件路径
2. 打开模式：针对不同文件（二进制文件、文本文件）以及不同操作（读操作、写操作），会有不同的打开模式
3. 编码：设定打开文件的默认编码

常用的打开模式如下：

| **模式** | **描述**                                                   |
| -------- | ---------------------------------------------------------- |
| t        | 文本模式（默认）                                           |
| x        | 写模式，新建一个文件                                       |
| b        | 二进制模式，打开二进制文件                                 |
| +        | 更新一个文件（可读可写）                                   |
| r        | 以只读模式打开一个文件                                     |
| rb       | 以二进制格式只读模式打开一个文件                           |
| w        | 打开一个文件进行写入，如果文件内容已存在，会清除原有的内容 |
| wb       | 以二进制格式只写模式打开一个文件，会清除原有的内容         |
| a        | 打开一个文件并追加内容，会往文件尾部添加内容               |
| ab       | 以二进制格式打开一个文件并追加内容，会往文件尾部添加内容   |
| w+       | 打开一个文件进行读写，如果文件内容已存在，会清除原有的内容 |
| a+       | 打开一个文件并使用追加进行读写                             |

注意，为了安全操作文件，文件使用完毕后，需要使用close()函数正确关闭。
在当前目录下新建一个test.txt文件，并新建一个main.py，此时文件目录如下：

```
|-- test.txt
+-- main.py 
```

 

```
f = open('test.txt', 'r') # 打开test.txt文件
type(f) # 打印f的类型(<class '_io.TextIOWrapper'>)
f.close() # 关闭文件
```

注意，在打开文本文件是并不需要特别指定模式t，因为默认就是以文本方式打开文件的。

## Python打开二进制文件

除了文本以外，还有大量的非文本文件，比如图片、压缩文件、视频文件、音乐文件等等，这种文件统称为二进制文件，在Python中打开二进制文件，需要不同的打开模式。

| b    | 二进制模式，打开二进制文件                                   |
| ---- | ------------------------------------------------------------ |
| wb   | 以二进制格式只写模式打开一个文件，会清除原有的内容           |
| ab   | 以二进制格式**打开一个文件并追加内容，会往文件尾部添加内容** |
| rb   | 以二进制格式只读模式打开一个文件                             |

```
f = open('test.jpg', 'rb')
f.close()
```

## Python读取文件内容

打开文件之后，就可以读取文件的内容，文件对象提供多种读取文件内容的方法。
打开test.txt文件：

```
f = open('test.txt', 'r') # 打开test.txt文件
f.close() # 关闭文件
```

test.txt文件有以下内容

```
Hello World.
Hello Python.
Hello Imooc.
```

### **读取若干字符**

文件对象提供read()方法，可以读取文件中的若干个字符，它提供一个参数size，可以指定读取字符的数量。

```
s = f.read(5)
print(s) # ==> Hello
```

当read()之后，访问文件的游标就会移动到第六个字符前面，此时，继续read，将得到Hello后面的结果。

```
s = f.read(6)
print(s) # ==> ' World'
```

### **读取一行**

文件对象提供readline()方法，和read()方法类似，可以读取文件中的若干个字符，它也提供一个参数size，可以指定读取字符的数量，不过和read()方法不同的是，readline()方法遇到一行结束的时候，就会返回。

```
f.close()
f = open('test.txt', 'r') # 重新打开文件
s = f.readline(20)
print(s)  # ==> 'Hello World.\n'
```

可以看到，打印的内容并没有20个字符，readline最多返回一行的所有字符。

### **读取多行**

文件对象提供readlines()方法，可以读取多行字符，返回一个列表。它提供一个hint参数，表示指定读取的行数，没有指定则默认以列表的形式返回文件所有的字符串。

```
f.close()
f.open('test.txt', 'r')
s = f.readlines()
print(s) # ==> ['Hello World.\n', 'Hello Python.\n', 'Hello Imooc.\n']
```

## Python把字符串写入文件

要把字符串内容写入文件，需要使用w的模式打开文件。

| **模式** | **描述**                                                   |
| -------- | ---------------------------------------------------------- |
| w        | 打开一个文件进行写入，如果文件内容已存在，会清除原有的内容 |
| wb       | 以二进制格式只写模式打开一个文件，会清除原有的内容         |
| w+       | 打开一个文件进行读写，如果文件内容已存在，会清除原有的内容 |

 

```
f = open('test.txt', 'w')
```

### **写入若干字符**

文件对象提供write方法向文件内写入若干字符，它接受一个字符串参数，表示需要写入的字符串。

```
f = open('test.txt', 'w')
f.write('Hello World\n')
f.close()
```

### **写入若干行**

文件对象提供writelines()方法向文件内容写入多行数据，它接受一个列表，表示需要写入的字符串列表。

```
lines = ['Hello World\n', 'Hello Python\n', 'Hello Imooc\n']
f = open('test.txt', 'w')

f.writelines(lines)
f.close()
```

## Python往文件追加内容

通过w的打开方式打开文件，会清空文件的内容，这在很多场景下是不合适的，比如写系统日志的时候，需要累积随时间推移的所有数据。

Python提供文件追加内容的打开模式，可以往文件尾部添加内容，又不清空文件原有的内容。

| **模式** | **描述**                                                 |
| -------- | -------------------------------------------------------- |
| a        | 打开一个文件并追加内容，会往文件尾部添加内容             |
| ab       | 以二进制格式打开一个文件并追加内容，会往文件尾部添加内容 |
| a+       | 打开一个文件并使用追加进行读写                           |

 

```
f = open('test.txt', 'a')
f.write('Hello Everyone\n')
f.close()
```

使用a的打开方式打开文件，文件游标默认是在文件的尾部，因此，可以便捷的往文件尾部添加内容，除此以外，文件对象还提供seek()方法，可以移动文件的游标位置，它接受一个参数，表示文件的位置，0：文件首部，1：当前位置，2：文件尾部，通过seek()可以把文件游标移动到文件首部但不删除文件的内容。

```
f = open('test.txt', 'a+')
content = f.readlines()
print(content) # ==> []
f.seek(0)
content = f.readlines()
print(content) # ==> ['Hello World\n', 'Hello Python\n', 'Hello Imooc\n']
```

第一次print(content)的时候，由于文件游标在文件的尾部，所以readlines()读取不到任何数据，打印了空的结果，第二次print(content)的时候，由于通过seek(0)，文件游标移动到了文件的首部，因此readlines()就返回了文件所有的内容。

## Python正确关闭文件

在进行文件操作的时候，正确关闭一个文件非常重要，如果在文件读写后，没有正确关闭一个文件的话，则有可能导致文件损坏，文件内容丢失等问题。

在一般情况下，我们使用文件对象的close()方法，来关闭一个文件。
但是，使用close()方法，也不是100%安全的，如果在close()文件之前，程序异常退出了，那么文件也得不到正确的关闭。比如：

```
f = open('test.txt', 'a+')
exit(-1) # ==> 模拟程序异常退出
f.close() # ==> close语句永远的不到执行
```

在实际工程中，close()文件之前，为了正确关闭文件，需要考虑各种异常情况，这是非常麻烦的一件事，Python提供with关键字，可以免除这类后顾之忧。
with关键字对资源进行访问的场合，会确保不管在使用过程中是否发生异常，都会执行必要的“清理”的操作，释放资源，比如文件使用后自动关闭等等。
with的使用方法如下：

```
with open('test.txt', 'r') as f:
    content = f.readlines()
    for line in content:
        print(line)
```

当文件使用结束后，不需要显式的调用f.close()关闭文件。

# Python的网络编程

## 套接字Socket与套接字编程

要进行网络通信，需要建立起通信双方的连接，连接的双方分别称为客户端和服务端，在Python中，使用套接字socket来建立起网络连接。
套接字包含在socket模块中：

```
import socket
socket.socket()
```

对于客户端和服务端，都是使用socket来建立连接的，但是在使用行为上，客户端和服务端会有一些不一样。
服务端建立需要四个步骤：新建socket、绑定IP和端口(bind)、监听连接(listen)、接受连接(accept)。
客户端建立则简单一些，仅需两个步骤：新建socket、连接服务端(connect)。
当网络连接上以后，客户端和服务端就可以进行数据通信了，套接字通过send()函数发送数据，通过recv()函数接收数据。


先看服务端的过程，新建一个server.py的文件：

```
import socket

server = socket.socket() # 1. 新建socket
server.bind(('127.0.0.1', 8999)) # 2. 绑定IP和端口（其中127.0.0.1为本机回环IP）
server.listen(5) # 3. 监听连接
s, addr = server.accept() # 4. 接受连接
print('connect addr：{}'.format(addr))
content =s.recv(1024)
print(str(content, encoding='utf-8'))  # 接受来自客户端的消息，并编码打印出来
s.close()
```

如上，服务端就编写完毕，接下来是编写客户端，新建一个client.py的文件：

```
import socket

client = socket.socket() # 1. 新建socket
client.connect(('127.0.0.1', 8999)) # 2. 连接服务端（注意，IP和端口要和服务端一致）
client.send(bytes('Hello World. Hello Socket', encoding='utf-8')) # 发送内容，注意发送的是字节字符串。
client.close()
```

接着在一个终端先运行服务端：

```
python server.py
```

然后再在另外一个终端运行客户端：

```
python client.py
```

在服务端的终端，将会输出以下信息：

```
connect addr：('127.0.0.1', 50382)
b'Hello World. Hello Socket'
```

## Python自带的HTTP服务器

在互联网的世界中，网页、手机H5等都是通过HTTP向用户提供服务的，这些信息存储在HTTP服务器中，HTTP服务器是一种特殊的Socket服务器，它在网络连接之上，定义了HTTP协议，使得网页、手机H5等数据，都可以以标准的HTTP协议进行传输。
实现一个HTTP服务器是一个不错的编程实践，可以学习到很多的知识，有兴趣的同学，可以了解下这门课程：https://www.imooc.com/learn/1172。
Python提供了简易的HTTP服务器，可以直接运行起来。
在终端，输入这条命令，就可以启动一个HTTP服务器。

```
python -m http.server
```

启动成功后，会输出以下信息：

```
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

提示HTTP服务器在本机8000端口运行，接着就可以在浏览器输入[http://127.0.0.1:8000](http://127.0.0.1:8000/)看到由这个服务器提供的网页。

![image-20211002094132167](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20211002094132167.png)

这个HTTP服务器会把运行目录的所有文件列出来，并提供下载功能。

## Python发送HTTP请求

在上一节，使用了Python自带的功能启动了一个HTTP服务器，并通过浏览器浏览到了这个HTTP服务器提供的页面。在浏览的过程中，实际上是浏览器向HTTP服务器发送了一个HTTP请求。

除了使用浏览器发送HTTP请求，通过代码也可以向HTTP服务器发送请求，Python提供了相关的库urllib，通过urllib包里面的request，可以向其他HTTP服务器发起请求。

```
from urllib import request
response = request.urlopen('https://www.imooc.com') # 向慕课网官网发出请求
print(response) # ==> <http.client.HTTPResponse object at 0x000001377D631948>
```

请求成功的话，会得到一个HTTPResponse，它是来自HTTP服务器的一个回应，可以把这个回应的一些信息打印出来。
状态码：

```
print(response.status) # ==> 200
```

状态码是一个三位整数，在HTTP协议的标准里面，定义了很多状态码，其中200表示请求是正常的。
响应头：

```
for k, v in response.getheaders():
    print('{}: {}'.format(k, v))
```

将会输出以下信息，这是HTTPResponse附带的一些信息，包括服务端的服务器是什么、请求时间、内容类型、内容长度等等。

```
Server: openresty
Date: Thu, 20 Aug 2020 08:16:07 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 376639
Connection: close
Vary: Accept-Encoding
Vary: Accept-Encoding
X-Varnish: 280516221 281284036
Age: 29
Via: 1.1 varnish (Varnish/6.0)
X-Cache: HIT from CS42
Accept-Ranges: bytes
```

Python官方提供的urllib库可以满足一般情况下的HTTP操作，但是urllib这个库设计是用来处理url地址的，并不是专门处理HTTP操作的包。因此，在很多场景下，一般会使用requests库来进行HTTP请求。
requests库是著名的Python第三方库，使用requests库，可以定制化你的HTTP请求，包括请求方法，请求参数等等。
由于requests是第三方库，因此在使用前，需要安装。

```
pip install requests
```

安装完成后，使用requests库来请求慕课网官网。

```
response = requests.get('https://www.imooc.com')
# 打印状态码
print(response.status_code)
# 打印回应头
print(response.headers)
```

在一般的使用上，requests和urllib没有太大区别，但是在复杂的场景中，requests可以提供urllib无法提供的强大功能。因此，在使用上，建议使用requests库代替urllib库来进行HTTP请求等的操作。

## HTTP响应的内容

通过urllib或者requests请求后，会得到一个HTTPResponse，HTTPResponse拥有状态码、回应头等的信息。
但我们知道，对于一个页面，通常是由文字、图片等信息组成的，这些属于一个HTTPResponse的内容。

```
import requests

response = requests.get('https://www.imooc.com')
content = str(response.content, encoding='utf-8') # ==> 打印具体内容
```

打印的结果是一个很长的字符串，显得杂乱无章，但其实它是由结构的，它是一个标准的HTML页面，可以从页面内容里面获取很多有用的数据。
网络爬虫是典型的应用程序，它的工作原理就是通过不断的请求互联网的页面，并从回应中解析获取出有用的数据；数据积累后，可以有很多用处。
通过requests获得网页的内容后，我们可以尝试使用一些简单的方法获取页面的内容。

```
content_list = content.split('\n') # 分行
len(content_list) # 打印页面内容的行数
```

在网页中，页面内部链接其他资源的信息是通过href提供的，通过字符串匹配的方式可以过滤出包含链接的行。

```
for line in content_list:
    if 'href' in line:
        print(line.strip())
```

过滤出来的信息或许有些杂乱，但也包含了一些有用的数据，我们可以从过滤后的信息中找到链接相关的信息。不过我们过滤的方式比较简单，通过优化过滤的方式可以匹配到更加精准的数据。而爬虫正是这样工作的。

# Python的函数式编程

## Python把函数作为参数

在前面，我们了解了高阶函数的概念，并编写了一个简单的高阶函数：

```
def add(x, y, f):
    return f(x) + f(y)
```

如果传入abs作为参数f的值：

```
add(-5, 9, abs)
```

根据函数的定义，函数执行的代码实际上是：

```
abs(-5) + abs(9)
```

由于参数 x, y 和 f 都可以任意传入，如果 f 传入其他函数，就可以得到不同的返回值。

## Python的map()函数

map()是 Python 内置的高阶函数，它接收一个函数 f 和一个 list，并通过把函数 f依次作用在list的每个元素上，map()函数会返回一个迭代器，可以依次迭代得到原来list的元素被函数f处理后的结果。

```
>>> map(f, list)
```

例如，对于list [1, 2, 3, 4, 5, 6, 7, 8, 9]。
如果希望把list的每个元素都作平方，就可以利用map()函数。

![image-20211002095410847](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20211002095410847.png)

我们定义需要传入函数f(x)=x*x，就可以利用map()函数完成这个计算：

```
def f(x):
    return x*x

for item in map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9]):
    print(item)
```

得到结果：

```
[1, 4, 9, 10, 25, 36, 49, 64, 81]
```

由于list包含的元素可以是任何类型，因此，map() 不仅仅可以处理只包含数值的 list，事实上它可以处理包含任意类型的 list，只要传入的函数f可以处理这种数据类型。

## Python的reduce()函数

和map函数一样，reduce()函数也是Python内置的一个高阶函数。reduce()函数接收的参数和 map() 类似，一个函数 f，一个list，但行为和 map()不同，reduce()传入的函数 f 必须接收两个参数，reduce()对list的每个元素反复调用函数f，并返回最终结果值。
在python2中，reduce()函数和map()函数一样，可以直接使用，但是在python3中，reduce()函数被收录到functools包内，需要引入functools才可以使用。
例如，编写一个f函数，接收x和y，返回x和y的和：

```
def f(x, y):
    return x + y
```

调用 reduce(f, [1, 3, 5, 7, 9])：

```
from functools import reduce

def f(x, y):
    return x + y

print(reduce(f, [1,3,5,7,9])) # ==> 25
```

得到的结果是25，实际过程是这样的，reduce()函数会做如下计算：

```
先计算头两个元素：f(1, 3)，结果为4；
再把结果和第3个元素计算：f(4, 5)，结果为9；
再把结果和第4个元素计算：f(9, 7)，结果为16；
再把结果和第5个元素计算：f(16, 9)，结果为25；
由于没有更多的元素了，计算结束，返回结果25。
```

上述计算实际上是对 list 的所有元素求和。虽然Python内置了求和函数sum()，但是，利用reduce()求和也很简单。
reduce()还可以接收第3个可选参数，作为计算的初始值。如果把初始值设为100，计算：

```
print(reduce(f, [1, 3, 5, 7, 9], 100)) # ==> 125
```

结果将变为125，因为第一轮计算是：

计算初始值和第一个元素：f(100, 1)，结果为101。

## Python的filter()函数

filter()函数是 Python 内置的另一个有用的高阶函数，filter()函数接收一个函数 f 和一个list，这个函数 f 的作用是对每个元素进行判断，返回 True或 False，filter()根据判断结果自动过滤掉不符合条件的元素，并返回一个迭代器，可以迭代出所有符合条件的元素。
例如，要从一个list [1, 4, 6, 7, 9, 12, 17]中删除偶数，保留奇数，首先，要编写一个判断奇数的函数：

```
def is_odd(x):
    return x % 2 == 1
```

然后，利用filter()过滤掉偶数：

```
for item in filter(is_odd, [1, 4, 6, 7, 9, 12, 17]):
    print(item)
```

结果：1,7,9,17。
利用filter()函数，可以完成很多很有用的功能，例如，删除 None 或者空字符串：

```
def is_not_empty(s):
    return s and len(s.strip()) > 0

for item in filter(is_not_empty, ['test', None, '', 'str', '  ', 'END']):
    print(item)
```

结果：test, str, END
注意：注意: s.strip()会默认删除空白字符（包括'\n', '\r', '\t', ' ')，如下：

```
s = '     123'
s.strip() # ==> 123
s= '\t\t123\r\n'
s.strip() # ==> 123
```

## Python自定义排序函数

Python内置的 sorted()函数可对list进行排序：

```
>>> sorted([36, 5, 12, 9, 21])
[5, 9, 12, 21, 36]
```

可以看到，sorted()函数，默认是由小到大排序列表的元素。

```
>>> score = [('Alice', 72), ('Candy', 90), ('Bob', 62)]
>>> sorted(score)
[('Alice', 72), ('Bob', 62), ('Candy', 90)]
```

当list的每一个元素又是一个容器时，则会以第一个元素来排序，比如在score中，每个元素都是包含名字和成绩的一个tuple，sorted()函数则按名字首字母进行了排序并返回。
对于上述排序成绩的情况，默认是按照第一个名字进行排序的，有没有办法让sorted()函数按照成绩来进行排序呢？
如果需要按照成绩高低进行排序，需要指定排序的字段是成绩，sorted接受key参数，用来指定排序的字段，key的值是一个函数，接受待排序列表的元素作为参数，并返回对应需要排序的字段。因此，sorted()函数也是高阶函数。

```
def k(item):
    return item[1] # ==> 按成绩排序，成绩是第二个字段

sorted(score, key=k)
```

得到结果：[('Bob', 62), ('Alice', 72), ('Candy', 90)] 。
如果需要倒序，指定reverse参数即可。

```
sorted(score, key=k, reverse=True)
```

得到结果：[('Candy', 90), ('Alice', 72), ('Bob', 62)] 。

## Python返回函数

在函数内部，是可以定义子函数的。

```
def func():
    # 定义子函数
    def sub_func():
        print('call sub_func.')
    sub_func()

>>> func()
call sub_func.
```

作为高阶函数，可以接受函数作为参数，其实高阶函数，除了不仅仅可以返回int、str、list、dict等数据类型，还可以返回函数。因此，可以把函数的子函数返回。

```
def f():
    print('call f()...')
    # 定义函数g:
    def g():
        print('call g()...')
    # 返回函数g:
    return g
```

仔细观察上面的函数定义，我们在函数 f 内部又定义了一个函数 g。由于函数 g 也是一个对象，函数名 g 就是指向函数 g 的变量，所以，最外层函数 f 可以返回变量 g，也就是函数 g 本身。
调用函数 f，我们会得到 f 返回的一个函数：

```
>>> x = f()   # 调用f()
call f()...
>>> x   # 变量x是f()返回的函数：
<function f.<locals>.g at 0x7f4a4936dbf8>
>>> x()   # x指向函数，因此可以调用
call g()...   # 调用x()就是执行g()函数定义的代码
```

有必要注意的是，返回函数和返回函数值的语句是非常类似的，返回函数时，不能带小括号，而返回函数值时，则需要带上小括号以调用函数。

```
# 返回函数
def myabs():
    return abs

# 返回函数值
def myabs(x):
    return abs(x)
```

返回函数有很多应用，比如可以将一些计算延迟执行，举个例子，定义一个普通的求和函数。

```
def calc_sum(list_):
    return sum(list_)
```

调用calc_sum()函数时，将立刻计算并得到结果：

```
>>> calc_sum([1, 2, 3, 4])
10
```

但是，如果返回一个函数，就可以“延迟计算”：

```
def calc_sum(list_):
    def lazy_sum():
        return sum(list_)
    return lazy_sum
```

调用calc_sum()并没有计算出结果，而是返回函数:

```
>>> f = calc_sum([1, 2, 3, 4])
>>> f
<function calc_sum.<locals>.lazy_sum at 0x7f4a4936db70>
```

对返回的函数进行调用时，才计算出结果:

```
>>> f()
10
```

由于可以返回函数，我们在后续代码里就可以决定到底要不要调用该函数。

## Python的闭包

在函数内部定义的函数和外部定义的函数是一样的，只是他们无法被外部访问：

```
def g():
    print('g()...')

def f():
    print('f()...')
    return g
```

将g的定义移入函数 f 内部，防止其他代码调用 g：

```
def f():
    print('f()...')
    def g():
        print('g()...')
    return g
```

但是，考察上一小节定义的 calc_sum 函数：

```
def calc_sum(list_):
    def lazy_sum():
        return sum(list_)
    return lazy_sum
```

注意: 发现没法把 lazy_sum 移到 calc_sum 的外部，因为它引用了 calc_sum 的参数 list_。

像这种内层函数引用了外层函数的变量（参数也算变量），然后返回内层函数的情况，称为闭包（Closure）。

闭包的特点是返回的函数还引用了外层函数的局部变量，所以，要正确使用闭包，就要确保引用的局部变量在函数返回后不能变。举例如下：

```
# 希望一次返回3个函数，分别计算1x1,2x2,3x3:
def count():
    fs = []
    for i in range(1, 4):
        def f():
             return i*i
        fs.append(f)
    return fs

f1, f2, f3 = count()
```

你可能认为调用f1()，f2()和f3()结果应该是1，4，9，但实际结果全部都是 9（请自己动手验证）。

原因就是当count()函数返回了3个函数时，这3个函数所引用的变量 i 的值已经变成了3。由于f1、f2、f3并没有被调用，所以，此时他们并未计算 i*i，当 f1 被调用时：

```
>>> f1()
9     # 因为f1现在才计算i*i，但现在i的值已经变为3
```

因此，返回函数不要引用任何循环变量，或者后续会发生变化的变量。

## Python的匿名函数

高阶函数可以接收函数做参数，有些时候，我们不需要显式地定义函数，直接传入匿名函数更方便。

在Python中，对匿名函数提供了有限支持。还是以map()函数为例，计算 f(x)=x * x时，f(x)就是作为参数传入map的。
在前面，我们是显式的定义了一个f(x)的函数，除此以外，其实可以直接传入匿名函数。 
匿名函数使用lambda定义：lambda x: x * x，就可以完成原来显式定义的f(x)函数的功能，冒号前面的x表示匿名函数的参数，后面的是一个表达式，匿名函数有个限制，就是只能有一个表达式，不写return，返回值就是该表达式的结果。

```
result = [item for item in map(lambda x: x * x, [1, 2, 3, 4, 5, 6, 7, 8, 9])]
print(result) # ==> [1, 4, 9, 16, 25, 36, 49, 64, 81]
```

同理，对于reduce()函数，也同样可以通过定义匿名函数来实现相同的逻辑。

```
from functools import reduce

reduce(lambda x, y: x + y, [1,3,5,7,9])
```

## Python编写无参数的decorator

Python的 decorator 本质上就是一个高阶函数，它接收一个函数作为参数，然后，返回一个新函数。

使用 decorator 用Python提供的 @ 语法，这样可以避免手动编写 f = decorate(f) 这样的代码。
考察一个@log的定义：

```
def log(f):
    def fn(x):
        print('call ' + f.__name__ + '()...')
        return f(x)
    return fn
```

对于阶乘函数，@log工作得很好：

```
@log
def factorial(n):
    return reduce(lambda x,y: x*y, range(1, n+1))

print(factorial(10))
```

结果：

```
call factorial()...
3628800
```

但是，对于参数不是一个的函数，调用将报错：

```
@log
def add(x, y):
    return x + y
print(add(1, 2))
```

 

```
>>> print(add(1, 2))
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: fn() takes 1 positional argument but 2 were given
```

因为 add() 函数需要传入两个参数，但是 @log 写死了只含一个参数的返回函数。

要让 @log 自适应任何参数定义的函数，可以利用Python的 *args 和 **kwargs，保证任意个数的参数总是能正常调用：

```
def log(f):
    def fn(*args, **kwargs):
        print('call ' + f.__name__ + '()...')
        return f(*args, **kwargs)
    return fn
```

## Python编写有参数的decorator

考察上一节的 @log 装饰器：

```
def log(f):
    def fn(x):
        print('call ' + f.__name__ + '()...')
        return f(x)
    return fn
```

发现对于被装饰的函数，log打印的语句是不能变的（除了函数名）。

如果有的函数非常重要，希望打印出'[INFO] call xxx()...'。
有的函数不太重要，希望打印出'[DEBUG] call xxx()...'。
这时，log函数本身就需要传入'INFO'或'DEBUG'这样的参数，类似这样：

```
@log('DEBUG')
def my_func():
    pass
```

把上面的定义翻译成高阶函数的调用，就是：

```
my_func = log('DEBUG')(my_func)
```

上面的语句看上去还是比较绕，再展开一下：

```
log_decorator = log('DEBUG')
my_func = log_decorator(my_func)
```

上面的语句又相当于：

```
log_decorator = log('DEBUG')
@log_decorator
def my_func():
    pass
```

所以，带参数的log函数首先返回一个decorator函数，再让这个decorator函数接收my_func并返回新函数，相当于是在原有的二层嵌套里面，增加了一层嵌套：

```
def log(prefix):
    def log_decorator(f):
        def wrapper(*args, **kw):
            print('[{}] {}()...'.format(prefix, f.__name__))
            return f(*args, **kw)
        return wrapper
    return log_decorator

@log('DEBUG')
def test():
    pass
test()
```

执行结果：

```
[DEBUG] test()...
```

对于这种三层嵌套的decorator定义，你可以先把它拆开：

```
# 标准decorator:
def log_decorator(f):
    def wrapper(*args, **kw):
        print('[{}] {}()...'.format(prefix, f.__name__))
        return f(*args, **kw)
    return wrapper
return log_decorator

# 返回decorator:
def log(prefix):
    return log_decorator(f)
```

## Python的偏函数

当一个函数有很多参数时，调用者就需要提供多个参数。如果减少参数个数，就可以简化调用者的负担。

比如，int()函数可以把字符串转换为整数，当仅传入字符串时，int()函数默认按十进制转换：

```
>>> int('12345')
12345
```

但int()函数还提供额外的base参数，默认值为10。如果传入base参数，就可以做 N 进制的转换：

```
>>> int('12345', base=8)
5349
>>> int('12345', 16)
74565
```

假设要转换大量的二进制字符串，每次都传入int(x, base=2)非常麻烦，于是，我们想到，可以定义一个int2()的函数，默认把base=2传进去：

```
def int2(x, base=2):
    return int(x, base)
```

这样，我们转换二进制就非常方便了：

```
>>> int2('1000000')
64
>>> int2('1010101')
85
```

偏函数指的就是“创建一个调用另外一个部分参数或变量已经预置的函数”的函数的用法，如上所示，int()函数的base参数，没有指定的时候，默认是以十进制工作的，当指定base=2的时候，int2实际上就变成了部分参数(base)已经预置了的偏函数。
functools.partial就是帮助我们创建一个偏函数的，不需要我们自己定义int2()，可以直接使用下面的代码创建一个新的函数int2：

```
>>> import functools
>>> int2 = functools.partial(int, base=2)
>>> int2('1000000')
64
>>> int2('1010101')
85
```

所以，functools.partial可以把一个参数多的函数变成一个参数少的新函数，少的参数需要在创建时指定默认值，这样，新函数调用的难度就降低了。

# 补充

#### 第三方模块

```
#ModuleNotFoundError 缺少模块

pillow          图片处理
requests        爬虫
pyemail         邮件处理
baidu-aip       百度人工智能接口
pymysql         mysql数据库连接
tushare         财经数据接口
pyecharts       数据可视化
```

#### 内置模块urllib

```
# 内置模块urllib(爬虫模块)
# 爬虫:爬取互联网数据的程序
from urllib import request

url = "http://www.baidu.com"
data = request.urlopen(url).read()  # 发送请求并读取数据
print(data.decode())  # decode()解码：将二进制转换成字符

with open(r"0413.html", "wb") as f:
    f.write(data)
```

#### 内置模块datetime

```
# 内置模块datetime
import datetime

# 获取当前的日期时间
now = datetime.datetime.now()
print(type(now))

# 获取一个指定时间
d1 = datetime.datetime(2018, 2, 13, 5, 23, 45)
print(d1)

# 日期转字符串
s1 = d1.strftime("%Y年-%m月-%d日  %H:%M:%S")
print(s1)

# 字符串转日期(格式一定要一致)
s2 = "2018/02/13 05:23:45"
d2 = datetime.datetime.strptime(s2, "%Y/%m/%d %H:%M:%S")
print(d2, type(d2))
```

#### 内置模块time

```
# 内置模块time
import time

# #获取一个时间戳：当前时间距离1970年元旦0时的秒数
s1=time.time()
for x in range(1,10001):
   print(x)
s2=time.time()
print(s2-s1)

# 获取当前本地的日期和时间
t = time.localtime()

# 将日期和时间转换成指定格式的字符串
strtime = time.strftime("%Y年-%m月-%d日----%H:%M:%S", t)
# print(strtime)


# #程序休眠
# time.sleep(5*60*60)
# print("hello")


# 倒计时
# i = 10
# while i >= 0:
#     print("倒计时：", i)
#     time.sleep(1)
#     i -= 1
```

#### 内置模块random

```
import random  # 引入随机数模块

# 模块名.函数名()
r1 = random.randint(1, 6)  # 生成指范围随机整数
r2 = random.uniform(1, 6)  # 生成指范围随机浮点数
r3 = random.choice([1, 132, 32, 43, 43, 454, 46, 56, 55, 76, 7])  # 在一个序列中随机获取一个值
r4 = random.random()  # 生成0-1随机浮点数

# 抽奖程序：一等奖 笔记本电脑 0.001   二等奖 冰箱 0.01  三等奖 音响 0.05   谢谢惠顾 1-0.001-0.01-0.05
print("正在抽奖.......")
r = random.randint(1, 1000)
print("----------您的抽奖号码是：", r)
if r == 1:
    print("*******恭喜你，获得一等奖笔记本电脑！")
elif 10 <= r <= 19:
    print("*******恭喜你，获得二等奖 冰箱！")
elif 100 <= r <= 149:
    print("*******恭喜你，获得三等奖 音响！")
else:
    print("******* 谢谢惠顾！")
```

####  with open()语法

```
# with open()语法
with open(r"F:\Pycharm\file\再别康桥.txt", "r") as file:
    data = file.read()
    print(data)

# 文件复制
with open(r"F:\Pycharm\file\aaa\cat.jpg", "rb") as file1, open(
        r"F:\Pycharm\file\bbb\cat-4.jpg", "wb") as file2:
    data = file1.read()
    file2.write(data)
```

#### 案例：模拟银行ATM

```
# 案例：模拟银行ATM存款取款

# 1.模拟3张银行卡,1001,1002,1003,分别设置密码和余额(使用列表嵌套字典的方式)；

# 2.提示用户输入银行卡和密码，遍历每张卡的信息验证是否成功；

# 3.如果用户输入正确---提示让用户选择取款.存款还是退出,并提示余额多少.  输入错误---重新输入卡号密码；
# 选择取款---提示输入取款额度,如果超过余额,提示余额不足;否则,在余额上减掉相应金额；
# 选择存款---输入存款额度,余额加上相应额度,并提示余额多少；
# 选择退出---重新登录；

# 4.连续3次输入错误账号密码,提示银行卡已被锁定，程序结束。

card1 = {"姓名": "张三", "卡号": "1001", "密码": "123", "余额": 10000}
card2 = {"姓名": "李四", "卡号": "1002", "密码": "123", "余额": 20000}
card3 = {"姓名": "王五", "卡号": "1003", "密码": "123", "余额": 30000}
card4 = {"姓名": "赵六", "卡号": "1004", "密码": "123", "余额": 40000}
cardsList = [card1, card2, card3, card4]
count = 0  # 记录输入错误的次数
while 1 == 1:
    cnum = input("请输入卡号：")
    cpwd = input("请输入密码：")
    msg = 0  # 记录登录状态 0失败 1成功！
    for card in cardsList:
        if cnum == card["卡号"] and cpwd == card["密码"]:
            msg = 1
            count = 0  # 当验证成功时，错误次数清零
            print("恭喜你！", card["姓名"], "！验证成功！")
    if msg == 0:
        count += 1
        if count == 3:
            print("您已经连续3次输入错误，银行卡被锁定！")
            break
        else:
            print("验证失败！您已经连续", count, "次输入错误,还有", 3 - count, "次机会！")
            continue

    # 银行业务
    while 2 == 2:
        choice = int(input("请输入要办理的业务编号（1.存款 2.取款 3.退出）："))
        if choice == 1:
            money1 = float(input("请输入存款金额："))
            for card in cardsList:
                if card["卡号"] == cnum:
                    card["余额"] = card["余额"] + money1
                    print("存款成功！存入", money1, "元！余额", card["余额"], "元！")
                    break
        elif choice == 2:
            money2 = float(input("请输入取款金额："))
            for card in cardsList:
                if card["卡号"] == cnum:
                    card["余额"] = card["余额"] - money2
                    print("取款成功！取出", money2, "元！余额", card["余额"], "元！")
                    break
        elif choice == 3:
            print("-----------已退出！-------------")
            break
        else:
            print("没有此业务，请重新选择！")
            continue
```

#### 案例：商品管理

```
# 商品管理系统
# a.   使用列表嵌套字典的方式保存用户数据（包含用户名，密码，姓名）；
# b.   使用列表嵌套字典的方式保存商品数据（包含编号，名称，价格，折扣）；
# c.   编写用户登录的函数，返回登录结果；
# d.   循环提示菜单，业务完毕时返回主菜单，退出时回到登陆页面；
# e.   将功能菜单中的业务功能各自编写到函数中；
# f.   用户选择不同业务编号时，调用已经写好的各种函数。

# 数据准备
user1 = {"用户名": "aaa", "密码": "123", "姓名": "张三"}
user2 = {"用户名": "bbb", "密码": "123", "姓名": "李四"}
user3 = {"用户名": "ccc", "密码": "123", "姓名": "王五"}
usersList = [user1, user2, user3]  # 用户列表

p1 = {"编号": "1001", "名称": "苹果", "价格": 5, "折扣": 1}
p2 = {"编号": "1002", "名称": "香蕉", "价格": 3, "折扣": 1}
p3 = {"编号": "1003", "名称": "牛奶", "价格": 4, "折扣": 1}
p4 = {"编号": "1004", "名称": "白菜", "价格": 1, "折扣": 1}
p5 = {"编号": "1008", "名称": "西瓜", "价格": 3, "折扣": 1}
productsList = [p1, p2, p3, p4, p5]  # 商品列表


# 登录
def login():
    msg = "失败"
    while 1 == 1:
        uname = input("请输入用户名：")
        upwd = input("请输入密码：")
        for user in usersList:
            if uname == user["用户名"] and upwd == user["密码"]:
                print("---------验证成功！欢迎你，", user["姓名"], "！")
                msg = "成功"
                break
        if msg == "失败":
            print("用户名密码错误，请重新输入！")
            continue
        else:
            break
    return msg  # 返回登录结果


# 1.显示商品列表
def showProcucts():
    print("-编号----名称----价格----折扣-")
    for product in productsList:
        print(product["编号"] + "-----" + product["名称"] + "-----" + str(product["价格"]) + "-------" + str(product["折扣"]))
    print("-----------------------------")


# 2.增加商品信息
def addProcuct():
    # 生成新编号
    lista = []  # 存放所有商品的编号
    for product in productsList:
        lista.append(int(product["编号"]))
    newNum = str(max(lista) + 1)
    name = input("请输入商品名称：")
    price = float(input("请输入商品单价："))
    newProduct = {"编号": newNum, "名称": name, "价格": price, "折扣": 1}
    productsList.append(newProduct)
    print("-------商品", name, "添加成功！")
    showProcucts()


# 3.删除商品（通过编号删除）
def delProcuct():
    while 1 == 1:
        msg = 0  # 记录商品是否存在
        num = input("请输入要删除的商品编号：")
        for product in productsList:
            if num == product["编号"]:
                print("---正在删除", product["名称"], "商品...........")
                productsList.remove(product)  # 删除商品
                print("----删除成功！")
                msg = 1
                break
        if msg == 0:
            print("商品编号不存在！")
            choice = int(input("取消请按1，重新输入请按2："))
            if choice == 1:
                break
            else:
                continue
        else:
            showProcucts()
            break


# 4.设置商品折扣
def setDiscout():
    while 1 == 1:
        msg = 0  # 记录商品是否存在
        num = input("请输入要设置折扣的商品编号：")
        for product in productsList:
            if num == product["编号"]:
                newDiscount = float(input("请输入新的折扣（0.1-1）："))
                product["折扣"] = newDiscount  # 设置折扣
                print("---商品", product["名称"], "折扣已设置成功，", newDiscount * 10, "折！")
                msg = 1
                break
        if msg == 0:
            print("商品不存在！")
            choice = int(input("取消请按1，重新输入请按2："))
            if choice == 1:
                break
            else:
                continue
        else:
            showProcucts()
            break


# 5.修改商品价格信息
def setPrice():
    while 1 == 1:
        msg = 0  # 记录商品是否存在
        num = input("请输入要调整价格的商品编号：")
        for product in productsList:
            if num == product["编号"]:
                newPrice = float(input("请输入新的价格："))
                product["价格"] = newPrice  # 设置价格
                print("---商品", product["名称"], "价格已设置成功，", newPrice, "元！")
                msg = 1
                break
        if msg == 0:
            print("商品不存在！")
            choice = int(input("取消请按1，重新输入请按2："))
            if choice == 1:
                break
            else:
                continue
        else:
            showProcucts()
            break


# 6.根据价格排序显示商品列表
def sort():
    choice = int(input("请选择升序或者降序（1.升序  2.降序）："))
    pList = []  # 存放所有价格信息
    for product in productsList:
        pList.append(product["价格"])
    pList = list(set(pList))  # 去掉重复价格

    print("-编号----名称----价格----折扣-")
    if choice == 1:
        newList = sorted(pList)
        for price in newList:
            for product in productsList:
                if price == product["价格"]:
                    print(product["编号"] + "-----" + product["名称"] + "-----" + str(product["价格"]) + "-------" + str(
                        product["折扣"]))
    else:
        newList = sorted(pList, reverse=True)
        for price in newList:
            for product in productsList:
                if price == product["价格"]:
                    print(product["编号"] + "-----" + product["名称"] + "-----" + str(product["价格"]) + "-------" + str(
                        product["折扣"]))


# 模块化
# -------------------------------------
# 显示主菜单，调用已经写好的业务函数

while 0 == 0:
    # result=login()
    # if result=="成功":
    if 1 == 1:
        while 2 == 2:
            print("----------------主菜单---------------")
            print("---1.显示商品列表")
            print("---2.增加商品信息")
            print("---3.删除商品")
            print("---4.设置商品折扣")
            print("---5.修改商品信息")
            print("---6.按照价格排序显示")
            print("---7.退出")

            choice = int(input("请选择业务编号（输入1-6）："))
            if choice == 1:
                showProcucts()
            elif choice == 2:
                addProcuct()
            elif choice == 3:
                delProcuct()
            elif choice == 4:
                setDiscout()
            elif choice == 5:
                setPrice()
            elif choice == 6:
                sort()
            elif choice == 7:
                print("-------------正在退出...")
                break
            else:
                print("没有此功能，请重新选择！")
                continue
```

# 异常

```
# SyntaxError 语法错误
# NameError: name 'b' is not defined  变量名写错
# IndentationError  缩进错误
# ModuleNotFoundError  第三方包未安装
# FileNotFoundError 文件未找到
# AttributeError: 'int' object has no attribute 'eat'  对象没有某个属性和方法
# IndexError: list index out of range 索引越界
print(5/0)
```

## 捕获异常1

```
# try:
#  可能出现异常的代码
# except Exception as e:
#  出现异常时执行的代码

lista = [12, 12, 12, 323, 24, 0, 43, 43, 54, 0, 56, 565, 65, 56]
for s in lista:
    try:
        r = 10 / s
        print(r)
    except Exception as e:  # Exception 捕获的错误类型  e保存具体错误内容
        print("出现错误：", e)
```

## 捕获异常2

```
# try:
#  可能出现异常的代码
# except Exception as e:
#  出现异常时执行的代码
# else:
#  没有出现异常时执行的代码
# finally:
#  无论是否出现异常，都会执行的代码（记录日志,关闭资源）

lista = [12, 12, 12, 323, 24, 0, 43, 43, 54, 0, 56, 565, 65, 56]
for s in lista:
    try:
        r = 10 / s
        print(r)
    except Exception as e:  # Exception 捕获的错误类型  e保存具体错误内容
        print("出现错误：", e)
    else:
        print("正常！")
    finally:
        print("-----执行完毕！")
```

## 自定义异常

```
exp = Exception("性别只能是男或者女！")  # 创建一个异常对象

sex = input("请输入您的性别（男，女）")
if sex == "男" or sex == "女":
    print("您输入的性别：", sex)
else:
    print("您输入的性别有误！")
    raise exp
```

# python连接数据库

```
#python连接数据库
import pymysql

#需要先创建一个数据库，才能连接
host="localhost"
port=3306 #注意使用数字
user="root"
password="123456"
db="51db" #数据库名称
charset="utf8"

#创建数据库连接对象，并建立连接
db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
print("数据库已连接.....")

#.......


#
db.close() #关闭数据库连接
```

## 创建表

```
import pymysql

#需要先创建一个数据库，才能连接
host="localhost"
port=3306 #注意使用数字
user="root"
password="123456"
db="51db" #数据库名称
charset="utf8"

#创建数据库连接对象，并建立连接
db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
print("数据库已连接.....")

#创建游标对象(1.执行sql语句，2.处理数据查询结果)
cursor=db.cursor()

#编写sql语句  列名，列数据类型
sql="CREATE TABLE stu(id int,name varchar(10),age int)"

#执行sql
cursor.execute(sql) 

#提交数据
db.commit() 

#关闭游标
cursor.close()

#关闭数据库连接
db.close() 
```

## 添加数据

```
import pymysql
import random

#需要先创建一个数据库，才能连接
host="localhost"
port=3306 #注意使用数字
user="root"
password="123456"
db="51db" #数据库名称
charset="utf8"

#创建数据库连接对象，并建立连接
db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
print("数据库已连接.....")

#创建游标对象(1.执行sql语句，2.处理数据查询结果)
cursor=db.cursor()

for x in range(3,13):
   num=x #id
   name=random.choice(["王五","赵六","老七","大宝"])
   age=random.choice([2,13,32,32,32,43,35,43])

   #编写sql  拼接时字符串中的单引号需要加上
   sql="INSERT INTO stu VALUES("+str(num)+",'"+name+"',"+str(age)+");"

   cursor.execute(sql) #执行sql
   db.commit() #提交

#关闭
cursor.close()
db.close() 
```

## 删除和修改数据

```
import pymysql
import random

#需要先创建一个数据库，才能连接
host="localhost"
port=3306 #注意使用数字
user="root"
password="123456"
db="51db" #数据库名称
charset="utf8"

#创建数据库连接对象，并建立连接
db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
print("数据库已连接.....")

#创建游标对象(1.执行sql语句，2.处理数据查询结果)
cursor=db.cursor()

#编写sql  拼接时字符串中的单引号需要加上
# sql="DELETE FROM emps WHERE dept='销售部'"
sql="UPDATE emps set salary=salary+2000 WHERE name='老七'"

cursor.execute(sql) #执行sql
db.commit() #提交

#关闭
cursor.close()
db.close() 
```

## 查询数据

```
import pymysql
import random

#需要先创建一个数据库，才能连接
host="localhost"
port=3306 #注意使用数字
user="root"
password="123456"
db="51db" #数据库名称
charset="utf8"

#创建数据库连接对象，并建立连接
db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
print("数据库已连接.....")

#创建游标对象(1.执行sql语句，2.处理数据查询结果)
cursor=db.cursor()

#编写sql  
# sql="SELECT salary FROM emps WHERE name='王五';"
# sql="SELECT * FROM emps WHERE name='王五';"
sql="SELECT * FROM emps;"

cursor.execute(sql) #执行sql
# db.commit() #提交(只在更新操作中使用)

# data=cursor.fetchone() #获取一行数据
data=cursor.fetchall() #获取多行数据
print(data)


#关闭
cursor.close()
db.close() 
```

## 案例：用户登录

```
import pymysql
import random

def getData(sql):
   #需要先创建一个数据库，才能连接
   host="localhost"
   port=3306 #注意使用数字
   user="root"
   password="123456"
   db="51db" #数据库名称
   charset="utf8"

   #创建数据库连接对象，并建立连接
   db=pymysql.Connect(host=host,port=port,user=user,passwd=password,db=db,charset=charset)
   print("数据库已连接.....")
   #创建游标对象(1.执行sql语句，2.处理数据查询结果)
   cursor=db.cursor()
   cursor.execute(sql) #执行sql
   data=cursor.fetchone() #获取一行数

   #关闭
   cursor.close()
   db.close() 

   return data

#登录
def login():
   uname=input("请输入用户名：")
   upwd=input("请输入密码：")
   sql="SELECT * FROM users WHERE username='"+uname+"' and password='"+upwd+"'"
   data=getData(sql)
   if data==None:
      print("失败！")
   else:
      print("成功！")


#
if __name__ == '__main__':
   login()
```

# json

```
#json数据

# java----python

# "name=zhangsan&pwd=123"
# "name:zhangsan,pwd:123"

# json本质上是一个固定格式的字符串

#保存一个学员信息
stu1='{"name":"zhangsan","age":18,"hobby":"play"}'

#保存多个学员信息
stus='[{"name":"zhangsan","age":18,"hobby":"play"},{"name":"lisi","age":18,"hobby":"play"},{"name":"wangwu","age":18,"hobby":"play"}]'
```

### json数据和python数据转换

```
#json数据和python数据转换
import json


#保存一个学员信息
stu1='{"name":"zhangsan","age":18,"hobby":"play"}'

#保存多个学员信息
stus='[\
{"name":"zhangsan","age":18,"hobby":"play"},\
{"name":"lisi","age":15,"hobby":"sleep"},\
{"name":"wangwu","age":17,"hobby":"eat"}\
]'


#1.json转python（转成字典或者列表嵌套字典）
jsonData='{"name":"zhangsan","age":18,"hobby":"play"}'
pythonData=json.loads(jsonData)
# print(pythonData["hobby"])

#2.python转json
pythonData={"cname":"1001","cpwd":"123","cbalance":1000,"name":"张三"}
# r=str(pythonData) #XXXXXXX错误
josnData=json.dumps(pythonData,ensure_ascii=False) #ensure_ascii=False 禁止ascii转换
print(josnData,type(josnData)) 
```

### json模拟数据库

```
#json模拟数据库
#在文本文件中保存json字符，通过文件读写来操作数据
import json

#创建文本文件（数据库文件）
# with open(r"user.txt","w") as f:
#  users='[{"uname":"zhangsan","upwd":"123"},{"uname":"lisi","upwd":"123"},{"uname":"wangwu","upwd":"123"}]'
#  f.write(users)

#读数据（查询）
def readData():
   with open(r"user.txt","r") as f:
      jsonData=f.read()
   usersList=json.loads(jsonData)
   return usersList

#写数据（修改）
def writeData(usersList):
   jsonData=json.dumps(usersList,ensure_ascii=False)
   with open(r"user.txt","w") as f:
      f.write(jsonData)
      print("----数据写入成功！")

#登录
def login():
   name=input("请输入用户名：")
   password=input("请输入密码：")
   usersList=readData() #读取所有用户列表
   msg="失败"
   for user in usersList:
      if name==user["uname"] and password==user["upwd"]:
         msg="成功"
         print("----恭喜登陆成功！")
   if msg=="失败":
      print("----登录失败！")
   return msg


#注册（在数据库中增加用户）
def reg():
   name=input("请输入新用户名：")
   password=input("请输入密码：")
   newuser={"uname":name,"upwd":password} #新用户
   usersList=readData()
   usersList.append(newuser) #将新用户添加到用户列表
   writeData(usersList)
   print("-----新用户添加成功！")

#-------------------------
if __name__ == '__main__':
   login()
```

user.txt

```
[{"uname": "zhangsan", "upwd": "123"}, {"uname": "lisi", "upwd": "123"}, {"uname": "wangwu", "upwd": "123"}, {"uname": "��", "upwd": "234"}]
```

# 人工智能

```
# baudu-aip 人工智能接口
from aip import AipOcr


""" 你的 APPID AK SK """
APP_ID = '23987163'
API_KEY = 'G1zMsGAGOyAKF3VDiYRmQwqy'
SECRET_KEY = 'bToYVIkK4cO1VxpnGjjWyRjThyweuH8v'

#ocr客户端对象
client = AipOcr(APP_ID, API_KEY, SECRET_KEY)

#读取图片
with open(r"C:\Users\mango\Desktop\python代码\file\ss.png","rb") as f:
   img=f.read()

#识别文字
data=client.basicGeneral(img)

for d in data["words_result"]:
   print(d["words"])
```

# pyEmail邮件处理

```
# pyEmail邮件处理

# 客户端1----微信服务器----客户端2
# 客户端1(网易)----网易邮箱服务器-----QQ邮箱服务器------客户端2（QQ）

# 邮箱协议：smtp协议  imap协议  pop协议

import smtplib   #smtp协议包
from email.mime.text import MIMEText #用于构建邮箱内容

msg_from="test666@126.com" #发件人
password="QBVECGFSSZOJARVS" #客户端授权码
msg_to="2268902957@qq.com"   #收件人 


#构造邮件内容
subject="0414测试邮件"
content="你中奖了！5毛钱！"
msg=MIMEText(content)  #msg邮件内容对象
msg["Subject"]=subject
msg["From"]=msg_from
msg["To"]=msg_to


#发送邮件
smtpObj=smtplib.SMTP_SSL("smtp.126.com",465)  #smtpObj smtp对象
smtpObj.login(msg_from,password) #登录
smtpObj.sendmail(msg_from,msg_to,str(msg)) #发送邮件
print("发送成功！")
smtpObj.quit()
```

# tushare股票价格自动监控

```
# tushare股票价格自动监控
# 需求：设置一只股票卖出和买入价格，程序对价格进行监控，当价格达到预定值时发送邮件提醒---盯盘

import tushare
import time

while 1==1:
   buyPoint=5.2
   salePoint=5.6

   data=tushare.get_realtime_quotes("601398")
   name=data.loc[0][0] #名称
   pre_close=float(data.loc[0][2]) #昨收
   price=float(data.loc[0][3])  #现价
   change=round((price-pre_close)/pre_close,4) #今日涨幅
   msg="股票名称："+name+"，当前价格："+str(price)+"元，涨幅："+str(change*100)+"%"
   print(msg)
   if price<=buyPoint:
      print("价格达到买点！如果空仓请买进！")
      print("邮件发送...")
   elif price>=salePoint:
      print("价格达到卖点！如果持仓请卖出！")
   else:
      print("不要做任何操作！")

   time.sleep(5)
```

# requests爬虫

```
#requests爬虫
import requests

#抓包获取音乐的链接
url="https://m801.music.126.net/20210415105529/957f299b2a0aaba6fa28\
e2a8f643edfb/jdyyaac/obj/w5rDlsOJwrLDjj7CmsOj/8304332344/f1c4/df0e/\
4fd8/8625bca4605b72e8cfeb8fda3cc6365a.m4a"

#get()向服务器发送get请求  .content获取二进制数据（.text 获取文本数据）
data=requests.get(url).content

#写入到本地
with open(r"C:\Users\mango\Desktop\python代码\file\音乐0415.m4a","wb") as f:
   f.write(data)
```

# pyecharts 数据可视化

### 商场销售情况

```
# pyecharts 数据可视化

# *******
# pyecharts 是一个用于生成 Echarts 图表的类库。
# Echarts 是百度开源的一个数据可视化 JS 库。
# 用 Echarts 生成的图可视化效果非常棒.

# ***下载：
# pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pyecharts

# ***新版v1和老版本不兼容，如果需要使用老版本，下载：
# pip install pyecharts==0.5.5

import pyecharts
from pyecharts.charts import Bar #柱状图
from pyecharts.charts import Pie #饼图
from pyecharts.charts import Line #折线图
from pyecharts import options as opts  #设置参数

bar=Bar() #创建柱状图对象
bar.add_xaxis(["衬衫","毛衣","裙子","风衣","T恤"]) #添加x轴数据
bar.add_yaxis("A商家销量",[150,67,95,78,99]) #添加y轴数据
bar.add_yaxis("B商家销量",[170,167,145,28,19]) #添加y轴数据
bar.add_yaxis("C商家销量",[120,67,125,58,89]) #添加y轴数据
bar.set_global_opts(title_opts=opts.TitleOpts(title="商场销售情况")) #设置标题
bar.render("商场销售柱状图.html")
```

### 手机销售饼图

```
# pyecharts 数据可视化

import pyecharts
from pyecharts.charts import Bar #柱状图
from pyecharts.charts import Pie #饼图
from pyecharts.charts import Line #折线图
from pyecharts import options as opts  #设置参数

pie=Pie() #创建饼状图对象
cate = ['苹果', '华为', '小米', 'Oppo', 'Vivo', '魅族']
data = [153, 124, 107, 99, 89, 46]
dataList=[] #数据处理
for i in range(0,len(cate)):
   d=[cate[i],data[i]]
   dataList.append(d)
pie.set_global_opts(title_opts=opts.TitleOpts(title="手机销售情况"))
pie.add("单位：万台",dataList)
pie.render("手机销量饼图.html")
```

### 降雨量折线图

```
# pyecharts 数据可视化

import pyecharts
from pyecharts.charts import Bar #柱状图
from pyecharts.charts import Pie #饼图
from pyecharts.charts import Line #折线图
from pyecharts import options as opts  #设置参数


line=Line()

x=["1月","2月","3月","4月","5月","6月"]
y1=[100,200,300,200,100,400]
y2=[50,100,200,300,400,100]

line.add_xaxis(xaxis_data=x)
line.add_yaxis(y_axis=y1,series_name="深圳")
line.add_yaxis(y_axis=y2,series_name="长沙")
line.set_global_opts(title_opts=opts.TitleOpts(title="降雨量折线图"))
line.render("降雨量折线图.html")
```

# TCP通信

## 客户端

```
#客户端：发送消息给服务端
from socket import *

#创建socket对象
#AF_UNIX本机通信 AF_INET（IPV4） AF_INET6（IPV6）
#SOCK_STREAM（TCP）  SOCK_DGRAM（UDP） 
s=socket(AF_INET,SOCK_STREAM)

#和目标建立连接
s.connect(("localhost",6363))

#发送消息
s.send("你好！服务端！".encode())  #.encode()对字符串进行编码

#关闭socket
s.close()
```

## 服务端

```
#服务端：接收客户端消息并显示
from socket import *

#创建socket对象 
s=socket(AF_INET,SOCK_STREAM)

#绑定监听端口
s.bind(("localhost",6363))

#监听
s.listen()

#等待消息
conn,adr=s.accept()

#接收信息
msg=conn.recv(1024)

print("--------:",msg.decode())

s.close()
```

# UDP通信

## 客户端

```
#客户端：发送消息给服务端
from socket import *

#创建socket对象
#AF_UNIX本机通信 AF_INET（IPV4） AF_INET6（IPV6）
#SOCK_STREAM（TCP）  SOCK_DGRAM（UDP） 
s=socket(AF_INET,SOCK_DGRAM)

#发送信息
while 1==1:
   msg=input("---------<<:")
   s.sendto(msg.encode(),("localhost",3435))

#关闭socket
s.close()
```

## 服务端

```
#服务端：接收客户端消息并显示
from socket import *
import time

#创建socket对象 
s=socket(AF_INET,SOCK_DGRAM)

#绑定端口
s.bind(("localhost",3435))

#接收信息
while 1==1:
   msg=s.recv(1024)
   print("----:",msg.decode())

s.close()
```

# 进程

```
import time

for x in range(1,100):
   print(x)
   time.sleep(10)
```

## 多进程

```
# 多进程：一个程序运行过程中，产生了多个进程

# n个正在运行的程序----至少n个进程
# 1个程序-----可能只有一个进程，也可能有多个进程


#引入进程类
from multiprocessing import Process
import time

#任务1
def run1():
   print("执行了任务1！")
   time.sleep(5)

#任务2
def run2():
   print("执行了任务2！")
   time.sleep(5)

#任务3
def run3():
   print("执行了任务3！")
   time.sleep(5)


#--------------------串行
# run1()
# run2()
# run3()


#--------------------并行
#创建进程对象
p1=Process(target=run1)  #(target=要执行的任务方法)
p2=Process(target=run2)
p3=Process(target=run3)

if __name__ == '__main__':
   p1.start() #启动进程,只能写道main中
   p2.start()
   p3.start()
```

## 多线程

```
import threading
import time

def run(name):
   print(name,"执行了任务！")
   time.sleep(5)

#创建线程对象
t1=threading.Thread(target=run,args=("t1",))
t2=threading.Thread(target=run,args=("t2",))
t3=threading.Thread(target=run,args=("t3",))

#启动线程
t1.start()
t2.start()
t3.start()
```

## 主线程和子线程

```
import threading
import time

def run(name):
   time.sleep(5)
   print(name,"执行了任务！")

#程序执行时，程序本身就是一个线程，称为主线程
#手动创建的线程，称为子线程
#主线程执行中不会等待子线程执行完毕，会直接执行后面代码

#创建线程对象
t1=threading.Thread(target=run,args=("t1",))
t2=threading.Thread(target=run,args=("t2",))
t3=threading.Thread(target=run,args=("t3",))

#启动线程
t1.start()
t2.start()
t3.start()

t1.join() #需要等待当前线程执行完毕，才能继续执行主线程
t2.join()
t3.join()

print("执行完毕！")
```

## 线程锁



```
import threading

# 线程锁（互斥锁）：当一个线程设置锁后，只有等到释放锁后，才能调度其他线程
lock=threading.Lock() #创建锁
num=100

def run(name):
   global num
   num-=1
   lock.acquire() #设置锁
   print("线程",name,"执行了,目前num的值为：",num)
   lock.release() #释放锁

for i in range(1,101):
   t=threading.Thread(target=run,args=(i,))
   t.start()
```

## 多线程聊天室

#### A

```
from threading import Thread
from socket import *


# 接收信息
def recvData():
    while 1 == 1:
        msg = s.recv(1024)
        print(">>:", msg.decode())


# 发送信息
def sendData():
    while 1 == 1:
        info = input("<<:")
        s.sendto(info.encode(), (ip, port))


# ----------------------------
ip = "localhost"  # 对方ip
port = 9011  # 对方端口号

s = socket(AF_INET, SOCK_DGRAM)
s.bind(("localhost", 9012))

# 创建线程
tr = Thread(target=recvData)
ts = Thread(target=sendData)

tr.start()
ts.start()
```

#### B

```
from threading import Thread
from socket import *


# 接收信息
def recvData():
    while 1 == 1:
        msg = s.recv(1024)
        print(">>:", msg.decode())


# 发送信息
def sendData():
    while 1 == 1:
        info = input("<<:")
        s.sendto(info.encode(), (ip, port))


# ----------------------------
ip = "localhost"  # 对方ip
port = 9012  # 对方端口号

s = socket(AF_INET, SOCK_DGRAM)
s.bind(("localhost", 9011))

# 创建线程
tr = Thread(target=recvData)
ts = Thread(target=sendData)

tr.start()
ts.start()
```