### methods参数
methods作为实例的方法的集合 类型必须为一个Object 且里边的key所对应的必须是一个function<br/>
通过v-on:XXX 指令可以绑定函数到对应的事件
```html
<div id="demo">
  <button type="button" name="button" v-on:click="methodName">click me</button>
</div>
```
```javascript
new Vue({
  el: '#demo',
  methods: {
    methodName: function () {
      alert('aha');
    }
  }
});
```
v-on:指令因为是比较常用的指令 所以可以缩写为: @
```html
<button type="button" name="button" v-on:click="methodName">click me</button>
<button type="button" name="button" @click="methodName">click me</button>
```
在函数中 this指向该vue的实例<br/>
所以可以直接通过this.XXX 来获取到 data中的值
