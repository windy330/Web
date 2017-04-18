### 编码模式

1 缓存：将ajax里面请求来的数据放到全局变量里面做缓存，便于重用

2 沙箱

```js
window.overVar = {};

;(function() {
    var cacheVar = true;
    overVar .myInitGame = function() {
        var localVar = true;
    };
});
```

```js
overVar .myInitGame();
```

3 图片缓存

```js
// 当image对象的src被赋值的时候，就开始请求图片
function main() {
    var prizeImgs = ['http://www.xxx.xx.png','http://www.xxx.yy.png']
    for(var i=0;i<prizeImgs.length; i++) {
        var img = new Image();
        (function(i , img ){
            img.onload = function(){
                biultImgO(i,img);
            };
        })(i , img);
        img.src = prizeImgs[i];
    }
}
function biultImgO() {
    
}
```


