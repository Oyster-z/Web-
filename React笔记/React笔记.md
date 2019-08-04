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
    上面的例子,可以执行的命令有 `npm run build` 和 `npm run test`,这样可以新建一条命令，命令的内容调用 webpack 的命令

##### 在项目中使用 react
1. 运行 'cnpm install react react-dom -S' 安装包
    - react： 专门用于创建组件和虚拟DOM 的，同时组件的生命周期都在这个包中
    - react-dom： 专门进行DOM操作的，最主要的应用场景，就是 ReactDOM.render()
2. 在 index.js 页面中，创建容器：
```html
    <!-- 容器，将来，使用React 创建的虚拟 DOM 元素，都会被渲染到这个指定的容器中-->
    <div id="app"></div>
```
