# 开始使用Vue
  1. 引入vue.js
      > 官网：vuejs.org

      > 开发版本：包含完整的警告和调试模式
      
      > 生产版本：删除了警告，体积更小

  2. 引入vue.js后，给我们提供了一个构造函数 Vue
  3. 在js中，`new Vue()`
  4. `new Vue()` 后会返回一个vue实例对象，我们用变量接着它
  5. `const vm = new Vue()`
  6. 传递一个配置对象{} -- > `const vm = new Vue({})`

## el
  > 类型： 字符串

  > 全称：element（元素）

  > 作用：配置控制的元素，表示Vue要控制的区域，值为css选择器
  ``` html
    <!-- 被Vue控制的区域，我们称之为模板 -->
    <div id="app"></div>
  ```
  ```js
    const vm = new Vue({
      el: '#app' // 控制id为app的元素
    })
  ```

## $mount
- 作用和el一致，都是配置控制的元素，使用哪个都可以，二选一
  ``` html
    <div id="app"></div>
  ```
  ```js
    const vm = new Vue({})
    vm.$mount('#app');
  ```
- 问：和el有什么不同？
  > 答：本质上没什么不同，$mount为手动挂载，在项目中有时要进行延迟挂载，比如有时要在挂载之前进行一些其他的操作，比如判断等等（但是，这样做的时候很少，比邓哥回家的次数还少，emmmmm）

## data
- 类型：对象
- 作用：存放要用到的数据，数据为响应式的
  ```js
    const vm = new Vue({
      el: '#app',
      data: {
        'msg': '雾岛董香'
      }
    })
  ```
## 插值表达式
- 使用方法： {{ }}
- 可以将vue中的数据填在插值表达式中，如：
  ``` html
    <div id="app">{{ msg }}</div>
  ```
  ```js
    const vm = new Vue({
      el: '#app',
      data: {
        msg: '金木研'
      }
    })
  ```