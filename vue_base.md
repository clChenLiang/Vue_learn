|常见 api||
|--|--|
|:visible :visible.sync v-model  label-width slot slot-scope||

npm 命令：
npm run 
npm build
npm install
npm 

slot API 特性：


科班教程：
基本指令:
v-if   v-bind  v-on  v-for  
v-else  v-if-else  
v-show 保留在 DOM 中，基于 CSS 进行变换

$event 传递原始 DOM 事件信息

v-model  双向绑定
ref    引用，提供子组件在父组件中的引用
slot  插槽，分发原始内容
基本属性：
prop  el  data   computed  watch
key  不要复用两个元素
directive

生命周期：
beforeCreate  created beforeMount mounted  updated  destroyed  
生命周期函数的 this 都是指向组件的，所以不能使用箭头函数，以免破坏作用域

inserted  在用户自定义指令 directive 下的插入前
事件函数：
keyup  click  

事件修饰符：
.stop  停止继续传播        .once
.prevent  阻止事件
.capture   .self  事件是自身发起的

自定义指令：

directives  组件的属性
hook 函数


|钩子名称|作用解释|特别说明|
|--|--|--|
|bind |当自定义指定第一次绑定的时候触发，随后失效||
|inserted |当被绑定元素插入父节点时触发|仅需要父元素存在即可，不需要在 DOM 中||
|update|绑定元素的 VNode 数据发生变动|可能发生在子组件前|
|componentUpdated|当组件及其子 VNode 全部更新后调用||
|unbind|指令与元素解绑时调用 ||


[钩子函数参数](https://cn.vuejs.org/v2/guide/custom-directive.html#钩子函数参数)（事件发生时，给钩子函数传递的参数）


| 参数 | 说明 |
|--|--|
|el |将要绑定的元素|
|binding |包含 {name, value, oldvalue, expression, arg, modifiers} 属性的 object ，|
|vnode |Vue 编译器解析的虚拟节点|
|oldVnode |只在 update 与 componentUpdated 两个钩函数中传递|

举例：
    例1：
    
    Vue.directive('focus', {
        bind:,
        inserted:function(el, binging, vnode){
            
        }
    })
例2：简写形式，只绑定 inserted 与 update ,且两者行为保持一致

    Vue.directive('focus', (el.binding)=>{
        ...
    })


创建组件的几种方法：

|new Vue()|.vue文件|Vue.component()|createElement()|
|--|--|--|--|
|||Vue.component('elName',{options},)|

琐碎杂项 - 待整理

|序号|问题|解释|整理|
|---|--|--|---|
|1|slot|slots().default  <span style="color:green">$slots</span>|
|2|mixin|
|3|Vue.filter('',function(){})|调用时直接使用 '\|' 符号串联各个过滤器|


核心概念

|概念|解释|
|--|--|
|模板字符串|
|模板文件|
|单文件组件|| 
  
插件  
Vue.use()  开发插件，需提供 install 方法

注意事项：
vm.items[key] = newValue , 不会触发 Vue 的检测
vm.items.length = n , 也不会
使用 splice() 或者 Vue.set() 方式替代上述方法
模板标签内部属于父级组件，在模板渲染时会被丢弃，除非有插槽 slot 引用进去；变量不知道怎么传进去？
