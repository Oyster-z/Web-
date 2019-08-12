<!--
 * @Description: In User Settings Edit
 * @Author: your name
 * @Date: 2019-07-30 23:11:36
 * @LastEditTime: 2019-08-12 23:34:22
 * @LastEditors: Please set LastEditors
 -->
#### 1. React简介  
两个概念：  
+ **Library(库) :** 小而巧的库，只提供特定的API，优点就是船小好调头，可以很方便的从一个库切换到另外的库，但是代码几乎不会改变  
+ **Framework(框架)：** 大而全的是框架，框架提供了一整套的解决方案，所以，如果在项目中间，想切换到另外的框架，是比较困难的。
#### 2. 前端三大主流框架
三大框架一大抄
+ Angular.js：出来较早的前端框架，学习曲线比较陡，NG1学习起来比较麻烦，NG2-NG5开始，进行了一系列的改革，也提供了组件化开发的概念，从NG2 开始，也支持使用TS(TypeScript) 进行编程。

+ Vue.js: **最火**(关注的人比较多)的一门前端框架，是中国人开发的，文档较为友好；

+ React.js:**最流行**(用的人比较多)的一门框架，因为设计较为优秀;  

#### 3. React 和 vue 的对比

##### 组件化方面
+ **什么是模块化**:是从代码的角度来进行分析的，把一些可复用的代码，抽离为单个的模块，便于项目的维护和开发。
+ **什么是组件化**:是从UI界面的角度来进行分析的；把一些可复用的UI元素，抽离为单独的组件；便于项目的维护和开发；
+ **组件化的好处**： 随着项目规模的增大，手里的组件越来越多；开发将变得越来越方便，因为可以使用现有的组件来进行拼接来得到需要的页面  
+ **vue是如何实践组件化的**: 通过.vue 文件，来创建对应的组件，这三者合起来属于一个组件；
    - template 结构
    - script 行为
    - style 样式
+ **React 如何实现组件化**: React 中有组件化的概念，但是并没有像vue这样的组件模板文件；React中一切都是JS 来表现的，因此要学习React ，js要合格，ES6 和 ES7(async 和 await) 要会用 
##### 开发团队方面
+ React：主要是facebook 团队来维护的，所以技术实力比较雄厚
+ vue：第一版，主要是由作者 尤雨溪 专门维护的，当vue更新到2.X 版本之后，也有一个以作者为主的开源团队来进行维护
##### 社区方面
+ 在社区方面：React 由于诞生的焦躁，所以社区比较强大，一些常见的问题、坑、最优解决方案，在社区中都可以找到；
+ vue 是近两年才火的，所以目前社区相对较小
##### 移动APP开发体验方面
+ vue 结合Weex这门技术，提供了迁移到移动端APP开发的体验（目前只是一个小的玩具，所以没有成功的案例）
+ React 结合ReactNative 也提供了无缝迁移到移动APP的开发体验（RN用的最多，也是最火最流行的）
#### 4. 为什么要学习React
1. 和Angular1相比，React设计很优秀，一切基于JS 并且实现了组件化开发的思想
2. 开发团队实力强悍，不必担心断更的情况
3. 社区强大，很多问题都很找到对应的解决方案；
4. 提供了无缝赚到ReactNative 上的开发体验，让我们技术能力得到拓展，增强了我们的核心竞争力；
5. 很多企业中，前端项目的技术选型都是使用React.js；
#### 5. React 中几个核心的概念
##### 虚拟DOM（virtual Document Object Model）
+ **DOM的本质** 浏览器中的概念，用JS 对象来表示页面上的元素，并提供了操作DOM 对象的API
+ **什么是React 中的虚拟DOM**: 是框架中的概念，是用 JS 对象来模拟页面上的 DOM 和 DOM 嵌套；
+ **为什么要实现虚拟DOM（虚拟DOM的目的）**: 为了实现页面中，DOM 元素的高效更新；
+ DOM 和 虚拟DOM 的区别
    - DOM：浏览器中提供的概念，用 JS 对象，表示页面上的元素，表示页面上的元素，并提供了操作元素的API
    **DOM 树的概念：**
    一个网页呈现的过程1. 浏览器请求服务器获取页面HTML代码 2. 浏览器要在内存中，解析DOM结构，并在浏览器内存中，渲染出一颗DOM树；3. 浏览器把DOM树，呈现到页面上；
    - 虚拟DOM：是框架中的概念，是开发框架的程序员，手动用 JS 对象来模拟 DOM 元素和嵌套关系；
    表格案例  
    需求：点击列头，实现对应表格数据的排序；
    1. 表格中的数据哪里来的：从数据库查询来的
    2. 这些查询到的数据，存在哪里的：存储在浏览器的内存中，以对象数组的形式来表示
    3. 这些数据，是怎么渲染到页面上的？  
     方案1： 手动for循环整个数组，然后手动拼接字符串 str += “<tr></tr>”  
     方案2：使用模板殷勤，art-template  
    4. **思考：上述的方案，有没有性能上的问题？**
    5. 如果用户点击了[时间]，想按照时间从大到小排序：
        + 触发点击事件，在事件中，把内存中的对象数组，重新排序；
        + 当排序之后，页面是旧的，但是内存中的对象数组是新的；
        + 想办法，把最新的数组重新渲染到页面上（有没有性能上的问题）
    6. 分析与总结： 上述方案，只是实现了把数组渲染到页面上的能力，但是并没有把性能做到最优，
    7. 如何才能把性能做到最优：按需渲染页面，（只重新渲染更新的数据所对应的页面元素）；
    8. 如何实现页面的按需更新呢？获取内存中的新旧两颗DOM 树，进行对比，得到需要被按需更新的 DOM 树；
    9. 如何获取到新旧 DOM 树，从而实现 DOM 树的对比呢? 分析：浏览器中，并没有直接提供获取 DOM树的API，因为，我们无法拿到浏览器内存的中 DOM 树；
    10. 程序员可以手动模拟新旧两颗 DOM 树：
    11. 程序员怎么手动模拟 DOM 树？如何模拟一个 DOM 树，举例说明：
    ```css
    <div id="mydiv" title="说实话" data-index="0">
        Oyster好帅
        <p>哈哈哈</p>
    </div>
    ```
    ```javascript
    var div = {
        tagName = "div",
        attrs:{
            id: "mydiv",
            title: "说实话"，
            "data-index":"0"
        },
        children:[
            "Oyster好帅",
            {
                tagName:"p",
                attrs:{},
                children:[
                    "哈哈哈"
                ]
            }
        ]
    }
    ```
    12. 程序员手动模拟的这两颗新旧 DOM 树，就是 React 中的虚拟 DOM 的概念；  
    **总结**：什么是虚拟DOM：用 JS 对象的形式，来模拟页面上 DOM 嵌套关系; (虚拟 DOM 是以 JS 对象的形式存在的)
    这就是React 中虚拟 DOM  的概念  
    本质: 就是用 JS 对象来模拟 DOM 元素和嵌套关系  
    目的：就是为了实现页面元素的高效更新；
    
##### Diff 算法
+ tree diff：新旧两颗 DOM 树，逐层对比的过程，就是 Tree Diff；当整颗DOM 逐层对比完毕，则所有需要被按需更新的元素，必然能够找到
+ component diff： 在进行Tree diff的时候，每一层中，组件级别的对比，叫做component Diff
    - 如果对比前后，组件的类型相同，则暂时认为此组件不需要被更新
    - 如果对比前后，组件类型不同，则需要移除旧组件，创建新则兼，并追加到页面上；
+ element diff：在进行组件对比的时候，如果两个组件类型相同，则需要进行元素级别的对比，这叫做Element Diff

#### 6. 创建基本的 webpack4.x 项目
1. 运行 'npm init -y' 快速初始化项目
2. 创建目录 'src' 存储源代码，'dist'产品目录，表示项目的发布目录
3. 在 'src' 目录下创建index.html
4. 会用npm 安装 webpack， 运行 npm install webpack -D '-D 表示安装到开发环境，-S表示安装到生产环境'
    - 全局运行 npm i cnpm -g
5. 安装 npm -i webpack-cli -D `可以使用 npm install webpack webpack-cli -D 来安装，使用cnpm 可以提高安装工速度，是采用淘宝的源进行安装`, 3.6 版本中 webpack 包含 webpack-cli 但是 4.x 之后就要分开安装。
6. 增加webpack.config.js 文件
```javascript
    // 向外暴露一个大包的配置对象，因为 webpack 是基于Node 构建的，所以 webpack 支持所有的 Node API 和语法
    module.export = {
        mode: 'development',   // development or production 
        // development 表示开发模式，不会对相关文件进行压缩，但是 production 表示生产模式，会对文件内容进行压缩，这样文件的大小就会变小。
        // 在 webpack 4.x 中，有一个很大的特性，就是约定大于配置值 ，约定，默认的大包入口路径是 src->index.js,所以将
        // src目录下的main.js 改为 index.js
    }
    // ES6 中向外导出的api 导入的 使用 import ** from '标识符'
    // export default{}
```
7. 注意： webpack 4.x 提供了约定大于配置的概念，目的是为了尽量减少 配置文件的体积：
    - 默认约定了：
    - 打包的入口是 `src->index.hs`
    - 打包的输出文件是 `dist->main.js`
    - 4.x 中新增了 `mode`选项(必选项)，可选的值为 production 和 development
8. 为了实现实时打包功能，需要安装 webpack-dev-server
    - 安装 cnpm install webpack-dev-server
    - 修改 package.json 文件，增加 dev: "webpack-dev-server", 使用npm run 就会自动调用 package.json 里面的dev 里面的脚本

##### 补充 webpack 相关知识
1. 浏览器只能识别 js png jpg css 文件，但是我们在完成代码的时候 可能会用到其它相关的文件，这时候就需要一个工具来对这些文件进行转换，webpack 属于这种工具的一种，目前还有 rollup(用在javascript), parcel, FIS 等相关工具。
2. 安装和启动
    `使用 npm install webpack webpack-cli` 来安装，安装之后，不能在 terminal下直接使用 webpack 的命令方式来执行webpack 的命令
3. 执行webpack 命令
    利用 npm 命令来进行执行，在 package.json 文件中的 scripts 标签下，增加响应的 npm 脚本命令，scripts 中表示的是脚本命令，使用 npm run + 脚本命令执行
    ```json
        ...
        "scripts": {
            "build": "webpack --mode development",        
            "test": "echo \"Error: no test specified\" && exit 1"
        }
        ...
    ```
    上面的例子,可以执行的命令有 `npm run build` 和 `npm run test`,这样可以新建一条命令，命令的内容调用 webpack 的命令，在使用 webpack 命令的时候，需要新建 webpack.config.js 文件，webpack命令默认会在根路径下，找对应的 js 文件，该文件表示在使用 webpack 打包命令的时候，调用哪些功能或者插件，webpack 只是一个 tool ，针对不同的文件，需要不同的插件或者modules 进行处理。如果需要指定配置文件，那么就需要在 `webpack --config 配置文件`，打包生成的文件都会放到 dist 目录下，该目录会自动生成;

4. webpack 配置文件
	- webpack入口文件的编译解析
	```javascript
		module.exports = {
			entry: "./src/index.js",
			// entry: {             与上方的写法一致,可以用这种方式来定义多个入口
			//     main: "./src/index.js"
			// },
			output: {
				path: path.resolve(__dirname, "dist"),  // 使用 process.pwd()来项目的根目录
				// filename: "index.js"   默认名称是 main.js
				filename: "[name].[hash:8].js"
				// 使用 hash:8 来进行截断操作, hash实现根据文件生成 hash 值的方法,使用hash 的作用是为了防止线上更新的时候避免有缓存
				// chunkHash 是根据每个文件来创建的不同的hash值，hash的方法是全局的，每个文件的hash值都是一样的，如果修改一个文件，所有的文件哈希值都会变化
				// contentHash 是根据内容计算出来的 hash 值
				// 目前使用 chunkHash 比较多
			}
		}
	```
	使用modules.exports 导出相关配置信息。配置信息以对象的方式存在。
	- html 文件的编译解析，使用plugin 的html-webpack-plugin 插件来实现打包
	```javascript
	plugins:[
        new HtmlWebpackPlugin(
            {
                filename:"dist_index.html",
				// filename 表示生成的文件名称
                template:"src/index.html"
				// template 表示被解析的文件名称以及路径
				title: "webpack html lesson"
				// 使用title 定位html 文件的抬头，但是需要在html文件中<%= htmlWebpackPlugin.options.title %> 使用这个来定义网页标签名
            }
        ),
    ]
	```
	- css 文件， 需要安装 `css-loader` 
	```javascript
	  module: {
		rules: [
		  {
			test: /\.css$/i,
			use: ['style-loader', 'css-loader'],
		  },
		],
	  },
	```
	在 js 文件中引用该 css文件才能将css 文件嵌入到html 文件中，其实是嵌入到 js 文件中，只不过在执行js的过程中，该css 被加载
##### 在项目中使用 react
1. 运行 'cnpm install react react-dom -S' 安装包
    - react： 专门用于创建组件和虚拟DOM 的，同时组件的生命周期都在这个包中
    - react-dom： 专门进行DOM操作的，最主要的应用场景，就是 ReactDOM.render()
2. 在 index.js 页面中，创建容器：
```html
    <!-- 容器，将来，使用React 创建的虚拟 DOM 元素，都会被渲染到这个指定的容器中-->
    <div id="app"></div>
```
fiber 算法和 diff 算法
fiber 算法把渲染的进程设置成异步，且对渲染流程进行优先级控制。

3. react 的几个特点
- 虚拟DOM 
- 组件化
- jsX(javascriptxml)

react-native :可以将js代码转换成 object-c java 来完成app应用
react-web 
react-VR：虚拟现实 

16 16.3 16.8 三个版本需要注意，16版本的写法有了比较大的变化

4. npx create-react-app 01.react-tuts
5. 删除 src 下文件
6. 安装 vscode 插件 ES7 React/Redux/GraphQL/React-Native snippets
7. npm start
8. react 创建组件的第一种方式：箭头函数
9. react 创建组件的第二种方式: 使用类的方式
10. react 创建组件的第三种方式：使用React.createElement 的方法进行创建
- react 增加组件 css 样式的时候
    1. 使用内联的方式，在里面直接添加
    ```javascript
    class App extends Component {
        render (){
            const style = {color: 'red'};
            return(
                <div>
                    {/* 第一种使用css的方式，采用js的方式 */}
                    <h1 style={style}>元素中的样式</h1>
                </div>
            )
        }
    }
    ```
    2. 使用引入 css文件和类名的方式，引入css文件
    ```css
        <!-- index.css -->
        .has-text-color{
            color: gold
        }
    ```
    ```javascript
        import './index.css'
        class App extends Component {
            render (){
                const style = {color: 'red'};
                return(
                    <div>
                        {/* 第一种使用css的方式，采用js的方式 */}
                        <h1 className='has-text-color'>元素中的样式</h1>
                    </div>
                )
            }
        }                 
    ```
    3. 使用工具来动态添加不同的class 来配置css
    ```javascript
     <li className={classNames('a', {'b': true, 'c': false})}>
    ```
    4. style-components 插件,利用 styled-components 来实现封装单独组件
    ```javascript
        <!-- 单独定义一个组件 -->
        const Title = styled.h1`color: purple`

        <!-- <h1>h1标签<h1> -->
        <!-- 替换为下面的组件标签 -->
        <Title>h1标签</Title>
    ```

>1. 在你的GitHub上新建个仓库，把地址复制下来备用
>2. 项目所在文件夹下git init
>3. git add . （点的意思是所有文件，把所有文件添加上去）
>4. git commit -m "xxxxxxxxxx"（提交信息）
>5. git remote add origin https://github.com/xxx/xxx（刚才你在GitHub上保存的地址）
>6. git pull origin master（上传之前先拉一下，第一次不拉也行，但是之后提交最好想成这个习惯）
>6. git push -u origin master（把你的代码提到GitHub上）

##### react 组件化目录组织模式
1. index.js 是入口文件
```javascript
    import React, { Component } from 'react'

    export class App extends Component{
        render(){
            return (
                <div>
                </div>
            )
        }
    }
    // 可以在安装插件  ES7 React/Redux/GraphQL/React-Native snippets 之后
    // 直接使用 rcc(react class component ) 来快速完成上述代码 rfc(react function component) 函数式组件
```

2. src目录下封装组件
```shell
    #src---
    #    index.js    import XX from './App'
    #    App.js      import {TodoHeader, TodoList} from './components'
    #    |-component
    #        |-index.js
    #        |-TodoHeader  // 组件
    #            |-TodoHeader.js / index.js #使用index.js 的好处是在引用的index.js 的时候只要指定目录即可，程序会默认找index.js
    #        |-TodoList
    #            |-TodoList.js
    #            |-TodoItem.js
```

3. 每个组件只能有一个根元素，当多个元素组合的时候需要加一个 div 标签，当不需要使用 div 来做父元素的时候，可以使用react 的 Fragment 空标签,或者在引入 Fragment 之后 直接使用 空标签

```javascript
    import react, {Component, Fragment} from 'react'
    <Fragment>
    </Fragment>
    // 或者直接使用空标签，但是也是需要引入 Fragment 
    <></>
```





































