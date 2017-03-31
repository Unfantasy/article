# 对Preact的初步探索

## 官方解释
**Preact is a fast, 3kB alternative to React, with the same ES2015 API.** <br/>
也就是React的轻量化解决方案下的产物。

## 一些值得参考的网站
* 官方网站 https://preactjs.com/
  * 里面介绍了[如何开始使用Preact](https://preactjs.com/guide/getting-started) , [与React的不同之处](https://preactjs.com/guide/differences-to-react)以及[如何从React迁移到Preact](https://preactjs.com/guide/switching-to-preact)。
* github https://github.com/developit/preact
* https://github.com/lcxfs1991/blog/issues/13
  * 一篇分析Preact的很全面的文章

## 包含的特性
* [ES6 类]
  * 类提供一个丰富表现力的途径去定义具有状态的组件
* [高阶组件]
  * 组件在 `render()`中返回其它组件，一个高效的封装
* [无状态的纯函数式组件]
  * 接收 `props`作为参数并返回 JSX/VDOM 的函数
* [场景]: 从 Preact 3.0 起 支持`context`
  * `context` 是 React实验性的特性，但许多库都已经采纳了
* Refs: 从 Preact 4.0 起支持 函数 refs 引用。字符串 refs 引用在 `preact-compact` 中支持
  * Refs 提供一个办法去引用被渲染的元素和子组件
* 虚拟 DOM 比较
  * 这是一个规定的特性 - Preact 的虚拟 DOM 比较 虽简单但高效 而且 特别 快.
* `h()`,一个更为通用的 `React.createElement` 实现版本
  * 这是一个通常被称作 [hyperscript](https://github.com/hyperhype/hyperscript) 的概念，而且它的价值远比 React 的生态强, 所以 Preact 发扬了它本来的规范. (请阅读: [why `h()`?](https://jasonformat.com/wtf-is-jsx/))
  * 而且它更可读一些: `h('a', { href:'/' }, h('span', null, 'Home'))`

## 新增的特性(与react比)
* `this.props` 和 `this.state` 帮你传进了 render() 作为参数
* [Linked State](https://preactjs.com/guide/linked-state) 当 inputs 输入框改变的时候，会自动更新状态state
* 批量 DOM 更新， `setTimeout(1)` 进行函数节流 使用 (也可以使用requestAnimationFrame)
* 你可以只用 `class` 作为 CSS 的类。 `className` 也仍然被支持， 但推荐使用 `class`
* 给一个对象设置 `class` 创建了一个包含可信的键值的字符串类名
* 组件和元素循环使用/存入池中

## 缺少的特性(与react比)
* PropType 验证
* [children](https://facebook.github.io/react/docs/react-api.html)
* Synthetic Events

## 具体区别
* `render()` 接受第三个参数，这是会被替换的根节点，否则，如果没有这个参数，Preact默认追加。这个将来的版本可能会有小的调整，可能会改成默认替换。

## 优点
可看这篇文章 [Preact -- React的轻量解决方案](https://github.com/lcxfs1991/blog/issues/13)
* 开源社区有较多star
* 较好的性能和兼容性
* api跟React接近
* 足够的框架周边，配置redux，router等使用
* 团队成员有能力维护的

## github上面与react的对比
截止至2017.3.17

||Preact|React|
| ----- | ----- | ------ |
|icon|![Preact](http://jiduo.org/images/Preact.png)|![React](http://jiduo.org/images/React.png)|
|star|8096|62072|
|最后提交时间|4天前|7天前|
|commits|809|8348|
|contributors|64|954|
|releases|104|54|
|issues|56 Open 238 Closed|568 Open 3635 Closed|
|PD|23|120|
|fork|316|11427|
|watch|206|4244|

## 将antd-mobile移植到Preact的尝试
由于antd-mobile是基于React的，所以简单的将之移植到Preact会报react找不到的错误，但是我不知道要怎么去改，可能这篇文章会有所帮助。https://preactjs.com/guide/switching-to-preact <br>
这边还有一个Preact + Redux Example Project 的参考 https://github.com/developit/preact-redux-example。

## 结论

从已知的情况来看Preact是有很多优点的，如果用它替换react最差的情况也就是用`preact-compact`设置一下就可以了吧。 <br>
补充： 基于React的组件类似antd-mobile的, 本人搞不定。。。
