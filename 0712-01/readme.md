### 实例化一个vue对象最基础的一个参数
el: vue对象在文档中的挂载点
类型可以是一个CSS选择符 或者一个DOM元素 一个函数（在组件定义中必须是函数 这个在helloWorld中不说-.-）

CSS选择符需注意一点：
  如果匹配的DOM元素为多个 vue对象只会挂载到第一个匹配到的元素上

DOM元素只能是DOM元素 不能是NodeList 神马神马的


```html
<div id="demo"></div>
```
```javascript
new Vue({
  el: '#demo'
});
```
最简单的一个实例化一个vue对象 但是好像并没有什么卵用
遂 我们需要 官网中hello world的第二个参数

```javascript
new Vue({
  el: '#demo',
  data: {
    message: 'hello world'
  }
})
```

data: vue对象的数据<br/>
展示数据使用 文本插值<br/>
```html
<div id="demo">
  <p>
    {{{message}}}   # 此处key值对应的为 data.message
  </p>
</div>
```
vue对data中所有的item进行get set的代理<br/>
可以直接通过 this.XXX 来获取到data某个item的值<br/>
也可以通过 this.$data 来获取到原始的data对象
```html
<div id="demo">
  <input v-model="message">
</div>
```
双向数据绑定使用 v-model<br/>
双向数据绑定会在数据值发生变化时 修改data中的值 并对应更新其他用到该值的地方<br/>
而文本插值只做展示
