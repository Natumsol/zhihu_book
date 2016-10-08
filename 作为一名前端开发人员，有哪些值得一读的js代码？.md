
#  [作为一名前端开发人员，有哪些值得一读的js代码？](https://zhihu.com/questions/27471576)



[@pw](https://zhihu.com/people/70ab0aaf2351b14e889417f1795df35a)

首先反对推荐读 jQuery 源码的，里面奇技淫巧太多，代码工程角度上来看不太适合实际产品的前端项目。有些代码在工程里面实际上是非常糟糕的写法，容易被带偏。<br><br>推荐 backbone.js 的源码，非常适合新手。<br><br>首先是代码结构清楚，几大模块，View/Model/Collection 像一本书一样简单清楚的介绍了现代前端 MVC 架构的组织方式，Events 的代码对于理解 Pub/Sub 模式也很有帮助。其次是奇技淫巧少，代码规矩。还有一个优点是 Annotated Source，有一份详细注释的代码文档，阅读起来非常舒服。当然最大大大的优点是代码量少啊，足够简单。<br><br>可以先上手一下简单的 Demo，比如 Backbone 的 TODO。然后看 Annotated Source，看下 TODO 里面所涉及的一些方法的原理。或者单独研究几个模块的实现，可以从 Events。或者研究一些核心方法，比如 Model.prototype.set。<br><br># 1月22日补充<br>下面提到的 underscore.js 也是很不错的项目，可以先看下文档，然后尝试自己实现里面提到的 API，然后对比下 underscore 的实现，对于了解 JS 语言特性很有帮助。<br><br>如果对 node.js 感兴趣，可以看 express 和 connect 的代码，可以了解到 HTTP 服务端的工作方式，服务端 MVC 模型，路由分发等等很有价值的工程知识。