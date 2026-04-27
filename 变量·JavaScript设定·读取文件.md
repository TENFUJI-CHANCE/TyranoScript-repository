# 变量·JavaScript设定·读取文件

快速跳转：
- <a href="#loadjs">[loadjs] 导入使用外部JavaScript文件</a>
- <a href="#eval">[eval] 引入exp指定的JavaScript函数</a>
- <a href="#clearvar">[clearvar] 消除变量</a>
- <a href="#clearsysvar">[clearsysvar] 清除全部系统变量</a>
- <a href="#trace">[trace] 向控制台输入值</a>
- <a href="#iscript">[iscript] 编写JavaScript脚本</a>
- <a href="#endscript">[endscript] 结束JavaScript编写</a>
- <a href="#emb">[emb] 内嵌表达式</a>
- <a href="#preload">[preload] 预加载数据</a>
- <a href="#wait_preload">[wait_preload] 等待数据预加载完成</a>
- <a href="#unload">[unload] 删除预加载数据</a>
- <a href="#plugin">[plugin] 加载外部插件</a>
- <a href="#loadcss">[loadcss] 导入使用CSS文件</a>

### <a id="loadjs"></a> **[loadjs] 导入使用外部JavaScript文件**

该标签用于加载外部JavaScript文件，并在TyranoScript中使用其中定义的函数和变量。

外部js文件请放进data/others目录下。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|storage|设定要加载的JavaScript文件||〇|
|type|加载方法，默认为“text”。当值为“module”时，将以ES模块的方式加载JavaScript文件，这意味着文件中的变量和函数将不会被添加到全局作用域中，而是需要通过import语句来使用|

代码结构及示例：
```
[loadjs storage="example.js" type="text"]
```
  
### <a id="eval"></a> **[eval] 引入JavaScript表达式**

该标签允许设置变量和定义变量。在exp中指定的JavaScript语句将被执行。

这主要用于为变量赋值。请确保exp中的语句用双引号（""）括起来，因为这样做有助于避免意外情况的发生。

您可以在exp中指定任何 JavaScript 语句，这样您就能够执行函数了（这是高级功能）。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|exp|该属性的值应填写要执行的JavaScript表达式||〇|

代码结构及示例：
```
[eval exp="f.akane_like=50"]
```
  
### <a id="clearvar"></a> **[clearvar] 消除变量**

清除已定义的变量。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|exp|要清除的变量名。name和flag无法清除，如果不填写，则清除所有变量|

代码结构及示例：
```
[clearvar exp="example_variable"]
```
  
### <a id="clearsysvar"></a> **[clearsysvar] 清除全部系统变量**

该标签用于清除所有的系统变量。请注意，这将重置所有系统变量到它们的初始状态，因此请谨慎使用。

代码结构及示例：
```
[clearsysvar]
```
  
### <a id="trace"></a> **[trace] 向控制台输出值**

该标签用于向浏览器的控制台输出指定的变量值，前提是该变量存在且被赋值，同时控制台是打开的。这对于调试和检查变量的值非常有用。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|exp|要输出的变量名|

代码结构及示例：
```
[trace exp="f.akane_like"]
```
  
### <a id="iscript"></a> **[iscript] 编写JavaScript脚本**

该标签允许在TyranoScript中直接编写JavaScript代码。您可以在标签内编写任意的JavaScript代码，这些代码将在执行到该标签时被执行。

代码结构及示例：
```
[iscript]
// 这里是JavaScript代码
console.log("Hello, TyranoScript!");
[endscript]
```
  
### <a id="endscript"></a> **[endscript] 结束JavaScript编写**

该标签用于标记JavaScript代码块的结束。与[iscript]标签配合使用，确保JavaScript代码块的正确结束。

代码结构及示例：
```
[endscript]
```
  
### <a id="emb"></a> **[emb] 内嵌表达式**

该标签的作用是允许在TyranoScript的文本中直接嵌入JavaScript表达式，并将其结果显示在文本中。这对于动态生成文本内容非常有用。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|exp|要嵌入的JavaScript表达式。表达式的结果将被转换为字符串并显示在文本中||〇|

代码结构及示例：
```
[emb exp="f.akane_like"]
```
  
### <a id="preload"></a> **[preload] 预加载数据**

该标签用于预先加载一些资源（如图像、音频等），以便在需要使用这些资源时能够更快地加载和显示。预加载可以提高游戏的性能和用户体验。

在V515版本之后，预加载的资源会自动清除，以释放内存。如果需要保留预加载的资源，可以使用属性single_use="false"来指定该资源不被自动清除。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|storage|指定要预加载的资源的路径。路径应从data目录开始||〇|
|wait|指定是否在预加载完成之前等待。设置为true时，游戏将暂停，直到预加载完成。如果您将其设置为“true”，建议在屏幕上显示“正在加载”或类似的文字，以告知玩家游戏正在加载资源|false|
|single_use|指定预加载的资源是否在使用后自动清除。设置为true时，资源在使用后会被自动清除以释放内存；设置为false时，资源将被保留，直到使用[unload]标签来清除它们|true|
|name|此参数仅在预加载音频文件时适用。您可以指定诸如“bgm”、“se”或“section1”这样的组名（可以指定多个名称，用逗号分隔），以便在使用[unload]标签清除数据时将它们作为一个组进行管理|

代码结构及示例：
```
```

### <a id="wait_preload"></a> **[wait_preload] 等待数据预加载完成**

该标签用于等待预加载完成。这看似与[preload]的wait属性相似，但它们之间存在一些区别。[wait_preload]标签会等待所有预加载的数据加载完成，允许多个[preload]标签同时运行，而不仅仅是特定的预加载项。这对于确保游戏在继续之前已经准备好所有必要的资源非常有用。

代码结构及示例：
```
; Load multiple images with preload and wait=false
[preload storage="data/fgimage/girl.jpg" wait="false"]
[preload storage="data/fgimage/haruko.jpg" wait="false"]
; Perform a different animation while loading
[quake2 time="1000" wait="true"]
; If preloading is not yet complete, wait until it finishes
[wait_preload]
```
  
### <a id="unload"></a> **[unload] 删除预加载的音频数据**

当使用属性single_use="false"预加载大量音频文件时，预加载的音频可能会占用过多内存，从而影响性能。[unload]可用于显式丢弃预加载的音频数据。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|storage|指定要卸载的预加载音频的路径。路径应与预加载时使用的路径相匹配|
|name|使用[preload]中指定的名称来统一丢弃预加载的音频数据|
|all_sound|如果设置为true，将丢弃所有预加载的音频数据|false|

代码结构及示例：
```
[unload storage="data/sound/bgm.mp3" name="bgm" all_sound="false"]
```
  
### <a id="plugin"></a> **[plugin] 加载外部插件**

该标签用于加载外部插件，以扩展TyranoScript的功能。插件可以是JavaScript文件，也可以是其他类型的资源，具体取决于插件的设计。

插件应放在data/others/plugin目录下。

该标签允许自由定义该标签的属性，以便插件开发者可以根据需要传递参数。这允许传递可在插件内自定义的变量，例如宏变量mp.my_color。要动态使用这些参数，可以使用"&mp.my_color"来引用它们。但是，与宏不同，不能使用"%my_color"这种格式。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|name|设定要加载的插件名称||〇|
|storage|该属性可以指定插件的初始剧本。这个属性用于确定从哪个剧本开始执行|init.ks|

代码结构及示例：
```
[plugin name="example_plugin" storage="init.ks" mp.my_color="red"]
```
  
### <a id="loadcss"></a> **[loadcss] 导入使用CSS文件**

该标签用于加载外部CSS文件，以便在TyranoScript中使用其中定义的样式。通过加载CSS文件，您可以自定义游戏的外观。

属性：
|变量名|解释|默认值|必需|
|-|-|-|-|
|file|设定要加载的CSS文件。路径应该从data目录开始||〇|

代码结构及示例：
```
[loadcss file="./data/others/css/mystyle.css" ]
```
