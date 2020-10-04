# fed-e-task-03-05
## 1、Vue 3.0 性能提升主要是通过哪几方面体现的？

- 响应式原理采用es6新特性proxy方式
- 对编译器进行了优化，重写了虚拟dom，渲染和更新的性能得到了提升。
- 服务器端渲染性能提升
- 移除了不常用的api，优化了代码体积

## 2、Vue 3.0 所采用的 Composition Api 与 Vue 2.x使用的Options Api 有什么区别？
 2.x中的Options Api是一个包含描述组件选项的对象，在开发复杂组件时，相同功能逻辑的代码可能被拆分到不同的组件中。3.0的 Composition Api 基于函数
，根据逻辑来灵活的组织组件，可以更好的重用逻辑。

## 3、Proxy 相对于 Object.defineProperty 有哪些优点
- 性能高于defineProperty
- 不需要初始化时遍历所有属性
- 可以监听到数组的索引和length
- 可以监听动态新增的属性
- 可以监听删除的属性


## 4、Vue 3.0 在编译方面有哪些优化？
- 首先标记和提升所有的静态根节点，在进行diff时，只需对比动态节点的内容
- 使用Fragments,模板中不需要再创建根结点
- 静态提升
- patch flag,diff时跳过静态节点
- 缓存事件处理函数,减少不必要的更新操作


## 5、Vue.js 3.0 响应式系统的实现原理？
3.0中使用proxy重写响应式系统，主要由reactive、effect、track、trigger、ref、toRefs、computed组成。
- reactive：将对象转换为响应式对象
- effect：访问响应式对象属性时去收集依赖
- track：收集依赖
- trigger： 更新函数
- ref： 将基本数据转换为响应式对象
- toRefs：接收一个reactive返回的对象或proxy对象，转换为响应式返回
- computed：计算属性
