###less安装
1. 安装nodeJs
2. 配置npm
![](/assets/21.bmp)

3. 确保有下面这两个文件夹
![](/assets/22.bmp)

4. 确保npm文件夹里面有这四个文件
![](/assets/23.bmp)

5. 确保node_modules里面有less文件

>由于sass的安装说明我放在别的文件夹里面了,我就不在这里重复讲了

###sass与less的区别
####主要针对rem适配的时候用less和sass语法上的区别
```css
//这是less的写法,750rem/@font-size,即使单位不一样,这个也不会报错,但是sass会报错
@font-size : 75px;

header {

 width: 750rem/@font-size;

 height: 40rem/@font-size;

 font-size: 20rem/@font-size;

 background: red;

 }
```
```css
//函数,rem适配,可以看出argument是px,($px/40px)相除之后是一个没有单位的数字,*1rem后就加上了单位rem.

@function torem($px){//$px为需要转换的字号

 @return $px / 40px * 1rem; //40px为根字体大小

}

header {

 display: block;

 width: torem(750px);

 height: torem(30px);

 font-size: torem(20px);

 background: red;

}

```
###sass常见的错误
>而最为常见的一个错误就是字符编译引起的。在Sass的编译的过程中，是不是支持“GBK”编码的。所以在创建 Sass 文件时，就需要将文件编码设置为“utf-8”。

>另外一个错误就是路径中的中文字符引起的。建议在项目中文件命名或者文件目录命名不要使用中文字符。而至于人为失误造成的编译失败，在编译过程中都会有具体的说明，大家可以根据编译器提供的错误信息进行对应的修改。