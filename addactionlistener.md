###兼容问题以及处理方法
1. addEventListener
```javascript
// 注册事件的方法
function regEvent(element, event_name, fun)
{
    // 处理ie
    if (window.attachEvent) 
        element.attachEvent(event_name, fun);  //IE浏览器
    else
    {
        event_name = event_name.replace(/^on/, “”);   //如果on开头，删除on，如onclick->click
        element.addEventListener(event_name, fun, false);  //非IE浏览器
    }
}
```