# KO 的工作原理及其带来的好处

> 来源：https://knockoutjs.com/downloads/index.html

## 知识点：jQuery（回调）:绑定一个在 DOM 完成加载时要执行的函数。

### 这个函数的行为就像$( document ).ready()，

### 因为它应该用于包装$()页面上依赖于准备好的 DOM 的其他操作。虽然从技术上讲，这个函数是可链接的，但链接它并没有太多用处

例子： 
  1：当 DOM 准备好使用时执行该函数。
```js
        $(function () {
            // Document is ready
        });
```
  2：使用 $(document).ready() 的快捷方式和使用 $ 别名编写故障安全 jQuery 代码的参数，而不依赖于全局别名。
```js
    jQuery(function( $ ) {
      // Your code using failsafe $ alias here...
    });
```

激活ko  要使用 $(function () { }
```js
    $(function () {
            ko.applyBindings(viewModel);
        });
```
##KO 的主要好处之一是它会在视图模型更改时自动更新您的 UI。
KO 如何知道您的视图模型的某些部分何时发生变化？
答：您需要将模型属性声明为可观察对象，因为这些是特殊的 JavaScript 对象，可以通知订阅者更改，并且可以自动检测依赖关系。
