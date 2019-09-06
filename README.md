# Notes
## text-indent:-9999px
=>字体隐藏属性，通常为了传达更好的视觉效果，我们常用图片替代掉字体。但是为了更好地让搜索引擎检索到，所以隐藏字体。
## onclick="return false;"
=>组织a链接的默认打开一个新窗口的事件发生.
## v-on:click.prevent
=>为了阻止链接在被点击时跳转。
## margin&padding的值各为4，3，2，1个的时候的代表含义
=>margin为4个时，margin:上  右  下  左;（为顺时针方向）<br>
=>margin为3个时，margin:上   左=右   下;<br>
=>margin为2个时，margin:上=下   左=右;<br>
=>margin为1个时，margin:上=右=下=左;
## visibility:hidden与display:none的区别
=>visibility:hidden将元素隐藏，但在网页所占的空间位置依然存在。<br>
=>display:none将元素的显示设置为无，在网页不占用任何空间.
## display常用属性值
=>none:此元素不会被显示<br>
=>block:此元素将被显示为块级元素，元素前后带有换行符<br>
=>inline:默认。此元素会被显示为内联元素，元素前后没有换行符<br>
=>inline-block:行内块元素
## 实现以一块图片为背景图片透明一个div
透明的div需要加position:absolute;而透明div外层的div要加上position:relative; 才能让透明div相对于外层div去定位，设置透明区域background:rgba(0,0,0,0.6)。并且将图片上层的divz-index属性的值调高。
## z-index
=>可被用于将在一个元素放置于另一元素之后.默认的是z-index是0，z-index-1拥有更低的优先级。
## nodemon安装后但是无法使用
=>是因为全局安装的路径不对，可以将全局安装的路径（F:\nodejs\node_global）添加到系统变量中
## webpack四个核心概念。
=>entry（入口）、output（输出）、loader（依赖加载）、plugin（插件）
## get和post方法的区别
=>1.get把请求的数据放在URL上，post把数据放在HTTP的包体内（request body）<br>
  2.get提交数据有大小限制，而post没有<br>
  3.get产生一个tcp数据包，post产生两个tcp数据包<br>
  4.最后，get效率比较高
## bcrypthash加密函数参数个数版本发生变化 参照如下
=>//密码hash加密
                bcrybtNodejs.genSalt(10, function(err, salt) {
                    bcrybtNodejs.hash(newUser.password, salt, null,function(err, hash){
                        //如果有错误则抛出异常
                        if(err)  throw err;

                        //没有错误的话将加密后的密码赋值给...
                        newUser.password=hash;

                        newUser.save()
                            .then(user=>res.json(user))
                            .catch(err=>console.log(err))
                    });
## 实现水平居中常用的几种方法
1.margin: 0 auto;<br>
2.text-align: center;<br>
3.父元素display: flex;flex-direction: column;子元素align-self: center;<br>
4.父元素display: table-cell;子元素margin-left取值剩余宽度的一半(或者父元素position: absolute;)<br>
## 实现垂直居中常用的几种方法
1.display: inline-block;vertical-align: middle;<br>
2.父元素display: flex;flex-direction: row;子元素align-self: center;<br>
3.父元素display: table;子元素display: table-cell;vertical-align: middle;<br>
4.设置行高，该元素的行高和其父元素的高度保持一致.
## 浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？
在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。
离线的情况下，浏览器就直接使用离线存储的资源。
## 关于cookies，sessionStorage 和 localStorage 的区别
相同：都存储在客户端（浏览器）<br>
1.存储大小<br>
cookies数据大小不能超过4k<br>
localstorage和sessionstorage也有数据限制，但可以达到5m<br>
2.有效时间<br>
localstorage只有主动删除数据才会消失<br>
sessionstorage在窗口关闭的时候数据自动删除<br>
cookies可以设置数据的有效时期<br>
3.数据与服务器端的交互方式<br>
cookie会把数据传输到服务端，服务端也可以写cookies到客户端<br>
localstotage和sessionstorage不会把数据传输到服务端，只保存在本地
## 清除浮动的方式以及优缺点<br>
1.clear:both简单，浏览器兼容性好，但容易造成页面混乱<br>
2.overflow:hidden使用简单，但是超出的尺寸会被隐藏<br>
3.使用伪元素:after浏览器兼容性好，但是代码较为复杂
## 闭包是什么 有什么特性 对页面有什么影响？
闭包是指有权访问另一个函数作用域的变量的函数<br>
封闭性：外部无法访问闭包北部的数据<br>
持久性：函数被调用后，闭包结构依然存在。<br>
过多的使用闭包会导致内存溢出
## 在 javascript 中，用于阻止默认事件的默认操作的方法是
preventDefault()
## link和@import的区别
1.link是由HTML提供，@import是由CSS样式提供<br>
2.link不仅能引入样式，比如定义RSS，定义rel连接属性等<br>
3.link引入的样式会在页面加载的时候同时加载，而@import引入的则会在页面加载完后再加载<br>
4.兼容性有一定的差别<br>
5.dom可以控制link但是不能控制@import
## HTML5新特性有哪些 删除了哪些元素？又如何处理兼容性的问题呢？如何区分HTML5和HTML！
1.语义化<br>
2.本地存储<br>
3.设备兼容<br>
4.连接特性，能够帮助我们将数据推送到客户端<br>
5.网页多媒体特性<br>
6.三维、图形及特效特性<br>
7.性能与集成特性<br>
8.css3特性<br>
### 移除的元素
纯表现的元素：basefont，big，center，font,s，strike，tt，u<br>
对可用性产生负面影响的元素：frame，frameset，noframes<br>
1.使用html5shim框架<br>
2.IE8/IE7/IE6支持通过document.方法产生的标签,利用这一特性让这些浏览器支持HTML5新标签。
### 区分
用doctype来区分
## iframe的优缺点
### 优点
1.iframe能够原封不动的把嵌入的网页展现出来。<br>
2.可以增加代码的可重用.<br>
### 缺点
1.会增加服务器的请求<br>
2.代码复杂，无法被搜索引擎解读。<br>
3.不易管理
## $(document).ready和window.onload的区别
$(document).ready()在DOM树加载完之后所有元素加载完成之前就可以执行了<br>
window.onload()需要在所有元素渲染完成后再执行
## 闭包是什么，为什么要使用闭包？
一言以蔽之，闭包就是可以调用其他函数作用域变量的函数，闭包的使用可以使变量一直存在在内存中。
## 如何定义嵌套路由
通过children来实现
## 如何设计动态路由，并动态获取参数？
使用 path 属性，使用动态路径参数，以冒号开头。当匹配到 /user 下的任意路由时，参数值会被设置到 this.$route.params 下，所以通过这个属性可以获取到动态参数。
## v-model是什么，如何使用？
就是表单数据的双向绑定！
## scss是什么，如何安装使用，有什么特性？
css预编译器的一种，可嵌套型，可重用性高，有函数功能。
## Restful api是什么？为什么要用它！
restful其实就是一套编写接口的协议
## 谷歌浏览器默认最小字体是多少？
12px
## postion常用属性值
fixed:生成绝对定位元素，相对于浏览器窗口进行定位，元素位置通过“left”，“right”，“top”，“bottom”属性进行规定<br>
absolute:生成绝对定位元素，相对于父元素进行定位，元素位置通过“left”，“right”，“top”，“bottom”属性进行规定<br>
relative:生成相对定位定位元素，相对于正常位置进行定位<br>
static:默认值，没有生成定位<br>
inherit:从父元素继承postion的值
## letterspace属性
表示该元素的字母间距.
## 关于小程序中var that=this;的作用
因为this所指的当前对象，所以this对象在程序中随时会改变，而var  that = this之后，that不会改变，仍然指向之前的this，这样就不会找不到原来的对象（个人理解）.
## 在bootstrap中，响应式布局（栅格布局）lg,md,sm,xs分别对应的像素宽度是多少？！
* col-xs-  超小屏幕 手机 (<768px)
* col-sm-  小屏幕 平板 (≥768px)
* col-md-  中等屏幕 桌面显示器 (≥992px)
* col-lg-  大屏幕 大桌面显示器 (≥1200px)
## ES6数组去重
arr=new Set(arr);
## jQuery中append()与prepend()的区别
append() - 在被选元素的结尾插入内容<br>
prepend() - 在被选元素的开始插入内容
## querySelector(API)
元素向下查询，返回一个元素
## .blur()方法
失去焦点的时候触发
## jQuery.serialize()方法
对表单的值进行序列化排序，&连接。
## window.history用法
history.back(-1):直接返回当前页的上一页，数据全部消息，是个新页面<br>
history.go(-1):也是返回当前页的上一页，不过表单里的数据全部还在 <br>
history.back(1) 前进 <br>
history.back(-1) 后退<br>
window.location.reload();    //刷新  <br>
window.history.go(1);         //前进  <br>
window.history.go(-1);        //返回+刷新  <br>
window.history.forward();  //前进  <br>
window.history.back();       //返回
## Vue实现遮罩层弹出的时候禁用滑动事件
在遮罩层加上属性@touchmove.prevent
## 解决Vue在ios端滚动不流畅的问题
在滚动列表的Listdiv增加css属性-webkit-overflow-scrolling: touch;<br>
.box{<br>
  overflow-y: scroll;<br>
	touch-action: pan-y;<br>
	-webkit-overflow-scrolling: touch;<br>
}
