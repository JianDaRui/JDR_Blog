<!--
 * @Author: your name
 * @Date: 2020-08-03 18:48:15
 * @LastEditTime: 2020-08-29 12:13:05
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \JDR_Blog\docs\Front_End\ECMAscript\Prototype.md
-->
# JavaScript中的原型、原型链与面向对象
- 对象：以键值对这种形式呈现的属性的集合。
- 构造函数：这个函数可不可以通过`new`来创建对象，如果可以则为构造函数。注意在`Javascript`中构造函数与普通的函数并没有区别，函数名称的大小写只是一种约定。在面向对象过程中构造函数可以确保实例有不同的特征。
- 原型：每一个构造函数都会有`prototype`属性，`function.prototype`指向构造函数的原型，原型其实也是对象，既然是对象那原型可以是另一个函数或者类实例。实例对象又会有一个`__proto__`属性，该属性与`function.prototype`指向相同的位置———原型。并且原型有一个不可枚举的属性`constructor`，该属性指向原型的构造函数。在面向对象过程中，原型负责保存实例共有的属性。
- 原型链：在Javascript，每一个对象都有一个__proto__属性，__proto__指向该对象的原型对象，当访问一个对象自身不存在的属性时，JavaScript引擎就会通过__proto__去对象原型上查找，如果该原型还没有，那么会到该原型的原型上查找，最顶层可查找到 Object.prototype 的原型 **null**。

总结：在JS中构造函数是用来创建对象的，确保对象有不同的特征。而原型一方面可以确保对象有共同的属性以方便又可以节省代码执行过程中的性能损耗。而原型链就是确保实例与原型之间的连接，确保实现继承的效果。

## 对象
- 
```js
function girlFriend() {
  let girl = new Object()
  girl.height = 180
  girl.braSize = "G"
  girl.callMe = function() {
    console.log("剑大瑞")
  }
  girl.giveServe = () => {
    console.log("老公坐，我给你煲了牛鞭汤🙈")
  }
  return girl
} 
let myGirl = new girlFriend()
console.dir(myGirl)
console.dir(myGirl.callMe)
console.dir(myGirl.major)
```
