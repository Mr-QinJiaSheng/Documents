### **【详解】python信息管理系统**



**一、前言**
  花了整整一天时间搞了个python的信息管理系统，完成一大半了突然发现，鱼c已经有@zltzlt大佬做过了，而且功能十分齐全（比我做的好），一时间有点儿懊恼，大家能理解这种心理就好...
  毕竟鱼c只有三种帖子最火，第一种——官方教程等，这个理所当然，没啥意见；第二种——pygame小游戏诸如此类，毕竟原版教程就是冲着这个去的，忍了；第三种——爬取妹子图，花样爬取妹子图，爬取花样妹子图......，我：？？？？
  转念一想，作为后来者，目前我们所做的东西绝大多数都是前人做过的，这本就是一种“前人栽树，后人乘凉”的体现。代码上，我承认以我入门不久的水平是不可能做到超越，不过我可以把整个程序描述的更详细点儿。
 我承认做不到100%的原创，也感谢前人给的参考，具体内容如下，帖子的顺序基本上算是还原了整个程序的制作过程了。
注：
本篇只是简单完成了信息管理系统的基本增删改查功能并注以解释，其余功能未完成或尚待优化之处，今后笔者会尽力更新的，还望读者见谅。
初次运行，请将【数据存储】部分students列表定义代码解除注释并将下方两行读取文件注释掉，避免因json文件不存在而报错。这一不足笔者后续会改善的，见谅
（完成不易，求大家评分支持！！）


**二、代码及详解**

**1、信息管理系统框架**

首先要完成的是打印出一个交互界面（相信大家学c过语言的都有经验），本质上就是一个菜单+死循环，在死循环中，通过input（）函数满足交互需要，并依照菜单所示，完成分支的框架搭建，这部分没什么难度，附上代码和效果图：

    #打印菜单，提示如何操作：
    def menu():
        #菜单以多行字符串打印
        str_menu = """
    \t欢迎使用【学生信息管理系统】
    ********************************************
    请输入您想要进行的操作：
    1.添加指定信息
    2.显示全部信息
    3.查询指定信息
    4.删除指定信息
    5.修改指定信息
    6.打印操作提示
    
    0.退出系统
    ********************************************
    """
        print(str_menu)
    
    menu()
    
    #主体循环
    while True:
        #输入操作：
        action = input("请输入您想要进行的操作：")
       
        #分支判断
        #1.添加指定信息
        if action == "1":
            print("【添加指定信息】")
            pass
       
       
        #2.显示全部信息
        elif action == "2":
           print("【显示全部信息】")
           pass
       
        #3.查询指定信息
        elif action == "3":
           print("【查询指定信息】")
           pass
       
        #4.删除指定信息
        elif action == "4":
           print("【删除指定信息】")
           pass
       
        #5.修改指定信息
        elif action == "5":
           print("【修改指定信息】")
           pass
       
        #6.打印操作提示
        elif action == "6":
           print("【打印操作提示】")
           pass
       
        #0.退出系统
        elif action == "0":
            print("退出【信息管理系统】,欢迎下次使用!")
            break
        #输入错误：
        else:
            print("输入操作不存在,请按提示正确输入!")



![img](https://s1.ax1x.com/2020/09/19/w5xXVA.png)


**2、选择数据存储方式**

 我们知道，数据可以保存在内存中，也可以保存在本地。
 在内存中保存的数据，只在程序执行过程中存在，具有一些局限性，因此我们更提倡另一种方式——以文件形式保存在本地。
 可选的文件格式有很多种，诸如：txt，csv， xml，json，html 以及小甲鱼讲过的pkl， 这里我选择数据格式为json，想用pkl的可以参考https://fishc.com.cn/thread-144923-1-1.html
 针对信息管理系统：多个学员，以列表存储；每个学员，以字典保存各属性及数据；故：列表包含字典来存储。
样例数据为：



```
students = [
        {'name':'李四','chinese':'64','math':'65','English':'66','total':195},
        {'name':'王五','chinese':'65','math':'65','English':'66','total':196},
        {'name':'赵六','chinese':'66','math':'65','English':'66','total':197}
        ]
```

**3、功能实现-打印**

  有了数据，我们从简单的开始，先实现【全部数据打印】：
  即：遍历列表打印字典的值：

![img](https://s1.ax1x.com/2020/09/19/wI98aj.png)


以*解包，（加入分隔符）效果如下：

![img](https://s1.ax1x.com/2020/09/19/wI9rdJ.png)

这部分的代码如下：

```
#显示全部信息
def print_info():
    print('姓名    语文    数学    英语    总分')
    for student in students:
        print(*student.values(),sep="     ")
```


**4、功能实现-插入**

 我们知道，每个学员的信息以字典的形式储存在列表students中，所以插入分为两步;
【收集信息】->【添加到students列表】
收集信息时应注意，input函数返回的为字符串类型，所以作为成绩相加应该转为int
代码及效果图如下：

```
#添加指定信息
def insert():
    #收集（输入）信息
    name = input('请输入学生姓名：')
    chinese = int(input('请输入学生语文成绩：'))
    math = int(input('请输入学生数学成绩：'))
    English = int(input('请输入学生英语成绩：'))
    total = chinese + math + English
    
    #添加到students列表中
students.append(
         {'name':name,'chinese':chinese,'math':math,'English':English,'total':total}
        )
```



![img](https://s1.ax1x.com/2020/09/19/wICB1P.png)


**5、功能实现-查找**

查找的本质是从students列表里面查找，但实际的操作对象确实内部的字典。
因此，需要将列表数据一个个取出来（遍历），然后对比字典name项。
存在一个问题，在找不到的情况下能直接搭配if使用else吗？

错误代码：



```
def search():
   name = input('请输入需查询学生姓名：')
   
   for student in students: #遍历列表
     if name == student['name']: #对比字典的name
       print('姓名  语文  数学  英语  总分')
     print(*student.values(),sep="   ")
   
    else:
      print("该学生不存在！")
```





产生的效果如下：


![img](https://s1.ax1x.com/2020/09/19/wIPNuT.png)

【解决方案】：else与for搭配使用，在执行完for后会执行else
众鱼友：好像还是不对啊？
当然，需要在if判断查找到后加一个break，跳出for循环，之后的else自然就不会再执行了。反之，当没有查找到时，自然就不会执行break，else照常打印。

正确代码：


    

    def search():
        name = input('请输入需查询学生姓名：')
        for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            print('姓名    语文    数学    英语    总分')
            print(*student.values(),sep="     ")
            break
    else:
        print("该学生不存在！")



效果图：

![img](https://s1.ax1x.com/2020/09/19/wIPygx.png)



**5、功能实现-删除和修改**

自不必多说，苍老师说过：“能找到，就能为所欲为”
你会发现这部分和查找何其相似（搬砖暴露了）。
代码如下：



    #删除指定信息√
    def delete_info():
        name = input('请输入需删除的学生姓名：')
        
    for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            students.remove(student)
            break
    else:
        print("该学生不存在！")
        #修改指定信息√
    def modify_info():
        name = input('请输入需修改的学生姓名：')
        for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            student['name']= input('请输入更新后学生姓名：')
            student['chinese'] = int(input('请输入更新后学生语文成绩：'))
            student['math']  = int(input('请输入更新后学生数学成绩：'))
            student['English'] = int(input('请输入更新后学生英语成绩：'))
            student['total']  = student['chinese'] +student['math'] + student['English']
            break
    else:
        print("该学生不存在！")



效果图如下：


![img](https://s1.ax1x.com/2020/09/19/wIFZm8.png)

![img](https://s1.ax1x.com/2020/09/19/wIFKYj.png)


**6、功能实现-保存与后期读取**

本程序默认退出程序时自动将内存中的students列表以json格式保存到本地。代码位于最后部分以with语句嵌入：

```
 #0.退出系统（自动保存到本地json形式）
    elif action == "0":
        print("退出【学生信息管理系统】")
        print("欢迎下次使用!")
        with open("data.json",mode='w',encoding="utf-8") as f:
             #将对象写入文件而不改变格式
            #f.write(json.dumps(students)) #这样写json格式中文会是“乱码”
            f.write(json.dumps(students,ensure_ascii=False))
        break
```

所谓“乱码”即为json格式里中文的sacii码，在dumps方法中加入ensure_ascii=False参数即可正确显示中文内容。
json格式中文“乱码”及修正后效果图：

![img](https://s1.ax1x.com/2020/09/19/wIAwsx.png)      ![img](https://s1.ax1x.com/2020/09/19/wIADeK.png)



后期读取代码在【数据存储】部分，这部分可与初始化时students列表相互替代：

```
with open("data.json",mode='r',encoding="utf-8") as f:
    students = json.loads(f.read()) #注：read读取出来的时字符串，需要转为json对象

```

**三、全部代码**

```

"""
Created on Fri Sep 18 23:37:54 2020
【学生信息管理系统】
注：
1.保存功能在退出系统时自动执行
2.首次执行时，请将【数据存储】部分students列表解除注释，并注释下方json读取
  第二次及其以后执行时，json文件已生成在本地，可以按当前代码执行
3.尚未完成排序功能，有需要者请参考@zltzlt老师代码，十分抱歉
4.操作六的意义在于，此处menu菜单只在首次打印，后续如果操作内容覆盖上方菜单
  执行六查看操作说明较为便利
  
@author: 昨非
"""

import json  #以json格式写入文件时要用到
"==========================数据存储==========================="
#多个学员-列表存储，单个学员-字典存储   保存格式-json
#students = [
#        {'name':'李四','chinese':'64','math':'65','English':'66','total':195},
#        {'name':'王五','chinese':'65','math':'65','English':'66','total':196},
#        {'name':'赵六','chinese':'66','math':'65','English':'66','total':197}
#        ]

'''
在初次执行之后，假设data.json文件已经存在，
就可以采取读取的方法进行操作了，如下：
'''
with open("data.json",mode='r',encoding="utf-8") as f:
    students = json.loads(f.read()) #注：read读取出来的时字符串，需要转为json对象




"==========================功能实现==========================="

#添加指定信息√
def insert():
    #收集（输入）信息
    name = input('请输入学生姓名：')
    chinese = int(input('请输入学生语文成绩：'))
    math = int(input('请输入学生数学成绩：'))
    English = int(input('请输入学生英语成绩：'))
    total = chinese + math + English
    
    #添加到students列表中
    students.append(
             {'name':name,'chinese':chinese,'math':math,'English':English,'total':total}
            )


#显示全部信息√
def print_info():
    print('姓名    语文    数学    英语    总分')
    for student in students:
        print(*student.values(),sep="     ")#解包并加分隔符美化
    

#查找指定信息√
def search():
    name = input('请输入需查询学生姓名：')
    
    for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            print('姓名    语文    数学    英语    总分')
            print(*student.values(),sep="     ")
            break
    else:
        print("该学生不存在！")
        
            
#删除指定信息√
def delete_info():
    name = input('请输入需删除的学生姓名：')
    
    for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            students.remove(student)
            break
    else:
        print("该学生不存在！")

#修改指定信息√
def modify_info():
    name = input('请输入需修改的学生姓名：')
    
    for student in students: #遍历列表
        if name == student['name']: #对比字典的name
            student['name']= input('请输入更新后学生姓名：')
            student['chinese'] = int(input('请输入更新后学生语文成绩：'))
            student['math']  = int(input('请输入更新后学生数学成绩：'))
            student['English'] = int(input('请输入更新后学生英语成绩：'))
            student['total']  = student['chinese'] +student['math'] + student['English']
            break
    else:
        print("该学生不存在！")
             
#打印操作提示√
def print_tips():
    str_tips = """
********************************************
1.添加指定信息
2.显示全部信息
3.查询指定信息
4.删除指定信息
5.修改指定信息
6.打印操作提示
0.退出系统
********************************************
"""
    print(str_tips)



"==========================主体框架==========================="
#打印菜单，提示如何操作：
def menu():
    #菜单以多行字符串打印
    str_menu = """
\t欢迎使用【学生信息管理系统】
********************************************
请输入您想要进行的操作：
1.添加指定信息
2.显示全部信息
3.查询指定信息
4.删除指定信息
5.修改指定信息
6.打印操作提示

0.退出系统
********************************************
"""
    print(str_menu)

menu()

#主体循环
while True:
    #输入操作：
    action = input("请输入您想要进行的操作：")
    
    #分支判断
    #1.添加指定信息
    if action == "1":
        print("【添加指定信息】")
        insert()
    
    
    #2.显示全部信息
    elif action == "2":
       print("【显示全部信息】")
       print_info()
    
    #3.查询指定信息
    elif action == "3":
       print("【查询指定信息】")
       search()
    
    #4.删除指定信息
    elif action == "4":
       print("【删除指定信息】")
       delete_info()
    
    #5.修改指定信息
    elif action == "5":
       print("【修改指定信息】")
       modify_info()
    
    #6.打印操作提示
    elif action == "6":
       print("【打印操作提示】")
       print_tips()
       
    
    #0.退出系统（自动保存到本地json形式）
    elif action == "0":
        print("退出【学生信息管理系统】")
        print("欢迎下次使用!")
        with open("data.json",mode='w',encoding="utf-8") as f:
             #将对象写入文件而不改变格式
            #f.write(json.dumps(students)) #这样写json格式中文会是乱码
            f.write(json.dumps(students,ensure_ascii=False))
        break
    
    #输入错误
    else:
        print("输入操作不存在,请按提示正确输入!")
    

```


**
四、更新部分**

**1、更新内容概述：**

（1）、数据存储部分，排除初次运行时json文件不存在需要手动修改代码的不便
（2）、部分注释内容不准确
（3）、数据结构中加入唯一ID解决按名字查找的重名问题
（4）、添加（多标准）排序功能 



**2、具体内容
**

关于问题一，笔者通过加入打开文件的异常处理解决，这样即保留了必要的初始数据，也不会影响到后续读取文件已有内容。
代码如下：

```
try:
    with open("data.json",mode='r',encoding="utf-8") as f:
        students = json.loads(f.read())
        #注：read读取出来的时字符串，需要转为json对象

except FileNotFoundError:
    students = [  #初始数据，初次运行时避免文件打开报错
        {'id':'20200001','name':'李四','chinese':'64','math':'65','English':'66','total':195},
        {'id':'20200002','name':'王五','chinese':'65','math':'65','English':'66','total':196},
        {'id':'20200003','name':'赵六','chinese':'66','math':'65','English':'66','total':197}
        ]

```


关于问题二、三，内容在此不作赘述，详情请参考下方更新后的代码，有不足或可改进之处，欢迎评论指出。


**新增排序功能部分：**

列表的sort方法可以实现将一个列表中元素按照升序排列。然后，sort方法还可以按照我们选定的标准进行元素排序。

```
list.sort(key=None, reverse=False)
```

key：匹配一个一元的函数或者表达式，按照这个值决定对应元素在列表中的位置。这里我们定义一个函数sort_key()来作为标准，并利用交互界面提供给用户选择标准的操作空间。
reverse: 一个布尔值，若是True，表示要逆序即从大到小，False表示顺序从小到大。
排序部分代码如下：

```
#自定义排序（按各成绩）
def sorted_by_grade():
    sort_way = input(
                "请选择排序方式:\n"
                "1按语文成绩排序\n"
                "2按数学成绩排序\n"
                "3按英语成绩排序\n"
                "0按总成绩排序")
    while sort_way not in ['0', '1', '2', '3']:
        sort_way = input(
                    "输入无效！请选择排序方式:\n"
                    "1按语文成绩排序\n"
                    "2按数学成绩排序\n"
                    "3按英语成绩排序\n"
                    "0按总成绩排序")
    if sort_way == '0':
        def sort_key(x):
            return x['total']
    elif sort_way == '1':
        def sort_key(x):
            return int(x['chinese'])
    elif sort_way == '2':
        def sort_key(x):
            return int(x['math'])
    else:
        def sort_key(x):
            return int(x['English'])
    new_students = sorted(students, key=sort_key, reverse=True)
    print(title) #打印
    for student in new_students:
        print(*student.values(),sep="\t")  
```

排完序后，可以由用户选择是否保存到本地，代码如下：

```
    #保存入文件
    save_in = input("是否将默认学号顺序存入文件 (y/n)？")
    while save_in not in ['y', 'n']:
        save_in = input("输入无效！是否保存 (y/n)？")
    if save_in == 'y':
         f = open("data.json",mode='w',encoding="utf-8")       
         f.write(json.dumps(new_students,ensure_ascii=False))
         print('保存成功！')
    else:
        print('排序结果如上！')
        print('如之后还有需要，请重新排序或选择存入文件！')
```

但笔者在测试时却出现了问题，即：排序后结果正确打印，选择保存到本地后，在此调用print_info()函数发现，打印顺序仍为排序前的顺序。整体语法上没有报错，那么问题只会出现在逻辑上。

经反复检查，发现问题所在：
函数中排序后的new_students列表是区别于students列表的局部变量，而在打印函数中，打印的始终是students列表。
有鱼友可能会问，退出系统（自动保存）后再运行不就好了吗？
但是还是不对的：退出系统的自动保存students 会覆盖排序后的new_students的保存效果。

为此，笔者专门去查看了一下@zltzlt的代码（连接见上文），发现他的每个函数都是独立打开文件并关闭实现操作的，而笔者的初衷是将students列表作为自始至终的操作对象。

【解决办法】：在调用环节嵌入文件读取，对new_students列表刚刚保存进去的数据进行读取，并依旧使用students作为列表名称。

代码如下：

```
    #7.恢复默认顺序（学号顺序）
    elif action == "7":
        print("【恢复默认学号顺序】")
        sorted_by_id()#存入重新打开
        with open("data.json",mode='r',encoding="utf-8") as f:
            students = json.loads(f.read())
        
    #8.自定义排序（按各成绩）
    elif action == "8":
        print("【自定义排序（按各成绩）】")    
        sorted_by_grade()#存入重新打开
        with open("data.json",mode='r',encoding="utf-8") as f:
            students = json.loads(f.read())
        
```

完成排序的效果图如下：
id默认排序：
![img](https://s1.ax1x.com/2020/09/23/wjMEXn.png)

成绩排序：
![img](https://s1.ax1x.com/2020/09/23/wjG8je.png)

**
3、更新后全部代码**

```

"""
Re edited on September 22 20:45:10 2020
【学生信息管理系统-2.0】
更新说明：
1、数据存储部分，排除初次运行时json文件不存在需要手动修改代码的不便
2、部分注释内容不准确
3、数据结构中加入唯一ID解决按名字查找的重名问题
4、添加（多标准）排序功能  
@author: 昨非
"""

import json  #以json格式写入文件时要用到
"==========================数据存储==========================="
#多个学员-列表存储，单个学员-字典存储   保存格式-json
#程序运行时，操作对象始终为students列表
try:
    with open("data.json",mode='r',encoding="utf-8") as f:
        students = json.loads(f.read())
        #注：read读取出来的时字符串，需要转为json对象

except FileNotFoundError:
    students = [  #初始数据，初次运行时避免文件打开报错
        {'id':'20200001','name':'李四','chinese':'64','math':'65','English':'66','total':195},
        {'id':'20200002','name':'王五','chinese':'65','math':'65','English':'66','total':196},
        {'id':'20200003','name':'赵六','chinese':'66','math':'65','English':'66','total':197}
        ]

#表格标题，以全局变量形式存储
title = ''
title += 'ID'.ljust(16)
title += '姓名'.ljust(7)
title += '语文'.ljust(7)
title += '数学'.ljust(6)
title += '英语'.ljust(6)
title += '总成绩'.ljust(5)

"==========================功能实现==========================="

#添加指定信息√(1更：√)
def insert():
    #收集（输入）信息
    _id = input('请输入学生学号：')
    name = input('请输入学生姓名：')
    chinese = int(input('请输入学生语文成绩：'))
    math = int(input('请输入学生数学成绩：'))
    English = int(input('请输入学生英语成绩：'))
    total = chinese + math + English
    
    #添加到students列表中
    students.append(
             {'id':_id,'name':name,'chinese':chinese,'math':math,'English':English,'total':total}
            )
    print("信息添加成功！")
    

#显示全部信息√(1更：√)
def print_info():
    print(title)
    for student in students:
        print(*student.values(),sep="\t")#解包并加分隔符美化
    

#查找指定信息√(1更：√)
def search():
    _id = input('请输入需查询学生学号：')
    
    for student in students: #遍历列表
        if _id == student['id']: #对比字典的id
            print(title)
            print(*student.values(),sep="\t")
            break
    else:
        print("该学生不存在！")
        
            
#删除指定信息√(1更：√)
def delete_info():
    _id = input('请输入需删除的学生学号：')
    
    for student in students: #遍历列表
        if _id == student['id']: #对比字典的name
            students.remove(student)
            print("信息删除成功！")
            break
    else:
        print("该学生不存在！")

#修改指定信息√(1更：√)
def modify_info():
    _id = input('请输入需修改的学生学号：')
    
    for student in students: #遍历列表
        if _id == student['id']: #对比字典的name
            student['name']= input('请输入更新后学生姓名：')
            student['chinese'] = int(input('请输入更新后学生语文成绩：'))
            student['math']  = int(input('请输入更新后学生数学成绩：'))
            student['English'] = int(input('请输入更新后学生英语成绩：'))
            student['total']  = student['chinese'] +student['math'] + student['English']
            print("信息修改成功！")
            break
    else:
        print("该学生不存在！")
             
#打印操作提示√
def print_tips():
    str_tips = """
********************************************
1.添加指定信息
2.显示全部信息
3.查询指定信息
4.删除指定信息
5.修改指定信息
6.打印操作提示
0.退出系统（自动保存）
********************************************
"""
    print(str_tips)


#恢复默认顺序（学号顺序）
def sorted_by_id():
    #自定义排序标准
    def sort_key(x):
            return x['id']
    new_students = sorted(students, key=sort_key)
    print(title)
    for student in new_students:
        print(*student.values(),sep="\t")
    #保存入文件
    save_in = input("是否将默认学号顺序存入文件 (y/n)？")
    while save_in not in ['y', 'n']:
        save_in = input("输入无效！是否保存 (y/n)？")
    if save_in == 'y':
         f = open("data.json",mode='w',encoding="utf-8")       
         f.write(json.dumps(new_students,ensure_ascii=False))
         print('保存成功！')
    else:
        print('排序结果如上！')
        print('如之后还有需要，请重新排序或选择存入文件！')


#自定义排序（按各成绩）
def sorted_by_grade():
    sort_way = input(
                "请选择排序方式:\n"
                "1按语文成绩排序\n"
                "2按数学成绩排序\n"
                "3按英语成绩排序\n"
                "0按总成绩排序")
    while sort_way not in ['0', '1', '2', '3']:
        sort_way = input(
                    "输入无效！请选择排序方式:\n"
                    "1按语文成绩排序\n"
                    "2按数学成绩排序\n"
                    "3按英语成绩排序\n"
                    "0按总成绩排序")
    if sort_way == '0':
        def sort_key(x):
            return x['total']
    elif sort_way == '1':
        def sort_key(x):
            return int(x['chinese'])
    elif sort_way == '2':
        def sort_key(x):
            return int(x['math'])
    else:
        def sort_key(x):
            return int(x['English'])
    new_students = sorted(students, key=sort_key, reverse=True)
    print(title) #打印
    for student in new_students:
        print(*student.values(),sep="\t")    
    #保存入文件
    save_in = input("是否将新顺序存入文件 (y/n)？")
    while save_in not in ['y', 'n']:
        save_in = input("输入无效！是否保存 (y/n)？")
    if save_in == 'y':
         f = open("data.json",mode='w',encoding="utf-8")       
         f.write(json.dumps(new_students,ensure_ascii=False))
         print('保存成功！')
    else:
        print('排序结果如上！')
        print('如之后还有需要，请重新排序或选择存入文件！')    



"==========================主体框架==========================="
#打印菜单，提示如何操作：
def menu():
    #菜单以多行字符串打印
    str_menu = """
\t欢迎使用【信息管理系统-2.0】
********************************************
请输入您想要进行的操作：
1.添加指定信息
2.显示全部信息
3.查询指定信息
4.删除指定信息
5.修改指定信息
6.打印操作提示
7.恢复默认顺序（学号顺序）
8.自定义排序（按各成绩）

0.退出系统（自动保存）
********************************************
"""
    print(str_menu)
    
menu()

#主体循环
while True:
    #输入操作：
    action = input("请输入您想要进行的操作：")
    
    #分支判断
    #1.添加指定信息
    if action == "1":
        print("【添加指定信息】")
        insert()
    
    
    #2.显示全部信息
    elif action == "2":
       print("【显示全部信息】")
       print_info()
    
    #3.查询指定信息
    elif action == "3":
       print("【查询指定信息】")
       search()
    
    #4.删除指定信息
    elif action == "4":
       print("【删除指定信息】")
       delete_info()
    
    #5.修改指定信息
    elif action == "5":
       print("【修改指定信息】")
       modify_info()
    
    #6.打印操作提示
    elif action == "6":
       print("【打印操作提示】")
       print_tips()
       
    #7.恢复默认顺序（学号顺序）
    elif action == "7":
        print("【恢复默认学号顺序】")
        sorted_by_id()#存入重新打开
        with open("data.json",mode='r',encoding="utf-8") as f:
            students = json.loads(f.read())
        
    #8.自定义排序（按各成绩）
    elif action == "8":
        print("【自定义排序（按各成绩）】")    
        sorted_by_grade()#存入重新打开
        with open("data.json",mode='r',encoding="utf-8") as f:
            students = json.loads(f.read())
        
        
    #0.退出系统（自动保存到本地json形式）
    elif action == "0":
        print("退出【学生信息管理系统】")
        print("欢迎下次使用!")
        with open("data.json",mode='w',encoding="utf-8") as f:
             #将对象写入文件而不改变格式
            #f.write(json.dumps(students)) #这样写json文件里中文显示为其ASCII码
            f.write(json.dumps(students,ensure_ascii=False))
            #故加入ensure_ascii参数正确显示中文
        break
    
    #输入错误
    else:
        print("输入操作不存在,请按提示正确输入!")
    
```


**五、结语**

  感谢众多鱼友提出的宝贵建议，根据这几天大家的提示，我把我能做出来的部分都做了，可能依旧微不足道。
至今还没有完成的内容：
一、加入图形化界面：这个笔者学的不到家，还做不出来，不过今后如果我学会了，可以考虑补上。
二、调整数据结构以优化运行速度：首先感谢您的宝贵意见，但是以笔者的水平，只能说暂时还考虑不到哪一步了，所以十分抱歉。

  这篇帖子从代码到排版花了好久才完成，首先是真正意义上体会了一遍小甲鱼作扩展阅读之类教程的不容易。和甲鱼哥的目的差不多，这篇内容主要面向新手，所以没有什么太过硬核的东西，之前有鱼友评论说有些内容描述不准确，希望理解下，谢谢。
  内容上，我已经尽力完善了整个信息管理系统的功能，我知道这类代码随便一搜就是一大堆，这也是我在篇头说看到已经有人发过了而感到有些负面情绪的原因。但我也可以肯定，我应该是这里面写的最详细的一批了。

**比不过大佬的游戏、爬虫那么吸引眼球，但也求一波评分支持!
Best wishes to FishC !**