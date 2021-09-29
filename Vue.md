推荐大家安装的 VScode 中的 Vue 插件

1. Vue 3 Snippets     https://marketplace.visualstudio.com/items?itemName=hollowtree.vue-snippets
2. Vetur                    https://marketplace.visualstudio.com/items?itemName=octref.vetur



### 什么是 vue

1. 构建用户界面
   + 用 vue 往 html 页面中填充数据，非常的方便
2. 框架
   + 框架是一套现成的解决方案，程序员只能遵守框架的规范，去编写自己的业务功能！
   + 要学习 vue，就是在学习 vue 框架中规定的用法！
   + vue 的指令、组件（是对 UI 结构的复用）、路由、Vuex、vue 组件库
   + 只有把上面老师罗列的内容掌握以后，才有开发 vue 项目的能力！



### vue 的两个特性

1. 数据驱动视图：

   + 数据的变化**会驱动视图**自动更新
   + 好处：程序员只管把数据维护好，那么页面结构会被 vue 自动渲染出来！

2. 双向数据绑定：

   > 在网页中，form 表单负责**采集数据**，Ajax 负责**提交数据**。

   + js 数据的变化，会被自动渲染到页面上
   + 页面上表单采集的数据发生变化的时候，会被 vue 自动获取到，并更新到 js 数据中

> 注意：数据驱动视图和双向数据绑定的底层原理是 MVVM（Mode 数据源、View 视图、ViewModel 就是 vue 的实例）



## vue 指令



### 1. 内容渲染指令

1. `v-text` 指令的缺点：会覆盖元素内部原有的内容！
2. `{{ }}` 插值表达式：在实际开发中用的最多，只是内容的占位符，不会覆盖原有的内容！
3. `v-html` 指令的作用：可以把带有标签的字符串，渲染成真正的 HTML 内容！

![image-20210925135835751](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135835751.png)

### 2. 属性绑定指令

>  注意：插值表达式只能用在元素的**内容节点**中，不能用在元素的**属性节点**中！

+ 在 vue 中，可以使用 `v-bind:` 指令，为元素的属性动态绑定值；

+ 简写是英文的 `:`

+ 在使用 v-bind 属性绑定期间，如果绑定内容需要进行动态拼接，则字符串的外面应该包裹单引号，例如：

  ```xml
  <div :title="'box' + index">这是一个 div</div>
  ```

![image-20210925135843272](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135843272.png)

### 3. 事件绑定

![image-20210925135900366](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135900366.png)

1. `v-on:` 简写是 `@`

2. 语法格式为：

   ```xml
   <button @click="add"></button>
   
   methods: {
      add() {
   			// 如果在方法中要修改 data 中的数据，可以通过 this 访问到
   			this.count += 1
      }
   }
   ```

3. `$event` 的应用场景：如果默认的事件对象 e 被覆盖了，则可以手动传递一个  $event。例如：

   ```xml
   <button @click="add(3, $event)"></button>
   
   methods: {
      add(n, e) {
   			// 如果在方法中要修改 data 中的数据，可以通过 this 访问到
   			this.count += 1
      }
   }
   ```

4. 事件修饰符：

   + `.prevent`

     ```xml
     <a @click.prevent="xxx">链接</a>
     ```

   + `.stop`

     ```xml
     <button @click.stop="xxx">按钮</button>
     ```

     ![image-20210923133508629](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923133508629.png)

### 4. v-model 指令

![image-20210925135917664](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135917664.png)

1. input 输入框
   + type="radio"
   + type="checkbox"
   + type="xxxx"
2. textarea
3. select

![image-20210923133606183](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923133606183.png)

### 5. 条件渲染指令

![image-20210925135930462](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135930462.png)

1. `v-show` 的原理是：动态为元素添加或移除 `display: none` 样式，来实现元素的显示和隐藏
   + 如果要频繁的切换元素的显示状态，用 v-show 性能会更好
2. `v-if` 的原理是：每次动态创建或移除元素，实现元素的显示和隐藏
   + 如果刚进入页面的时候，某些元素默认不需要被展示，而且后期这个元素很可能也不需要被展示出来，此时 v-if 性能更好

>  在实际开发中，绝大多数情况，不用考虑性能问题，直接使用 v-if 就好了！！！

![image-20210923133629941](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923133629941.png)

v-if 指令在使用的时候，有两种方式：

1. 直接给定一个布尔值 true 或 false

   ```xml
   <p v-if="true">被 v-if 控制的元素</p>
   ```

2. 给 v-if 提供一个判断条件，根据判断的结果是 true 或 false，来控制元素的显示和隐藏

   ```xml
   <p v-if="type === 'A'">良好</p>
   ```

   ### 6.列表渲染指令
   
   ![image-20210925135948274](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135948274.png)
   
   ![image-20210923134329387](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923134329387.png)

![image-20210923134341753](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923134341753.png)

![image-20210923134402909](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923134402909.png)

![image-20210923134411020](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923134411020.png)



## 过滤器

![image-20210925140003777](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140003777.png)

### 过滤器的注意点

1. 要定义到 filters 节点下，**本质是一个函数**
2. 在过滤器函数中，**一定要有 return 值**
3. 在过滤器的形参中，可以获取到“管道符”前面待处理的那个值
4. 如果全局过滤器和私有过滤器名字一致，此时按照“**就近原则**”，调用的是”私有过滤器“

### 私有过滤器

![image-20210925135550713](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135550713.png)

### 全局过滤器

![image-20210925135617459](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135617459.png)

## watch 侦听器

![image-20210925135754381](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135754381.png)

### 侦听器的格式

1. 方法格式的侦听器
   + 缺点1：无法在刚进入页面的时候，自动触发！！！
   + 缺点2：如果侦听的是一个对象，如果对象中的属性发生了变化，不会触发侦听器！！！
2. 对象格式的侦听器
   + 好处1：可以通过 **immediate** 选项，让侦听器自动触发！！！
   + 好处2：可以通过 **deep** 选项，让侦听器深度监听对象中每个属性的变化！！！



## 计算属性

![image-20210925135812409](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925135812409.png)

特点：

1. 定义的时候，要被定义为“方法”
2. 在使用计算属性的时候，当普通的属性使用即可

好处：

1. 实现了代码的复用
2. 只要计算属性中依赖的数据源变化了，则计算属性会自动重新求值！

![image-20210923143225945](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923143225945.png)

![image-20210923143247045](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923143247045.png)

## axios

> axios 是一个专注于网络请求的库！



![image-20210923143623843](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923143623843.png)

![image-20210923143925445](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923143925445.png)



### axios 的基本使用

1. 发起 GET 请求：

   ```js
   axios({
     // 请求方式
     method: 'GET',
     // 请求的地址
     url: 'http://www.liulongbin.top:3006/api/getbooks',
     // URL 中的查询参数
     params: {
       id: 1
     }
   }).then(function (result) {
     console.log(result)
   })
   ```

2. 发起 POST 请求：

3. ![image-20210923150628758](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923150628758.png)

   ```js
   document.querySelector('#btnPost').addEventListener('click', async function () {
     // 如果调用某个方法的返回值是 Promise 实例，则前面可以添加 await！
     // await 只能用在被 async “修饰”的方法中
     const { data: res } = await axios({
       method: 'POST', 
       url: 'http://www.liulongbin.top:3006/api/post',
       data: {
         name: 'zs',
         age: 20
       }
     })
   
     console.log(res)
   })
   ```

   ![image-20210923145924568](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923145924568.png)

   ### 解构赋值

   ![image-20210923150537736](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923150537736.png)

![image-20210923145805607](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923145805607.png)

![](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923145316988.png)

![image-20210923145338081](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923145338081.png)

## vue-cli 的使用

![image-20210923151615413](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210923151615413.png)

1. 在终端下运行如下的命令，创建指定名称的项目：

   ```bash
   vue cerate 项目的名称
   ```

2. vue 项目中 src 目录的构成：

   ```
   assets 文件夹：存放项目中用到的静态资源文件，例如：css 样式表、图片资源
   components 文件夹：程序员封装的、可复用的组件，都要放到 components 目录下
   main.js 是项目的入口文件。整个项目的运行，要先执行 main.js
   App.vue 是项目的根组件。
   ```

   ### vue组件的三个组成部分
   
   ![image-20210925140042897](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140042897.png)
   
   ![image-20210924124829882](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124829882.png)
   
   ![image-20210924124852057](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124852057.png)
   
   ![image-20210924124908491](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124908491.png)
   
   ![image-20210924124931997](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124931997.png)
   
   ![image-20210924124954170](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124954170.png)
   
   ## **组件之间的****父子关系**
   
   ![image-20210924125036716](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125036716.png)
   
   ![image-20210924125053269](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125053269.png)
   
   ![image-20210924125105853](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125105853.png)
   
   ![image-20210924125116702](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125116702.png)
   
   ## 组件props
   
   ![image-20210925140434156](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140434156.png)
   
   ![image-20210924124707559](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124707559.png)
   
   ![image-20210924125158348](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125158348.png)
   
   ![image-20210924124257217](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124257217.png)
   
   ![image-20210924124355619](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924124355619.png)

![image-20210924125247375](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924125247375.png)

![image-20210924130225047](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924130225047.png)

![image-20210924130236815](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924130236815.png)

![image-20210924130335654](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924130335654.png)

![image-20210924131352536](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924131352536.png)

![image-20210924131108851](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924131108851.png)

## 生命周期

![image-20210925140109260](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140109260.png)

### **1.** **生命周期** **&** **生命周期函数**

生命周期（Life Cycle）是指一个组件从创建 -> 运行 -> 销毁的整个阶段，强调的是一个时间段。生命周期函数：是由 vue 框架提供的内置函数，会伴随着组件的生命周期，自动按次序执行。

注意：生命周期强调的是时间段，生命周期函数强调的是时间点。

![image-20210924132339691](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132339691.png)

![image-20210924134627238](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924134627238.png)

![image-20210924140519513](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924140519513.png)

![image-20210924141159762](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924141159762.png)

![image-20210924141733066](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924141733066.png)

![image-20210924142432928](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924142432928.png)

```vue
<template>
  <div class="test-container">
    <h3 id="myh3">Test.vue 组件 --- {{ books.length }} 本图书</h3>
    <p id="pppp">message 的值是：{{ message }}</p>
    <button @click="message += '~'">修改 message 的值</button>
  </div>
</template>

<script>
export default {
  props: ['info'],
  data() {
    return {
      message: 'hello vue.js',
      // 定义 books 数组，存储的是所有图书的列表数据。默认为空数组！
      books: []
    }
  },
  watch: {
    message(newVal) {
      console.log('监视到了 message 的变化：' + newVal)
    }
  },
  methods: {
    show() {
      console.log('调用了 Test 组件的 show 方法！')
    },
    // 使用 Ajax 请求图书列表的数据
    initBookList() {
      const xhr = new XMLHttpRequest()
      xhr.addEventListener('load', () => {
        const result = JSON.parse(xhr.responseText)
        console.log(result)
        this.books = result.data
      })
      xhr.open('GET', 'http://www.liulongbin.top:3006/api/getbooks')
      xhr.send()
    }
  },
  // 创建阶段的第1个生命周期函数
  beforeCreate() {
    // console.log(this.info)
    // console.log(this.message)
    // this.show()
  },
  created() {
    // created 生命周期函数，非常常用。
    // 经常在它里面，调用 methods 中的方法，请求服务器的数据。
    // 并且，把请求到的数据，转存到 data 中，供 template 模板渲染的时候使用！
    this.initBookList()
  },
  beforeMount() {
    // console.log('beforeMount')
    // const dom = document.querySelector('#myh3')
    // console.log(dom)
  },
  // 如果要操作当前组件的 DOM，最早，只能在 mounted 阶段执行
  mounted() {
    // console.log(this.$el)
    // const dom = document.querySelector('#myh3')
    // console.log(dom)
  },
  beforeUpdate() {
    // console.log('beforeUpdate')
    // console.log(this.message)
    // const dom = document.querySelector('#pppp')
    // console.log(dom.innerHTML)
  },
  // 当数据变化之后，为了能够操作到最新的 DOM 结构，必须把代码写到 updated 生命周期函数中
  updated() {
    // console.log('updated')
    // console.log(this.message)
    // const dom = document.querySelector('#pppp')
    // console.log(dom.innerHTML)
  },
  beforeDestroy() {
    console.log('beforeDestroy')
    this.message = 'aaa'
    console.log(this.message)
  },
  destroyed() {
    console.log('destroyed')
    // this.message = 'aaa'
  }
}
</script>

<style lang="less" scoped>
.test-container {
  background-color: pink;
  height: 200px;
}
</style>

```



## **组件之间的数据共享**

### **1.** **组件之间的关系**

在项目开发中，组件之间的最常见的关系分为如下两种： 

① 父子关系

② 兄弟关系

![image-20210924132441850](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132441850.png)



### **2.** **父子组件之间的数据共享**

父子组件之间的数据共享又分为：

① 父 -> 子共享数据

② 子 -> 父共享数据

#### 2.1父组件向子组件共享数据

![image-20210925140511367](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140511367.png)

![image-20210924132524061](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132524061.png)

#### 2.2子组件向父组件共享数据

![image-20210925140526343](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140526343.png)

![image-20210924132534910](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132534910.png)

### 3.兄弟组件之间的数据共享

![image-20210925140542808](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925140542808.png)

![image-20210924132546807](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132546807.png)

**EventBus** **的使用步骤**

① 创建 eventBus.js 模块，并向外共享一个 Vue 的实例对象

② 在数据发送方，调用 bus.$emit('事件名称', 要发送的数据) 方法触发自定义事件

③ 在数据接收方，调用 bus.$on('事件名称', 事件处理函数) 方法注册一个自定义事件

## ref 引用

ref 用来辅助开发者在不依赖于 jQuery 的情况下，获取 DOM 元素或组件的引用。每个 vue 的组件实例上，都包含一个 $refs 对象，里面存储着对应的 DOM 元素或组件的引用。默认情况下，组件的 $refs 指向一个空对象

![image-20210924132732259](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132732259.png)

### 2.使用ref 引用DOM 元素

如果想要使用ref 引用页面上的DOM 元素，则可以按照如下的方式进行操作：

![image-20210924132900721](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132900721.png)

### 3.使用ref 引用组件实例

如果想要使用ref 引用页面上的组件实例，则可以按照如下的方式进行操作：

![image-20210924132909942](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132909942.png)

### 4.控制文本框和按钮的按需切换

通过布尔值inputVisible来控制组件中的文本框与按钮的按需切换。示例代码如下：

![image-20210924132938710](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132938710.png)

![image-20210924132946474](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924132946474.png)

### 5.让文本框自动获得焦点

当文本框展示出来之后，如果希望它立即获得焦点，则可以为其添加ref 引用，并调用原生DOM 对象的.focus() 方法即可。示例代码如下：

![image-20210924133023284](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924133023284.png)

### 6.this.$nextTick(cb) 方法

组件的$nextTick(cb) 方法，会把cb 回调推迟到下一个DOM 更新周期之后执行。通俗的理解是：等组件的DOM 更新完成之后，再执行cb 回调函数。从而能保证cb 回调函数可以操作到最新的DOM 元素。

![image-20210924133059752](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924133059752.png)

```vue
<template>
  <div class="app-container">
    <h1 ref="myh12">App 根组件</h1>
    <button @click="showThis">打印 this</button>
    <button @click="onReset">重置 Left 组件的 count 值为 0</button>
    <hr />

    <input type="text" v-if="inputVisible" @blur="showButton" ref="iptRef" />
    <button v-else @click="showInput">展示输入框</button>

    <hr />

    <div class="box">
      <!-- 渲染 Left 组件和 Right 组件 -->
      <Left ref="comLeft"></Left>
    </div>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'

export default {
  data() {
    return {
      // 控制输入框和按钮的按需切换；
      // 默认值为 false，表示默认展示按钮，隐藏输入框
      inputVisible: false
    }
  },
  /* updated() {
    this.$refs.iptRef.focus()
  }, */
  methods: {
    // 点击按钮，展示输入框
    showInput() {
      // 1. 切换布尔值，把文本框展示出来
      this.inputVisible = true
      // 2. 让展示出来的文本框，自动获取焦点
      this.$nextTick(() => {
        this.$refs.iptRef.focus()
      })
    },
    showButton() {
      this.inputVisible = false
    },
    showThis() {
      // this 是当前 App 组件的实例对象
      console.log(this)
      this.$refs.myh12.style.color = 'red'
    },
    // 点击按钮，重置 Left 组件的 count 值
    onReset() {
      this.$refs.comLeft.resetCount()
      // this.$refs.comLeft.count = 0
    }
  },
  components: {
    Left
  }
}
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}
.box {
  display: flex;
}
</style>

```

```vue
<template>
  <div class="left-container">
    <h3>Left 组件 --- {{ count }}</h3>
    <button @click="count += 1">+1</button>
    <button @click="resetCount">重置</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    resetCount() {
      this.count = 0
    }
  }
}
</script>

<style lang="less">
.left-container {
  padding: 0 20px 20px;
  background-color: orange;
  min-height: 250px;
  flex: 1;
}
</style>

```



## 总结  —— 第一阶段



![image-20210924133136016](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210924133136016.png)

## 数组的some方法

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>

<body>

  <script>
    const arr = ['小红', '你大红', '苏大强', '宝']

    // forEach 循环一旦开始，无法在中间被停止
    /* arr.forEach((item, index) => {
      console.log('object')
      if (item === '苏大强') {
        console.log(index)
      }
    }) */

    /* arr.some((item, index) => {
      console.log('ok')
      if (item === '苏大强') {
        console.log(index)
        // 在找到对应的项之后，可以通过 return true 固定的语法，来终止 some 循环
        return true
      }
    }) */
  </script>
</body>

</html>
```

## 数组的every方法

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>

<body>
  <script>
    const arr = [
      { id: 1, name: '西瓜', state: true },
      { id: 2, name: '榴莲', state: false },
      { id: 3, name: '草莓', state: true },
    ]

    // 需求：判断数组中，水果是否被全选了！
    const result = arr.every(item => item.state)
    console.log(result)
  </script>
</body>

</html>
```



## 数组的reduce方法

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>

<body>
  <script>
    const arr = [
      { id: 1, name: '西瓜', state: true, price: 10, count: 1 },
      { id: 2, name: '榴莲', state: false, price: 80, count: 2 },
      { id: 3, name: '草莓', state: true, price: 20, count: 3 },
    ]

    // 需求：把购物车数组中，已勾选的水果，总价累加起来！
    /* let amt = 0 // 总价
        arr.filter(item => item.state).forEach(item => {
          amt += item.price * item.count
        })
    
        console.log(amt) */

    // arr.filter(item => item.state).reduce((累加的结果, 当前循环项) => { }, 初始值)
    const result = arr.filter(item => item.state).reduce((amt, item) => amt += item.price * item.count, 0)

    console.log(result)
  </script>
</body>

</html>
```

## 动态组件

### **1. 什么是动态组件**

动态组件指的是动态切换组件的显示与隐藏。

### **2. 如何实现动态组件渲染**

vue 提供了一个内置的 <component> 组件，专门用来实现动态组件的渲染。示例代码如下：

![image-20210925180038979](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925180038979.png)

### **3. 使用 keep-alive 保持状态**

默认情况下，切换动态组件时无法保持组件的状态。此时可以使用 vue 内置的 <keep-alive> 组件保持动态组件的状态。示例代码如下：

![image-20210925180102443](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925180102443.png)

```vue
<template>
  <div class="app-container">
    <h1>App 根组件</h1>
    <hr />

    <button @click="comName = 'Left'">展示 Left</button>
    <button @click="comName = 'Right'">展示 Right</button>

    <div class="box">
      <!-- 渲染 Left 组件和 Right 组件 -->
      <!-- 1. component 标签是 vue 内置的，作用：组件的占位符 -->
      <!-- 2. is 属性的值，表示要渲染的组件的名字 -->
      <!-- 3. is 属性的值，应该是组件在 components 节点下的注册名称 -->

      <!-- keep-alive 会把内部的组件进行缓存，而不是销毁组件 -->
      <!-- 在使用 keep-alive 的时候，可以通过 include 指定哪些组件需要被缓存； -->
      <!-- 或者，通过 exclude 属性指定哪些组件不需要被缓存；但是：不要同时使用 include 和 exclude 这两个属性 -->
      <keep-alive exclude="MyRight">
        <component :is="comName"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'
import Right from '@/components/Right.vue'

export default {
  data() {
    return {
      // comName 表示要展示的组件的名字
      comName: 'Left'
    }
  },
  components: {
    // 如果在“声明组件”的时候，没有为组件指定 name 名称，则组件的名称默认就是“注册时候的名称”
    Left,
    Right
  }
}
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}
.box {
  display: flex;
}
</style>

```

### **4. keep-alive 对应的生命周期函数**

当组件被缓存时，会自动触发组件的 deactivated 生命周期函数。

当组件被激活时，会自动触发组件的 activated 生命周期函数。

![image-20210925180117528](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925180117528.png)

```vue
<template>
  <div class="left-container">
    <h3>Left 组件 --- {{ count }}</h3>
    <button @click="count += 1">+1</button>
  </div>
</template>

<script>
export default {
  name: 'MyLeft',
  data() {
    return {
      count: 0
    }
  },
  created() {
    console.log('Left 组件被创建了！')
  },
  destroyed() {
    console.log('Left 组件被销毁了~~~')
  },

  // 当组件第一次被创建的时候，既会执行 created 生命周期，也会执行 activated 生命周期
  // 当时，当组件被激活的时候，只会触发 activated 生命周期，不再触发 created。因为组件没有被重新创建
  activated() {
    console.log('组件被激活了，activated')
  },
  deactivated() {
    console.log('组件被缓存了，deactivated')
  }
}
</script>

<style lang="less">
.left-container {
  padding: 0 20px 20px;
  background-color: orange;
  min-height: 250px;
  flex: 1;
}
</style>

```

### **5. keep-alive 的** **include** **属性**和exclude属性

include 属性用来指定：只有名称匹配的组件会被缓存。多个组件名之间使用英文的逗号分隔：

![image-20210925180133556](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210925180133556.png)

```vue
<template>
  <div class="right-container">
    <h3>Right 组件</h3>
  </div>
</template>

<script>
export default {
  // 当提供了 name 属性之后，组件的名称，就是 name 属性的值
  // 对比：
  // 1. 组件的 “注册名称” 的主要应用场景是：以标签的形式，把注册好的组件，渲染和使用到页面结构之中
  // 2. 组件声明时候的 “name” 名称的主要应用场景：结合 <keep-alive> 标签实现组件缓存功能；以及在调试工具中看到组件的 name 名称
  name: 'MyRight'
}
</script>

<style lang="less">
.right-container {
  padding: 0 20px 20px;
  background-color: lightskyblue;
  min-height: 250px;
  flex: 1;
}
</style>

```

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926101044637.png" alt="image-20210926101044637" style="zoom:150%;" />

### 6.了解组件注册名称和组件声明时name的区别

```vue
<script>
export default {
  // 当提供了 name 属性之后，组件的名称，就是 name 属性的值
  // 对比：
  // 1. 组件的 “注册名称” 的主要应用场景是：以标签的形式，把注册好的组件，渲染和使用到页面结构之中
  // 2. 组件声明时候的 “name” 名称的主要应用场景：结合 <keep-alive> 标签实现组件缓存功能；以及在调试工具中看到组件的 name 名称
  name: 'MyRight'
}
</script>
```

```vue
components: {
    // 如果在“声明组件”的时候，没有为组件指定 name 名称，则组件的名称默认就是“注册时候的名称”
    Left,
    Right
  }
```

## 插槽

### **1. 什么是插槽**

插槽（Slot）是 vue 为组件的封装者提供的能力。允许开发者在封装组件时，把不确定的、希望由用户指定的部分定义为插槽。

![image-20210926102220911](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102220911.png)

可以把插槽认为是组件封装期间，为用户预留的内容的占位符

![image-20210926104322407](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926104322407.png)

![image-20210926104236476](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926104236476.png)

### **2. 体验插槽的基础用法**

在封装组件时，可以通过 <slot> 元素定义插槽，从而为用户预留内容占位符。示例代码如下：

![image-20210926102250560](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102250560.png)

![image-20210926102257413](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102257413.png)

#### **2.1 没有预留插槽的内容会被丢弃**

如果在封装组件时没有预留任何 <slot> 插槽，则用户提供的任何自定义内容都会被丢弃。示例代码如下：

![image-20210926102327694](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102327694.png)

![image-20210926102333246](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102333246.png)

#### **2.2 后备内容**

封装组件时，可以为预留的 <slot> 插槽提供后备内容（默认内容）。如果组件的使用者没有为插槽提供任何内容，则后备内容会生效。示例代码如下：

![image-20210926102355242](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102355242.png)

### **3. 具名插槽**

如果在封装组件时需要预留多个插槽节点，则需要为每个 <slot> 插槽指定具体的 name 名称。这种带有具体名称的插槽叫做“具名插槽”。示例代码如下：

![image-20210926102417212](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102417212.png)

#### **3.1 为具名插槽提供内容**

在向具名插槽提供内容的时候，我们可以在一个 <template> 元素上使用 v-slot 指令，并以 v-slot 的参数的形式提供其名称。示例代码如下：

![image-20210926102442224](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102442224.png)

#### **3.2 具名插槽的简写形式**

跟 v-on 和 v-bind 一样，v-slot 也有缩写，即把参数之前的所有内容 (v-slot:) 替换为字符 #。例如 v-slot:header可以被重写为 #header：

![image-20210926102505757](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102505757.png)

### **4. 作用域插槽**

在封装组件的过程中，可以为预留的 <slot> 插槽绑定 props 数据，这种带有 props 数据的 <slot> 叫做“作用域插槽”。示例代码如下：

![image-20210926102525510](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102525510.png)

#### **4.1 使用作用域插槽**

可以使用 v-slot: 的形式，接收作用域插槽对外提供的数据。示例代码如下：

![image-20210926102542796](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102542796.png)

#### **4.2 解构插槽 Prop**

作用域插槽对外提供的数据对象，可以使用解构赋值简化数据的接收过程。示例代码如下：

![image-20210926102607006](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926102607006.png)

```vue
<template>
  <div class="app-container">
    <h1 v-color="color">App 根组件</h1>
    <p v-color="'red'">测试</p>

    <button @click="color = 'green'">改变 color 的颜色值</button>
    <hr />

    <Article>
      <template #title>
        <h3>一首诗</h3>
      </template>

      <template #content="{ msg, user }">
        <div>
          <p>啊，大海，全是水。</p>
          <p>啊，蜈蚣，全是腿。</p>
          <p>啊，辣椒，净辣嘴。</p>
          <p>{{ msg }}</p>
          <p>{{ user.name }}</p>
        </div>
      </template>

      <template #author>
        <div>作者：彬果锅</div>
      </template>
    </Article>

    <hr />

    <div class="box" style="display: none;">
      <!-- 渲染 Left 组件和 Right 组件 -->
      <Left>
        <!-- 默认情况下，在使用组件的时候，提供的内容都会被填充到名字为 default 的插槽之中 -->
        <!-- 1. 如果要把内容填充到指定名称的插槽中，需要使用 v-slot: 这个指令 -->
        <!-- 2. v-slot: 后面要跟上插槽的名字 -->
        <!-- 3. v-slot: 指令不能直接用在元素身上，必须用在 template 标签上 -->
        <!-- 4. template 这个标签，它是一个虚拟的标签，只起到包裹性质的作用，但是，不会被渲染为任何实质性的 html 元素 -->
        <!-- 5. v-slot: 指令的简写形式是 # -->
        <template #default>
          <p>这是在 Left 组件的内容区域，声明的 p 标签</p>
        </template>
      </Left>
    </div>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'
import Article from '@/components/Article.vue'
export default {
  data() {
    return {
      color: 'blue'
    }
  },
  components: {
    Left,
    Article
  },
  // 私有自定义指令的节点
  directives: {
    // 定义名为 color 的指令，指向一个配置对象
    /* color: {
      // 当指令第一次被绑定到元素上的时候，会立即触发 bind 函数
      // 形参中的 el 表示当前指令所绑定到的那个 DOM 对象
      bind(el, binding) {
        console.log('触发了 v-color 的 bind 函数')
        el.style.color = binding.value
      },
      // 在 DOM 更新的时候，会触发 update 函数
      update(el, binding) {
        console.log('触发了 v-color 的 update 函数')
        el.style.color = binding.value
      }
    } */
    color(el, binding) {
      el.style.color = binding.value
    }
  }
}
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}
.box {
  display: flex;
}
</style>

```

```vue
<template>
  <div class="left-container">
    <h3>Left 组件</h3>
    <hr />
    <!-- 声明一个插槽区域 -->
    <!-- vue 官方规定：每一个 slot 插槽，都要有一个 name 名称 -->
    <!-- 如果省略了 slot 的 name 属性，则有一个默认名称叫做 default -->
    <slot name="default">
      <h6>这是 default 插槽的后备内容</h6>
    </slot>
  </div>
</template>

<script>
export default {}
</script>

<style lang="less">
.left-container {
  padding: 0 20px 20px;
  background-color: orange;
  min-height: 250px;
  flex: 1;
}
</style>

```

```vue
<template>
  <div class="article-container">
    <h3 v-color="'red'">Article 组件</h3>
    <!-- 文章的标题 -->
    <div class="header-box">
      <slot name="title"></slot>
    </div>

    <!-- 文章的内容 -->
    <div class="content-box">
      <!-- 在封装组件时，为预留的 <slot> 提供属性对应的值，这种用法，叫做 “作用域插槽” -->
      <slot name="content" msg="hello vue.js" :user="userinfo"></slot>
    </div>

    <!-- 文章的作者 -->
    <div class="footer-box">
      <slot name="author"></slot>
    </div>
  </div>
</template>

<script>
export default {
  // 首字母要大写
  name: 'Article',
  data() {
    return {
      // 用户的信息对象
      userinfo: {
        name: 'zs',
        age: 20
      }
    }
  }
}
</script>

<style lang="less" scoped>
.article-container {
  > div {
    min-height: 150px;
  }
  .header-box {
    background-color: pink;
  }
  .content-box {
    background-color: lightblue;
  }
  .footer-box {
    background-color: lightsalmon;
  }
}
</style>

```

## **自定义指令**

### **1. 什么是自定义指令**

vue 官方提供了 v-text、v-for、v-model、v-if 等常用的指令。除此之外 vue 还允许开发者自定义指令。

### **2. 自定义指令的分类**

vue 中的自定义指令分为两类，分别是：

⚫ 私有自定义指令

⚫ 全局自定义指令

### **3. 私有自定义指令**

在每个 vue 组件中，可以在 directives 节点下声明私有自定义指令。示例代码如下：

![image-20210926112400342](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112400342.png)

### **4. 使用自定义指令**

在使用自定义指令时，需要加上 v- 前缀。示例代码如下：

![image-20210926112420325](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112420325.png)

### **5. 为自定义指令****动态绑定参数值**

在 template 结构中使用自定义指令时，可以通过等号（=）的方式，为当前指令动态绑定参数值：

![image-20210926112445813](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112445813.png)

### **6. 通过** **binding** **获取指令的参数值**

在声明自定义指令时，可以通过形参中的第二个参数，来接收指令的参数值：

![image-20210926112500774](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112500774.png)

### **7. update 函数**

bind 函数只调用 1 次：当指令第一次绑定到元素时调用，当 DOM 更新时 bind 函数不会被触发。 update 函数会在每次 DOM 更新时被调用。示例代码如下：

![image-20210926112521148](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112521148.png)

### **8. 函数简写**

如果 insert 和update 函数中的逻辑完全相同，则对象格式的自定义指令可以简写成函数格式：

![image-20210926112557338](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112557338.png)

![image-20210926123612454](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926123612454.png)

私有自定义指令在其他组件中使用会报错
![image-20210926123831164](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926123831164.png)

私有自定义指令

```js
export default {
  data() {
    return {
      color: 'blue'
    }
  },
  components: {
    Left,
    Article
  },
  // 私有自定义指令的节点
  directives: {
    // 定义名为 color 的指令，指向一个配置对象
    /* color: {
      // 当指令第一次被绑定到元素上的时候，会立即触发 bind 函数
      // 形参中的 el 表示当前指令所绑定到的那个 DOM 对象
      bind(el, binding) {
        console.log('触发了 v-color 的 bind 函数')
        el.style.color = binding.value
      },
      // 在 DOM 更新的时候，会触发 update 函数
      update(el, binding) {
        console.log('触发了 v-color 的 update 函数')
        el.style.color = binding.value
      }
    } */
    color(el, binding) {
      el.style.color = binding.value
    }
  }
}
```

### **9. 全局自定义指令**

全局共享的自定义指令需要通过“Vue.directive()”进行声明，示例代码如下：

![image-20210926112615195](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112615195.png)

```js
import Vue from 'vue'
import App from './App.vue'

Vue.config.productionTip = false

// 全局自定义指令
/* Vue.directive('color', {
  bind(el, binding) {
    el.style.color = binding.value
  },
  update(el, binding) {
    el.style.color = binding.value
  }
}) */
Vue.directive('color', function(el, binding) {
  el.style.color = binding.value
})

// Vue.filter('过滤器的名字', function () {  })

new Vue({
  render: h => h(App)
}).$mount('#app')
```



## 总结 —— 第一阶段

![image-20210926112629842](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926112629842.png)

## ESLint常见语法规则

![image-20210926135408645](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926135408645.png)

## 自定义ESLint的rules 规则

![image-20210926135751984](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926135751984.png)

## 把axios挂载到Vue的原型上并配置请求根路径

![image-20210926144850289](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926144850289.png)

```js
import Vue from 'vue'
import App from './App.vue'
//导入axios
import axios from 'axios'

Vue.config.productionTip = false

// 全局配置 axios 的请求根路径
axios.defaults.baseURL = 'http://www.liulongbin.top:3006'
// 把 axios 挂载到 Vue.prototype 上，供每个 .vue 组件的实例直接使用
Vue.prototype.$http = axios
// 今后，在每个 .vue 组件中要发起请求，直接调用 this.$http.xxx
// 但是，把 axios 挂载到 Vue 原型上，有一个缺点：不利于 API 接口的复用！！！

new Vue({
  render: (h) => h(App),
}).$mount('#app')

```

![image-20210926145334672](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926145334672.png)

```vue
<template>
  <div>
    <h1>App 根组件</h1>
    <button @click="btnGetBooks">获取图书列表的数据</button>

    <hr />

    <div class="box">
      <Left></Left>
      <Right></Right>
    </div>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'
import Right from '@/components/Right.vue'

export default {
  methods: {
    // 点击按钮，获取图书列表的数据
    async btnGetBooks() {
      const { data: res } = await this.$http.get('/api/getbooks')
      console.log(res)
    },
  },
  components: {
    Left,
    Right,
  },
}
</script>

<style lang="less" scoped>
.box {
  display: flex;
}
</style>

```

![image-20210926145409552](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926145409552.png)

```vue
<template>
  <div class="left-container">
    <h3>Left 组件</h3>
    <button @click="getInfo">发起 GET 请求</button>
    <button @click="btnGetBooks">获取图书列表的数据</button>
  </div>
</template>

<script>
// import axios from 'axios'

export default {
  methods: {
    async getInfo() {
      const { data: res } = await this.$http.get('/api/get')
      console.log(res)
    },
    // 点击按钮，获取图书列表的数据
    async btnGetBooks() {
      const { data: res } = await this.$http.get('/api/getbooks')
      console.log(res)
    },
  },
}
</script>

<style lang="less" scoped>
.left-container {
  background-color: orange;
  min-height: 200px;
  flex: 1;
}
</style>

```

![image-20210926145429942](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210926145429942.png)

```vue
<template>
  <div class="right-container">
    <h3>Right 组件</h3>
    <button @click="postInfo">发起 POST 请求</button>
    <button @click="btnGetBooks">获取图书列表的数据</button>
  </div>
</template>

<script>
// import axios from 'axios'

export default {
  methods: {
    async postInfo() {
      const { data: res } = await this.$http.post('/api/post', { name: 'zs', age: 20 })
      console.log(res)
    },
    // 点击按钮，获取图书列表的数据
    async btnGetBooks() {
      const { data: res } = await this.$http.get('/api/getbooks')
      console.log(res)
    },
  },
}
</script>

<style lang="less" scoped>
.right-container {
  background-color: skyblue;
  min-height: 200px;
  flex: 1;
}
</style>

```

## **前端路由的概念与原理**

### **1. 什么是路由**

路由（英文：router）就是对应关系。

### **3. SPA 与前端路由**

SPA 指的是一个 web 网站只有唯一的一个 HTML 页面，所有组件的展示与切换都在这唯一的一个页面内完成。此时，不同组件之间的切换需要通过前端路由来实现。

结论：在 SPA 项目中，不同功能之间的切换，要依赖于前端路由来完成！

### **4. 什么是前端路由**

通俗易懂的概念：Hash 地址与组件之间的对应关系。

### **5. 前端路由的工作方式**

① 用户点击了页面上的路由链接

② 导致了 URL 地址栏中的 Hash 值发生了变化

③ 前端路由监听了到 Hash 地址的变化

④ 前端路由把当前 Hash 地址对应的组件渲染都浏览器中

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085222962.png" alt="image-20210927085222962" style="zoom: 200%;" />

结论：前端路由，指的是 Hash 地址与组件之间的对应关系！

### **6. 实现简易的前端路由**

步骤1：通过 <component> 标签，结合 comName 动态渲染组件。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085302622.png" alt="image-20210927085302622" style="zoom:200%;" />

步骤2：在 App.vue 组件中，为 <a> 链接添加对应的 hash 值：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085316675.png" alt="image-20210927085316675" style="zoom:200%;" />

步骤3：在 created 生命周期函数中，监听浏览器地址栏中 hash 地址的变化，动态切换要展示的组件的名称：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085335030.png" alt="image-20210927085335030" style="zoom: 200%;" />

```vue
<template>
  <div class="app-container">
    <h1>App 根组件</h1>

    <a href="#/home">首页</a>
    <a href="#/movie">电影</a>
    <a href="#/about">关于</a>
    <hr />

    <component :is="comName"></component>
  </div>
</template>

<script>
// 导入组件
import Home from '@/components/Home.vue'
import Movie from '@/components/Movie.vue'
import About from '@/components/About.vue'

export default {
  name: 'App',
  data() {
    return {
      // 在动态组件的位置，要展示的组件的名字，值必须是字符串
      comName: 'Home'
    }
  },
  created() {
    // 只要当前的 App 组件一被创建，就立即监听 window 对象的 onhashchange 事件
    window.onhashchange = () => {
      console.log('监听到了 hash 地址的变化', location.hash)
      switch (location.hash) {
        case '#/home':
          this.comName = 'Home'
          break
        case '#/movie':
          this.comName = 'Movie'
          break
        case '#/about':
          this.comName = 'About'
          break
      }
    }
  },
  // 注册组件
  components: {
    Home,
    Movie,
    About
  }
}
</script>

<style lang="less" scoped>
.app-container {
  background-color: #efefef;
  overflow: hidden;
  margin: 10px;
  padding: 15px;
  > a {
    margin-right: 10px;
  }
}
</style>

```



## **vue-router 的基本用法**

### **1. 什么是 vue-router**

vue-router 是 vue.js 官方给出的路由解决方案。它只能结合 vue 项目进行使用，能够轻松的管理 SPA 项目中组件的切换。

vue-router 的官方文档地址：https://router.vuejs.org/zh/

### **2. vue-router 安装和配置的步骤**

① 安装 vue-router 包 

② 创建路由模块

③ 导入并挂载路由模块

④ 声明路由链接和占位符

#### **2.1 在项目中安装 vue-router**

在 vue2 的项目中，安装 vue-router 的命令如下：

```npm
npm i vue-router#3.5.2 -S
```

#### **2.2 创建路由模块**

在 src 源代码目录下，新建 router/index.js 路由模块，并初始化如下的代码：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085708711.png" alt="image-20210927085708711" style="zoom:150%;" />

#### **2.3 导入并挂载路由模块**

在 src/main.js 入口文件中，导入并挂载路由模块。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085731349.png" alt="image-20210927085731349" style="zoom: 150%;" />

#### 2.4 声明路由链接和占位符

在 src/App.vue 组件中，使用 vue-router 提供的 <router-link> 和 <router-view> 声明路由链接和占位符：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085811294.png" alt="image-20210927085811294" style="zoom:150%;" />

```vue
<template>
  <div class="app-container">
    <h1>App2 组件</h1>

    <!-- 当安装和配置了 vue-router 后，就可以使用 router-link 来替代普通的 a 链接了 -->
    <!-- <a href="#/home">首页</a> -->
    <router-link to="/home">首页</router-link>
    <!-- 注意1：在 hash 地址中， / 后面的参数项，叫做“路径参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.params 来访问路径参数 -->

    <!-- 注意2：在 hash 地址中，? 后面的参数项，叫做“查询参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.query 来访问查询参数 -->

    <!-- 注意3：在 this.$route 中，path 只是路径部分；fullPath 是完整的地址 -->
    <!-- 例如： -->
    <!-- /movie/2?name=zs&age=20 是 fullPath 的值 -->
    <!-- /movie/2 是 path 的值 -->
    <router-link to="/movie/1">洛基</router-link>
    <router-link to="/movie/2?name=zs&age=20">雷神</router-link>
    <router-link to="/movie/3">复联</router-link>
    <router-link to="/about">关于</router-link>

    <hr />

    <!-- 只要在项目中安装和配置了 vue-router，就可以使用 router-view 这个组件了 -->
    <!-- 它的作用很单纯：占位符 -->
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="less" scoped>
.app-container {
  background-color: #efefef;
  overflow: hidden;
  margin: 10px;
  padding: 15px;
  > a {
    margin-right: 10px;
  }
}
</style>
```



### 3. 声明路由的匹配规则

在 src/router/index.js 路由模块中，通过 routes 数组声明路由的匹配规则。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085845115.png" alt="image-20210927085845115" style="zoom:150%;" />

```js
// src/router/index.js 就是当前项目的路由模块
import Vue from 'vue'
import VueRouter from 'vue-router'

// 导入需要的组件
import Home from '@/components/Home.vue'
import Movie from '@/components/Movie.vue'
import About from '@/components/About.vue'
// 把 VueRouter 安装为 Vue 项目的插件
// Vue.use() 函数的作用，就是来安装插件的
Vue.use(VueRouter)

// 创建路由的实例对象
const router = new VueRouter({
  // routes 是一个数组，作用：定义 “hash 地址” 与 “组件” 之间的对应关系
  routes: [
    // 路由规则
    { path: '/home', component: Home },
    // 需求：在 Movie 组件中，希望根据 id 的值，展示对应电影的详情信息
    // 可以为路由规则开启 props 传参，从而方便的拿到动态参数的值
    { path: '/movie/:mid', component: Movie},
    { path: '/about',  component: About},
  ]
})
```

## **vue-router 的常见用法**

### **1. 路由重定向**

路由重定向指的是：用户在访问地址 A 的时候，强制用户跳转到地址 C ，从而展示特定的组件页面。通过路由规则的 redirect 属性，指定一个新的路由地址，可以很方便地设置路由的重定向：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927085924382.png" alt="image-20210927085924382" style="zoom:150%;" />

### **2. 嵌套路由**

通过路由实现组件的嵌套展示，叫做嵌套路由。

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090005152.png" alt="image-20210927090005152" style="zoom:150%;" />

### 3.1 声明子路由链接和子路由占位符

在 About.vue 组件中，声明 tab1 和 tab2 的子路由链接以及子路由占位符。示例代码如下

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090054237.png" alt="image-20210927090054237" style="zoom:150%;" />

### **3.2 通过** **children** 属性声明子路由规则

在 src/router/index.js 路由模块中，导入需要的组件，并使用 children 属性声明子路由规则：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090117679.png" alt="image-20210927090117679" style="zoom:150%;" />

### **4. 动态路由匹配**

思考：有如下 3 个路由链接：

![image-20210927090153718](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090153718.png)

定义如下 3 个路由规则，是否可行???

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090222284.png" alt="image-20210927090222284" style="zoom:150%;" />

缺点：路由规则的复用性差。

#### **4.1 动态路由的概念**

动态路由指的是：把 Hash 地址中可变的部分定义为参数项，从而提高路由规则的复用性。 在 vue-router 中使用英文的冒号（:）来定义路由的参数项。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090356759.png" alt="image-20210927090356759" style="zoom:150%;" />

#### **4.2** **$route.params** **参数对象**

在动态路由渲染出来的组件中，可以使用 this.$route.params 对象访问到动态匹配的参数值。

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090422755.png" alt="image-20210927090422755" style="zoom:150%;" />

#### **4.3 使用 props 接收路由参数**

为了简化路由参数的获取形式，vue-router 允许在路由规则中开启 props 传参。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927090447599.png" alt="image-20210927090447599" style="zoom:150%;" />

#### 拓展query和fullpath

```
	 <!-- 注意1：在 hash 地址中， / 后面的参数项，叫做“路径参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.params 来访问路径参数 -->

    <!-- 注意2：在 hash 地址中，? 后面的参数项，叫做“查询参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.query 来访问查询参数 -->

    <!-- 注意3：在 this.$route 中，path 只是路径部分；fullPath 是完整的地址 -->
    <!-- 例如： -->
    <!-- /movie/2?name=zs&age=20 是 fullPath 的值 -->
    <!-- /movie/2 是 path 的值 -->
```

![image-20210927131508684](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927131508684.png)

![image-20210927131610714](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927131610714.png)

```vue
<template>
  <div class="app-container">
    <h1>App2 组件</h1>

    <!-- 当安装和配置了 vue-router 后，就可以使用 router-link 来替代普通的 a 链接了 -->
    <!-- <a href="#/home">首页</a> -->
    <router-link to="/home">首页</router-link>
    <!-- 注意1：在 hash 地址中， / 后面的参数项，叫做“路径参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.params 来访问路径参数 -->

    <!-- 注意2：在 hash 地址中，? 后面的参数项，叫做“查询参数” -->
    <!-- 在路由“参数对象”中，需要使用 this.$route.query 来访问查询参数 -->

    <!-- 注意3：在 this.$route 中，path 只是路径部分；fullPath 是完整的地址 -->
    <!-- 例如： -->
    <!-- /movie/2?name=zs&age=20 是 fullPath 的值 -->
    <!-- /movie/2 是 path 的值 -->
    <router-link to="/movie/1">洛基</router-link>
    <router-link to="/movie/2?name=zs&age=20">雷神</router-link>
    <router-link to="/movie/3">复联</router-link>
    <router-link to="/about">关于</router-link>

    <hr />

    <!-- 只要在项目中安装和配置了 vue-router，就可以使用 router-view 这个组件了 -->
    <!-- 它的作用很单纯：占位符 -->
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="less" scoped>
.app-container {
  background-color: #efefef;
  overflow: hidden;
  margin: 10px;
  padding: 15px;
  > a {
    margin-right: 10px;
  }
}
</style>

```

```js
// src/router/index.js 就是当前项目的路由模块
import Vue from 'vue'
import VueRouter from 'vue-router'

// 导入需要的组件
import Home from '@/components/Home.vue'
import Movie from '@/components/Movie.vue'
import About from '@/components/About.vue'

import Tab1 from '@/components/tabs/Tab1.vue'
import Tab2 from '@/components/tabs/Tab2.vue'

import Login from '@/components/Login.vue'
import Main from '@/components/Main.vue'

// 把 VueRouter 安装为 Vue 项目的插件
// Vue.use() 函数的作用，就是来安装插件的
Vue.use(VueRouter)

// 创建路由的实例对象
const router = new VueRouter({
  // routes 是一个数组，作用：定义 “hash 地址” 与 “组件” 之间的对应关系
  routes: [
    // 重定向的路由规则
    { path: '/', redirect: '/home' },
    // 路由规则
    { path: '/home', component: Home },
    // 需求：在 Movie 组件中，希望根据 id 的值，展示对应电影的详情信息
    // 可以为路由规则开启 props 传参，从而方便的拿到动态参数的值
    { path: '/movie/:mid', component: Movie, props: true },
    {
      path: '/about',
      component: About,
      // redirect: '/about/tab1',
      children: [
        // 子路由规则
        // 默认子路由：如果 children 数组中，某个路由规则的 path 值为空字符串，则这条路由规则，叫做“默认子路由”
        { path: '', component: Tab1 },
        { path: 'tab2', component: Tab2 },
      ],
    },
    { path: '/login', component: Login },
    { path: '/main', component: Main },
  ],
})

// 为 router 实例对象，声明全局前置导航守卫
// 只要发生了路由的跳转，必然会触发 beforeEach 指定的 function 回调函数
router.beforeEach(function (to, from, next) {
  // to 表示将要访问的路由的信息对象
  // from 表示将要离开的路由的信息对象
  // next() 函数表示放行的意思
  // 分析：
  // 1. 要拿到用户将要访问的 hash 地址
  // 2. 判断 hash 地址是否等于 /main。
  // 2.1 如果等于 /main，证明需要登录之后，才能访问成功
  // 2.2 如果不等于 /main，则不需要登录，直接放行  next()
  // 3. 如果访问的地址是 /main。则需要读取 localStorage 中的 token 值
  // 3.1 如果有 token，则放行
  // 3.2 如果没有 token，则强制跳转到 /login 登录页
  if (to.path === '/main') {
    // 要访问后台主页，需要判断是否有 token
    const token = localStorage.getItem('token')
    if (token) {
      next()
    } else {
      // 没有登录，强制跳转到登录页
      next('/login')
    }
  } else {
    next()
  }
})
export default router
```





### **5. 声明式导航 & 编程式导航**

在浏览器中，点击链接实现导航的方式，叫做声明式导航。例如：

⚫ 普通网页中点击 <a> 链接、vue 项目中点击 <router-link> 都属于声明式导航

在浏览器中，调用 API 方法实现导航的方式，叫做编程式导航。例如：

⚫ 普通网页中调用 location.href 跳转到新页面的方式，属于编程式导航

#### 5.1 vue-router 中的编程式导航 API

![image-20210927132140813](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927132140813.png)

vue-router 提供了许多编程式导航的 API，其中最常用的导航 API 分别是：

① this.$router.push('hash 地址')

⚫ 跳转到指定 hash 地址，并增加一条历史记录

② this.$router.replace('hash 地址') 

⚫ 跳转到指定的 hash 地址，并替换掉当前的历史记录

③ this.$router.go(数值 n)

⚫ 实现导航历史前进、后退

#### 5.2 $router.push

调用 this.$router.push() 方法，可以跳转到指定的 hash 地址，从而展示对应的组件页面。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927091030270.png" alt="image-20210927091030270" style="zoom:150%;" />

#### 5.3 $router.replace

调用 this.$router.replace() 方法，可以跳转到指定的 hash 地址，从而展示对应的组件页面。

push 和 replace 的区别：

⚫ push 会增加一条历史记录

⚫ replace 不会增加历史记录，而是替换掉当前的历史记录

```vue
<template>
  <div class="home-container">
    <h3>Home 组件</h3>

    <hr />

    <button @click="gotoLk">通过 push 跳转到“洛基”页面</button>
    <button @click="gotoLk2">通过 replace 跳转到“洛基”页面</button>
    <router-link to="/main">访问后台主页</router-link>
  </div>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    gotoLk() {
      // 通过编程式导航 API，导航跳转到指定的页面
      this.$router.push('/movie/1')
    },
    gotoLk2() {
      this.$router.replace('/movie/1')
    }
  }
}
</script>

<style lang="less" scoped>
.home-container {
  min-height: 200px;
  background-color: pink;
  padding: 15px;
}
</style>
```

#### 5.4 $router.go

调用 this.$router.go() 方法，可以在浏览历史中前进和后退。示例代码如下：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927091948209.png" alt="image-20210927091948209" style="zoom:150%;" />

#### 5.5 $router.go 的简化用法

在实际开发中，一般只会前进和后退一层页面。因此 vue-router 提供了如下两个便捷方法：

① $router.back()

⚫ 在历史记录中，后退到上一个页面

② $router.forward()

⚫ 在历史记录中，前进到下一个页面

```vue
<template>
  <div class="movie-container">
    <!-- this.$route 是路由的“参数对象” -->
    <!-- this.$router 是路由的“导航对象” -->
    <h3>Movie 组件 --- {{ $route.params.mid }} --- {{ mid }}</h3>
    <button @click="showThis">打印 this</button>
    <button @click="goback">后退</button>
    <!-- 在行内使用编程式导航跳转的时候，this 必须要省略，否则会报错！ -->
    <button @click="$router.back()">back 后退</button>
    <button @click="$router.forward()">forward 前进</button>
  </div>
</template>

<script>
export default {
  name: 'Movie',
  // 接收 props 数据
  props: ['mid'],
  methods: {
    showThis() {
      console.log(this)
    },
    goback() {
      // go(-1) 表示后退一层
      // 如果后退的层数超过上限，则原地不动
      this.$router.go(-1)
    }
  }
}
</script>

<style lang="less" scoped>
.movie-container {
  min-height: 200px;
  background-color: lightsalmon;
  padding: 15px;
}
</style>
```

### **6. 导航守卫**

导航守卫可以控制路由的访问权限。示意图如下：

![image-20210927092033429](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092033429.png)

#### **6.1 全局前置守卫**

每次发生路由的导航跳转时，都会触发全局前置守卫。因此，在全局前置守卫中，程序员可以对每个路由进行访问权限的控制：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092056143.png" alt="image-20210927092056143" style="zoom:150%;" />

#### **6.2 守卫方法的 3 个形参**

全局前置守卫的回调函数中接收 3 个形参，格式为：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092114892.png" alt="image-20210927092114892" style="zoom:150%;" />

#### **6.3 next 函数的 3 种调用方式**

参考示意图，分析 next 函数的 3 种调用方式最终导致的结果：

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092133069.png" alt="image-20210927092133069" style="zoom:150%;" />

当前用户拥有后台主页的访问权限，直接放行：next()

当前用户没有后台主页的访问权限，强制其跳转到登录页面：next('/login')

当前用户没有后台主页的访问权限，不允许跳转到后台主页：next(false)

#### **6.4 控制后台主页的访问权限**

<img src="C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092158958.png" alt="image-20210927092158958" style="zoom:150%;" />

```js
// src/router/index.js 就是当前项目的路由模块
import Vue from 'vue'
import VueRouter from 'vue-router'

// 导入需要的组件
import Home from '@/components/Home.vue'
import Movie from '@/components/Movie.vue'
import About from '@/components/About.vue'

import Tab1 from '@/components/tabs/Tab1.vue'
import Tab2 from '@/components/tabs/Tab2.vue'

import Login from '@/components/Login.vue'
import Main from '@/components/Main.vue'

// 把 VueRouter 安装为 Vue 项目的插件
// Vue.use() 函数的作用，就是来安装插件的
Vue.use(VueRouter)

// 创建路由的实例对象
const router = new VueRouter({
  // routes 是一个数组，作用：定义 “hash 地址” 与 “组件” 之间的对应关系
  routes: [
    // 重定向的路由规则
    { path: '/', redirect: '/home' },
    // 路由规则
    { path: '/home', component: Home },
    // 需求：在 Movie 组件中，希望根据 id 的值，展示对应电影的详情信息
    // 可以为路由规则开启 props 传参，从而方便的拿到动态参数的值
    { path: '/movie/:mid', component: Movie, props: true },
    {
      path: '/about',
      component: About,
      // redirect: '/about/tab1',
      children: [
        // 子路由规则
        // 默认子路由：如果 children 数组中，某个路由规则的 path 值为空字符串，则这条路由规则，叫做“默认子路由”
        { path: '', component: Tab1 },
        { path: 'tab2', component: Tab2 },
      ],
    },
    { path: '/login', component: Login },
    { path: '/main', component: Main },
  ],
})

// 为 router 实例对象，声明全局前置导航守卫
// 只要发生了路由的跳转，必然会触发 beforeEach 指定的 function 回调函数
router.beforeEach(function (to, from, next) {
  // to 表示将要访问的路由的信息对象
  // from 表示将要离开的路由的信息对象
  // next() 函数表示放行的意思
  // 分析：
  // 1. 要拿到用户将要访问的 hash 地址
  // 2. 判断 hash 地址是否等于 /main。
  // 2.1 如果等于 /main，证明需要登录之后，才能访问成功
  // 2.2 如果不等于 /main，则不需要登录，直接放行  next()
  // 3. 如果访问的地址是 /main。则需要读取 localStorage 中的 token 值
  // 3.1 如果有 token，则放行
  // 3.2 如果没有 token，则强制跳转到 /login 登录页
  if (to.path === '/main') {
    // 要访问后台主页，需要判断是否有 token
    const token = localStorage.getItem('token')
    if (token) {
      next()
    } else {
      // 没有登录，强制跳转到登录页
      next('/login')
    }
  } else {
    next()
  }
})

export default router

```



## **总结**  —— 第三阶段

![image-20210927092215536](C:\Users\30676\AppData\Roaming\Typora\typora-user-images\image-20210927092215536.png)
