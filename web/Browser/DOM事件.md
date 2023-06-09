# DOM 事件类型

- 用户界面事件      涉及与 BOM交的通用浏览器事件
- 焦点事件              在元素获得和失去焦点时触发
- 鼠标事件              使用鼠标在页面上执行某些操作时触发
- 滚轮事件              使用鼠标滚轮(或类似设备)时触发
- 输入事件              向文档中输人文本时触发
- 键盘事件              使用键盘在页面上执行某些操作时触发
- 合成事件              在使用某种IME(Input Method Editor，输入法编辑器)输入字符时触发



## 用户界面事件

用户界面事件或UI事件不一定跟用户操作有关

### 1. load 事件

`load`事件是在页面或资源加载完成时触发的事件。当整个页面及其所有相关资源（例如图像、样式表、脚本等）都加载完成后，浏览器会触发`load`事件。

`load`事件通常用于执行一些需要在页面加载完成后进行的操作，例如初始化页面数据、绑定事件处理程序、执行动画效果等。可以将需要在页面加载完成后执行的代码放在`load`事件的处理程序中。

```javascript
window.addEventListener("load", (event) => {
    console.log("Load")
})
```



### 2. unload 事件

unload 事件会在**文档卸载完成**后触发

`unload`事件是在浏览器窗口或标签关闭或刷新时触发的事件。它提供了一个机会执行清理操作或在用户离开页面之前保存数据。当`unload`事件被触发时，页面的资源和状态将被销毁，因此不建议在`unload`事件处理程序中执行复杂的操作或阻塞代码。常见的应用场景包括**清除定时器、取消网络请求、保存表单数据**等。

```javascript
window.addEventListener("unload", (event) => {
    console.log("Unload")
})
```



### 3. resize 事件

resize事件是在浏览器窗口大小发生改变时触发的事件。当用户调整浏览器窗口的大小，或者设备屏幕的大小发生变化时，会触发resize事件。

```javascript
window.addEventListener("resize", (event) => {
    console.log("Resize ")
})
```

需要注意的是，由于resize事件触发频率较高，特别是在用**户拖动浏览器窗口边界时**，resize事件可能会频繁触发。为了避免性能问题，可以采用一些优化策略，如使用节流函数或防抖函数来限制resize事件的触发频率。

另外，对于**移动设备**，由于**屏幕方向的改变也会导致窗口大小的改变**，因此resize事件在移动设备上也会被触发。在响应移动设备的屏幕方向改变时，可以通过resize事件来进行相应的调整和适配。



### 4. scroll 事件

scroll事件是在元素滚动时触发的事件。当元素的滚动条滚动时，无论是通过鼠标滚轮、键盘方向键、触摸操作还是编程方式触发，都会触发scroll事件。

```javascript
window.addEventListener("scroll", (event) => {
    console.log(document.body.scrollTop)
})
```

需要注意的是，**scroll事件会频繁触发**，特别是在用户拖动滚动条时，scroll事件会连续触发。为了避免性能问题，可以采用一些优化策略，如使用**节流函数**或**防抖函数**来限制scroll事件的触发频率。

此外，scroll事件可以应用于各种元素，包括窗口、容器元素、滚动区域等。可以根据实际需求，在相应的元素上添加scroll事件监听器来实现相应的功能。

