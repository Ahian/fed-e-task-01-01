# fed-e-task-01-01

选择题
1、下面关于虚拟 DOM 的说法正确的是：ABCD
A. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高程序的性能。

B. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高开发效率。

C. 虚拟 DOM 可以维护程序的状态，通过对比两次状态的差异更新真实 DOM。

D. 虚拟 DOM 本质上是 JavaScript 对象，可以跨平台，例如服务器渲染、Weex 开发等。

2、下面关于 Snabbdom 库的描述错误的是：C
A. Snabbdom 库是一个高效的虚拟 DOM 库，Vue.js 的虚拟 DOM 借鉴了 Snabbdom 库。

B. 使用 h() 函数创建 VNode 对象，描述真实 DOM 结构。

C. Snabbdom 库本身可以处理 DOM 的属性、事件、样式等操作。错：需要插件

D. 使用 patch(oldVnode, null) 可以清空页面元素

简答题
1、请简述 patchVnode 函数的执行过程。
作用：对比两个新旧节点，然后更新差异。

过程：
1. 触发prepatch钩子函数
2. 触发update钩子函数
3. 新节点有text 属性，且不等于旧节点的text 属性。如果老节点有children就移除，然后设置新节点对应的DOM 元素的textContent
4. 新老节点都有children ，且不等，1. 调用updateChildren() 2. 对比子节点，更新子节点差异
5. 只有新节点有children 1.如果老节点有text 属性，清空对应DOM 的textContent 2. 添加所有子节点
6. 只有老节点有children，移除老节点。
7. 只有老节点有text 属性,清空对应DOM 的textContent 
8. 触发postpatch 钩子函数