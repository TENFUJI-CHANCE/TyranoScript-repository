# 菜单·html设定

快速跳转：
- [[showsave] 显示保存画面](#showsave)
- [[showload] 显示读取画面](#showload)
- [[showmenu] 显示菜单画面](#showmenu)
- [[showlog] 显示历史记录](#showlog)
- [[web] 打开外部网站](#web)
- [[html] 添加html层](#html)
- [[endhtml] 结束html层](#endhtml)

### <a id="showsave"></a> **[showsave] 显示保存画面**

显示保存画面。

代码结构及示例：
```
[showsave]
```
  
### <a id="showload"></a> **[showload] 显示读取画面**

显示读档画面。

代码结构及示例：
```
[showload]
```
  
### <a id="showmenu"></a> **[showmenu] 显示菜单画面**

显示菜单画面。

代码结构及示例：
```
[showmenu]
```
  
### <a id="showlog"></a> **[showlog] 显示历史记录**

显示历史文本画面。

代码结构及示例：
```
[showlog]
```
  
### <a id="web"></a> **[web] 打开外部网站**

该标签用于在浏览器加载外部网站。只要该网站可以访问。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|url|要打开的网站的URL地址。如果您想在游戏内打开一个图片文件，请先在data文件夹里放入指定的文件||〇|

代码结构及示例：
```
[web url="https://www.example.com"]
```
  
### <a id="html"></a> **[html] 添加html层**

该标签用于在游戏中添加一个html，它将在前景层显示。

此功能非常强大。您可以嵌入JavaScript、svg、网络视频，并支持所有新一代网络表达形式。

您可以在 HTML 中使用 TyranoScript 变量。使用 [emb] 标签的方式与使用常规文本时相同。

**注意：在游戏使用HTML显示内容时，鼠标点击等用户操作输入无法使游戏继续进行。请务必设置一个图形按钮或其他类似元素，以便让游戏通过点击等操作得以推进。**

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|left|设定HTML的x轴位置|
|top|设定HTML的y轴位置|
|name|设定HTML的名称。该属性可用于让[anim]标签给HTML层添加动画，|

代码结构及示例：
```
[html top=100 left=300]

<object width="200" height="113">
<param name="movie" value="http://www.youtube.com/v/60TMm2sQTBU?version=3&amp;hl=ja_JP&amp;rel=0">
</param>
<param name="allowFullScreen" value="true"></param>
<param name="allowscriptaccess" value="always"></param>
<embed src="http://www.youtube.com/v/60TMm2sQTBU?version=3&amp;hl=ja_JP&amp;rel=0" type="application/x-shockwave-flash" width="200" height="113" allowscriptaccess="always" allowfullscreen="true">
</embed></object>

[endhtml]
```
  
### <a id="endhtml"></a> **[endhtml] 结束html层**

该标签用于结束由[html]标签创建的html层。

代码结构及示例：
```
[endhtml]
```
