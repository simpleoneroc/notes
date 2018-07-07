# notes
概述
==


**什么是HTML？**


-- `超文本标记语言` (Hyper Text Markup Language) /br
-- 不是一种编程语言，而是一种`标记语言` (markup language)
-- 标记语言是一套标记标签 (markup tag)
-- HTML 使用标记标签来描述网页
[什么是超文本？](http://www.w3school.com.cn/tags/tag_term_hypertext.asp)

**HTML 文档 = 网页**
-- HTML 文档描述网页
-- HTML 文档包含 HTML 标签和纯文本
-- HTML 文档也被称为网页
* `Web 浏览器的作用是读取 HTML 文档，并以网页的形式显示出它们。浏览器不会显示 HTML 标签，而是使用标签来解释页面的内容`

**HTML标签和HTML元素的区别**

-- HTML 标记标签通常被称为 HTML 标签 (HTML tag)，由尖括号包围的关键词，比如 `<html>`
-- HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码

![这里写图片描述](https://img-blog.csdn.net/20180630194146987?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
-- 属性：形态；存在方式；基本信息
-- 标签是不同的种族，每个种族有自己的天赋和不同的时装


----------








替换和不可替换元素
=========

从元素本身的特点来讲，可以分为`替换和不可替换元素`。
例如浏览器会根据<img>标签的src属性的值来读取图片信息并显示出来，而如果查看(X)HTML代码，则看不到图片的实际内容；又例如根据<input>标签的type属性来决定是显示输入框，还是单选按钮等。

(X)HTML中的`<img>、<input>、<textarea>、<select>、<object>`都是都是替换元素。这些元素往往没有实际的内容，即是一个空元素。

*`替换元素一般有内在尺寸，所以具有width和height，可以设定`。例如例如你不指定img的width和height时，就按其内在尺寸显示，也就是图片被保存的时候的宽度和高度。
对于表单元素，浏览器也有默认的样式，包括宽度和高度。

----------


行级元素，块级元素，行级块元素
===============

**行级元素（inline）【内联元素/行内元素】**

- `设置宽高无效`内联元素的宽高随元素的内容而变化，能够影响它宽高的为其本身的内容。
 - 行级元素`绝对定位`后可以设置width和height，这是由于display,position和float属性都能影响元素的显示及其位置，它们之间会相互影响。此处display在内联元素绝对定位后被重新计算，也就是说`内联元素绝对定位后变成了块级元素`。
  - `行内替换元素`一般有内在尺寸（替换元素比较特殊），所以具有width和height，可以设定。
- `设置margin和padding水平方向上有效`
- `设置margin在垂直方向上无效`，设置padding相当于改变背景`在显示效果上是改变的`，实际上是不变的，`对周围元素没有影响`
- `不会自动进行换行` 
- 常见的行内元素有：a , br , i , img , input , span , sub , sup


**块级元素（block）**

 - `能够设置宽高`
 - `margin和padding的上下左右均对其有效` 
 - `可以自动换行` 
 - 多个块状元素标签写在一起，默认排列方式为从上至下
 - 常见的块级元素有：address , div , form , h1, hr , ol , p , table , ul , li

**行级块元素（inline-block）**

 - `不能自动换行` 
 - `能够识别宽高` 
 - `默认排列方式为从左到右`

**通过 `display：inline / block / inline-block`转换**
[更多内容](https://blog.csdn.net/Ultranana/article/details/61423879 "更过内容")

**空元素(void)**
`没有内容的 HTML 元素被称为空元素。`空元素是在开始标签中关闭的。

```
 <br><hr> <img> <input> <link><meta>
```

----------
![这里写图片描述](https://img-blog.csdn.net/20180630205810903?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

![这里写图片描述](https://img-blog.csdn.net/20180630205949190?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

[原文链接](https://segmentfault.com/q/1010000004479084)


----------



`<!DOCTYPE>`
============

 1. 声明必须是 HTML 文档的第一行，位于 `<html>` 标签之前
 2. 指示 web 浏览器关于页面使用哪个 `HTML 版本进行编写`的指令。
 3. `<!DOCTYPE html>`使浏览器识别成H5文档
 4. 标准模式和怪异模式：
   - **`标准模式（Standards Mode）`**：浏览器按W3C标准解析执行代码 。
   - **`怪异模式（Quirks Mode）`**：兼容老页面。使用浏览器自己的方式解析执行代码，因为不同浏览器解析执行的方式不一样，所以我们称之为怪异模式。
   - **`近标准模式`**：与标准模式一致，除了在处理下面这种情况时： 
如果一个块级元素除了空白文本（空格，tab等字符）外再无其它内容，则它的高度按0处理；如果有子元素，则它的高度不能比子元素大，无论它的font-size多大。
- **`标准模式与怪异模式的区别`** ：
1） **`盒模型`**： IE下标准模式为标准w3c盒模型【content+padding+border+margin】，怪异模式为IE盒模型【content+margin：padding与border包含在content宽高中】 
2） **`行内元素的垂直对齐`**：基于 Gecko 的浏览器【Mozilla Firefox、HotBrowser、Mozilla Suite、Camino】标准模式对齐至基线，怪异模式对齐至底部 ；
3） 怪异模式中，IE6/7/8都不认识!important声明 ；
4） 设置行内元素的高宽： 在Standards模式下，给等行内元素设置wdith和height都不会生效，而在quirks模式下，则会生效。 
5） 使用margin:0 auto在standards模式下可以使元素水平居中，但在quirks模式下却会失效。

  [怪异模式（Quirks Mode）对 HTML 页面的影响](https://www.ibm.com/developerworks/cn/web/1310_shatao_quirks/)
[DOCTYPE声明——标准模式与怪异模式的区别](https://blog.csdn.net/Vivian_jay/article/details/61933580)
*

```
SGML(Standard Generalized Markup Language,标准通用标记语言)
是一种定义电子文档结构和描述其内容的国际标准语言，是所有电子文档标记语言的起源。
DTD（文档类型定义）的作用是定义 XML 文档的合法构建模块。
它使用一系列的合法元素来定义文档结构。
```
[DTD拓展](https://www.cnblogs.com/xiongmanli/p/6101899.html)



----------


头部元素`<head>`
============

可以放在头部标签中的元素有：`<meta>，<title>，<base>，<style>，<link>，<script>`。


`<title>`
---------



 1. 定义页面**`标题`**
 2. 收藏夹标题
 3. 搜索结果标题

`<base>`
--------

   标签为页面上的所有链接**`规定默认地址`**或默认目标（target）。

`<link>`
--------

-- **作用**：标签定义文档与外部资源之间的关系。标签最常用于**`连接样式表`**。

```
<link rel="stylesheet" type="text/css" href="theme.css" />
```
-- **属性**：

 1. **`rel`**：规定当前文档与被链接文档之间的关系。值`stylesheet`：文档的外部样式表。只有它得到全部浏览器的支持。
 2. **`href`** ：规定被链接文档的位置（URL）

----------


**`<meta>`**
------------

[meta标签的作用及整理](https://blog.csdn.net/yc123h/article/details/51356143)

**--作用：**提供关于 HTML 文档的**`元数据`**。它不会显示在页面上，但对于**`机器是可读的`**。可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。**`meta里的数据是供机器解读的，告诉机器该如何解析这个页面`**，还有一个用途是可以添加服务器发送到浏览器的http头部内容。

**--属性**：

 1. **`content`**：**`定义与 http-equiv 或 name 属性相关的元信息`**。
当有http-equiv或name属性的时候，一定要有content属性对其进行说明，例如：
 `<meta name="keywords" content="HTML,ASP,PHP,SQL">`
 这里面content里的属性就是对keywords进行的说明，可以理解成一个键值对，就是`{keywords:"HTML,ASP,PHP,SQL"}。`
 
 2. **`http-equiv`**：**`添加http头部内容`**，在浏览器接受文档时加入的处理信息。**`可以说明编码格式，文档格式，执行动作`**。

```
<meta http-equiv="Content-Type" content="text/html; charset=gb2312" />
<meta http-equiv="Refresh" content="5;url=http://www.w3school.com.cn" />
```

![这里写图片描述](https://img-blog.csdn.net/20180701143839118?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
![这里写图片描述](https://img-blog.csdn.net/20180701144127856?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
-- `MIME (Multipurpose Internet Mail Extensions) 是描述消息内容类型的因特网标准。`服务器会将它们发送的多媒体数据的类型告诉浏览器，而通知手段就是说明该多媒体数据的MIME类型，从而让浏览器知道接收到的信息哪些是MP3文件，哪些是Shockwave文件等等。服务器将MIME标志符放入传送的数据中来告诉浏览器使用哪种插件读取相关文件。[MIME 参考手册](http://www.w3school.com.cn/media/media_mimeref.asp)/[MIME是什么](https://zhidao.baidu.com/question/202397287.html)
[meta name="viewport" content="width=device-width,initial-scale=1.0" 解释](https://blog.csdn.net/u012402190/article/details/70172371)
[<meta>标签中http-equiv属性的属性值X-UA-Compatible详解](https://blog.csdn.net/changjiangbuxi/article/details/26054755)
 3. **`name`**：**`供浏览器进行解析，常用于解决兼容性。`**

 `<meta name="renderer" content="webkit">`这个meta标签的意思就是告诉浏览器，用webkit内核进行解析，当然前提是浏览器有webkit内核才可以，不然就是没有意义的啦。当然看到这个你可能会有疑问，这个renderer是从哪里冒出来的，我要怎么知道呢？这个就是在对应的浏览器的开发文档里就会有表明的，例如这个renderer是在360浏览器里说明的。[360浏览器内核控制Meta标签说明文档](http://se.360.cn/v6/help/meta.html)
 4. **`charset`**：**`声名字符集，解决乱码，放于首行。`**

```
<meta charset="utf-8">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
//两种写法都可以
```


----------

表单元素
====

`1---<form>`
--------
-- **作用**：创建表单。
-- **属性**：

 - `action`：规定当提交表单时向何处发送表单数据。`<form action="value">`
 - `autocomplete`：规定表单是否应该启用自动完成功能。`<form autocomplete="on|off">`
 - `method`：规定如何发送表单数据。表单数据可以作为 `URL 变量（method="get"）`或者 `HTTP post （method="post"）`的方式来发送。
 - `enctype`：规定在发送到服务器之前应该如何`对表单数据进行编码`。默认表单数据会编码为 "application/x-www-form-urlencoded"。所有字符都会进行编码（空格转换为 "+" 加号，特殊符号转换为 ASCII HEX 值）。
   -  application/x-www-form-urlencoded	：在发送前编码所有字符（默认）
   - multipart/form-data：不对字符编码。在使用包含文件上传控件的表单时，必须使用该值。  
   - text/plain：空格转换为 "+" 加号，但不对特殊字符编码。
 -  `target`：规定在何处打开 action URL。
   - _blank：在新窗口中打开。
   - _self：默认。在相同的框架中打开。


`2---<input>`
---------

-- **作用**：标签用于搜集用户信息。
-- **属性**：

 - `type`：规定 input 元素的类型。
  - button：`<input type="button" />` 定义可点击的按钮，但没有任何行为。button 类型常用于在用户点击按钮时启动 JavaScript 程序。
  - checkbox：`<input type="checkbox" />` 定义复选框。复选框允许用户在一定数目的选择中选取一个或多个选项。
   - file：`<input type="file" />` 用于文件上传。
   - hidden：`<input type="hidden" />` 定义隐藏字段。隐藏字段对于用户是不可见的。隐藏字段通常会存储一个默认值，它们的值也可以由 JavaScript 进行修改。
   - image：`<input type="image" />` 定义图像形式的提交按钮。必须把 `src` 属性 和 `alt` 属性 与 `<input type="image">` 结合使用。`<input type="image" src="submit.gif" alt="Submit" />`
   - password：`<input type="password" />` 定义密码字段。密码字段中的字符会被掩码（显示为星号或原点）。
   - radio：`<input type="radio" />` 定义单选按钮。单选按钮允许用户选取给定数目的选择中的一个选项。
   - reset：`<input type="reset" />` 定义重置按钮。重置按钮会清除表单中的所有数据。
   - submit：`<input type="submit" />` 定义提交按钮。提交按钮用于向服务器发送表单数据。数据会发送到表单的 `action` 属性中指定的页面。
    - number：
        - `<input type=”number” min=”1” max=”10” step=”10” value=”3” name=”haha”>`
        - 可以配合input的max/min/step/value规定允许输入的最大值/最小值/步长/默认值。
    - range：活动条
     -  `<input type=”range” min=”1” max=”10” step=”1” name=”h”>`
   - text
   - email
   - search
   - url

 - `value` ：value 属性为 input 元素设定值。
   - `type="button", "reset", "submit"` - 定义按钮上的显示的文本 
   - `type="text", "password", "hidden"` - 定义输入字段的初始值
   - `type="checkbox", "radio", "image"` - 定义与输入相关联的值
   - `<input type="checkbox">` 和 `<input type="radio">` 中必须设置 value 属性。
 - `name`：name 属性规定 input 元素的名称。
  - name 属性用于对提交到服务器后的表单数据进行标识，或者在客户端通过 JavaScript 引用表单数据。
   - `只有设置了 name 属性的表单元素才能在提交表单时传递它们的值`。
 - `accept`：accept 属性只能与 `<input type="file">` 配合使用。它规定能够通过文件上传进行提交的文件类型。`请避免使用该属性。应该在服务器端验证文件上传。`
 - `autocomplete`：规定输入字段是否应该启用自动完成功能。
  - `<input autocomplete="on/off">`
 - `autofocus`：文本输入字段被设置为当页面加载时获得焦点。
    - `<input autofocus="autofocus">`
 - `checked`：checked 属性规定在页面加载时应该被预先选定的 input 元素。
  - `<input checked="checked">`

  - checked 属性 与 `<input type="checkbox">` 或 `<input type="radio">` 配合使用。

  - checked 属性也可以在页面加载后，通过 JavaScript 代码进行设置。
 - `disabled`：disabled 属性规定应该禁用 input 元素。
  - `<input disabled="disabled">` 
  - 被禁用的 input 元素既不可用，也不可点击。可以设置 disabled 属性，直到满足某些其他的条件为止（比如选择了一个复选框等等）。然后，就需要通过 JavaScript 来删除 disabled 值，将 input 元素的值切换为可用。
 - `form`：form 属性规定 input 元素所属的一个或多个表单。
  -  `<input form="id">`
  - `form 属性的值必须是其所属表单的 id`。如需引用一个以上的表单，请使用空格分隔的列表。
![这里写图片描述](https://img-blog.csdn.net/20180703171435346?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `formaction`：formaction 属性覆盖 form 元素的 action 属性。
  - `<input formaction="url">`  
  - 该属性适用于 type="submit" 以及 type="image"。
![这里写图片描述](https://img-blog.csdn.net/20180703171703336?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `formmethod`：formmethod 属性覆盖 form 元素的 method 属性。
   -  `<input formmethod="get|post">`
![这里写图片描述](https://img-blog.csdn.net/20180703172044153?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `formnovalidate`：使用该属性，则提交表单时按钮不会执行验证过程。
   - `<input formnovalidate="formnovalidate">` 
 -  `formtarget`：formtarget 属性覆盖 form 元素的 target 属性。
  - `<input formtarget="_blank/_self(default)">` 
 - `list`：list 属性`引用数据列表`，其中包含输入字段的预定义选项。
   - `<input list="datalist_id">`
![这里写图片描述](https://img-blog.csdn.net/20180703173712908?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `min/max`：规定输入字段所允许的最大值最小值。
   - `<input min="number|date" max="number|date">` 
   - max 属性与 min 属性配合使用，可创建合法值范围。
   - 注释：max 和 min 属性适用于以下 `<input>` 类型：number, range, date, datetime, datetime-local, month, time 以及 week。
 - `maxlength`：maxlength 属性规定输入字段的最大长度，以字符个数计。
  - `<input maxlength="value">`  
  - maxlength 属性与 `<input type="text">` 或 `<input type="password">` 配合使用。
 - `pattern`：pattern 属性规定用于验证输入字段的模式（正则表达式）。
  - `<input pattern="regexp">` 
  - pattern 属性适用于以下 `<input>` 类型：text, search, url, telephone, email 以及 password 。
  - 请使用标准的 "title" 属性来描述模式。
 - `required`：required 属性规定必需在提交之前填写输入字段。
   - `<input required="required">`
   ![这里写图片描述](https://img-blog.csdn.net/20180703180214128?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `readonly`：readonly 属性规定输入字段为只读。
  - `<input readonly="readonly">` 
  - 只读字段是不能修改的。不过，用户仍然可以使用 tab 键切换到该字段，还可以选中或拷贝其文本。
  - readonly 属性可以防止用户对值进行修改，直到满足某些条件为止（比如选中了一个复选框）。然后，需要使用 JavaScript 消除 readonly 值，将输入字段切换到可编辑状态。
  - readonly 属性可与 <input type="text"> 或 <input type="password"> 配合使用。
![这里写图片描述](https://img-blog.csdn.net/20180703180032117?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 - `placeholder`：placeholder 属性提供可描述输入字段预期值的提示信息（hint）。
  - `<input placeholder="text">` 
![这里写图片描述](https://img-blog.csdn.net/2018070317565767?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)


`3---<select>`
----------

-- **作用**：select 元素可创建单选或多选菜单。
-- **属性**：

 - `autofocus`：规定在页面加载后文本区域自动获得焦点。
 - `form`：规定文本区域所属的一个或多个表单。

`4---<option>`
----------
-- **作用**：option 元素定义下拉列表中的一个选项（一个条目）。
浏览器将 `<option>` 标签中的内容作为 `<select>` 标签的菜单或是滚动列表中的一个元素显示。option 元素位于 select 元素内部。
-- **属性**：

 - `selected`：规定选项（在首次显示在列表中时）表现为选中状态。
   - `<option selected="selected">` 
 - `value`：value 属性规定在表单被提交时被发送到服务器的值。

   - ！！！`<option>` 与 `<option/>` 之间的值是浏览器显示在下拉列表中的内容，而 value 属性中的值是表单被提交时被发送到服务器的值。

    - 注释：如果没有指定 value 属性，选项的值将设置为 <option> 标签中的内容。

`5---<textarea>`
------------
-- **作用**：定义多行的文本输入控件。
在文本输入区内的文本行间，用 "`%OD%OA`" （回车/换行）进行分隔。
-- **属性**：

 - `autofocus`
 - `form`
 - `maxlength`：规定文本区域的最大字符数。
 - `placeholder`：规定描述文本区域预期值的简短提示。
 - `required`：规定文本区域是必填的。（兼容性）




`6---<label>`
---------
-- 作用：为 input 元素定义标注（标记）。绑定文本与控件。为鼠标用户改进了可用性，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。
-- 属性：

 - `for`：规定 label 绑定到哪个表单元素。

```
<form id="roc">
  <label for="male">Male</label>
  <input type="radio" name="sex" id="male" />
</form>

<label><input type="radio" name="sex" form="roc">male</label>
```

 - `form`：规定 label 字段所属的一个或多个表单。


`7---<button>`
----------
-- **作用**：标签定义一个按钮。
-- **属性**：

 - `type`：规定按钮的类型。
   -  submit：该按钮是提交按钮（除了 Internet Explorer，该值是其他浏览器的默认值）。
   - button：该按钮是可点击的按钮（Internet Explorer 的默认值）。
   - reset： 	该按钮是重置按钮（清除表单数据）。
 - `value`：Internet Explorer 将提交 `<button>` 与 `<button/>` 之间的文本，而其他浏览器将提交 value 属性的内容。
 - `formaction,formmethod,formnovalidate,formtarget`：`type="submit"`时配合使用。
 - `autofocus，form`

`8---<datalist>`
----------------
-- **作用**：定义选项列表。

 - 与 input 元素配合使用该元素，来定义 input 可能的值。
 - datalist 及其选项不会被显示出来，它仅仅是合法的输入值列表。
 - 使用 input 元素的 list 属性来绑定 datalist。

-- **属性**：

----------


*`<button>` 与 `<input type="button">` 区别
----------------------------------------

 - button元素是双标签，其内部可以配置图片与文字，进行更复杂的样式设计
 - button元素禁止使用的元素是图像映射，因为它对鼠标和键盘敏感的动作会干扰表单按钮的行为。
 - 请始终为按钮规定 type 属性。Internet Explorer 的默认类型是 "button"，而其他浏览器中（包括 W3C规范）的默认值是 "submit"。
 - 在form表单内就用`<inputtype=”submit”>`
   在form表单外就用`<button></button>`

     
----------


*GET和POST区别
-----------
GET和POST是HTTP协议中的两种发送请求的方法。
HTTP是基于TCP/IP的关于数据如何在万维网中如何通信的协议。
HTTP的底层是TCP/IP。所以GET和POST的底层也是TCP/IP链接。
两者在本质上没差。
在HTTP协议中，Method和Data是正交的两个概念，也就是说，使用哪个method与应用层的数据如何传送是没有相互关系的。 
HTTP没有要求如果method是POST数据就要放在BODY中。也么有要求如果method是GET,数据参数就一定放在URL中而不能放在BODY中。
只是在HTML标准中这样要求。

```
在我大万维网世界中，TCP就像汽车，我们用TCP来运输数据，
它很可靠，从来不会发生丢件少件的现象。
如果路上跑的全是看起来一模一样的汽车，
那这个世界看起来是一团混乱，送急件的汽车可能被前面满载货物的汽车拦堵在路上，
整个交通系统一定会瘫痪。
为了避免这种情况发生，交通规则HTTP诞生了。
HTTP给汽车运输设定了好几个服务类别，有GET, POST, PUT, DELETE等等，
HTTP规定，当执行GET请求的时候，
要给汽车贴上GET的标签(设置method为GET)，
而且要求把传送的数据放在车顶上(url中)以方便记录。
如果是POST请求，就要在车上贴上POST的标签，并把货物放在车厢里。
当然，你也可以在GET的时候往车厢内偷偷藏点货物，但是这是很不光彩;
也可以在POST的时候在车顶上也放一些数据，让人觉得傻乎乎的。
HTTP只是个行为准则，而TCP才是GET和POST怎么实现的基本。

但是，我们只看到HTTP对GET和POST参数的传送渠道(url还是requrest body)提出了要求。
“标准答案”里关于参数大小的限制又是从哪来的呢?

在我大万维网世界中，还有另一个重要的角色：运输公司。
不同的浏览器(发起http请求)和服务器(接受http请求)就是不同的运输公司。 
虽然理论上，你可以在车顶上无限的堆货物(url中无限加参数)。
但是运输公司可不傻，装货和卸货也是有很大成本的，
他们会限制单次运输量来控制风险，数据量太大对浏览器和服务器都是很大负担。
业界不成文的规定是，(大多数)浏览器通常都会限制url长度在2K个字节，
而(大多数)服务器最多处理64K大小的url。超过的部分，恕不处理。
如果你用GET服务，在request body偷偷藏了数据，
不同服务器的处理方式也是不同的，有些服务器会帮你卸货，读出数据，
有些服务器直接忽略，所以，虽然GET可以带request body，
也不能保证一定能被接收到哦。
```
[99%的人都理解错了HTTP中GET与POST的区别](http://www.techweb.com.cn/network/system/2016-10-11/2407736.shtml)

 - GET - 从指定的资源请求数据。
 - POST - 向指定的资源提交要被处理的数据


![这里写图片描述](https://img-blog.csdn.net/20180701175726372?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
`GET`
-----
-- **格式**：

查询字符串（名称/值对）是在 GET 请求的 `URL 中发送`的：

`/test/demo_form.asp?name1=value1&name2=value2`



`POST`
------
-- **格式**：

查询字符串（名称/值对）是在 POST 请求的 `HTTP 消息主体(request body)中发送`的：


```
POST /test/demo_form.asp HTTP/1.1
Host: w3schools.com
name1=value1&name2=value2
```


![这里写图片描述](https://img-blog.csdn.net/20180701175634104?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
GET在浏览器回退时是无害的，而POST会再次提交请求。 
GET产生的URL地址可以被Bookmark，而POST不可以。
GET请求会被浏览器主动cache，而POST不会，除非手动设置。 
GET请求只能进行url编码，而POST支持多种编码方式。 
GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。 
对参数的数据类型，GET只接受ASCII字符，而POST没有限制。  


**为什么GET有长度限制？**

-- `HTTP协议对HTTP头和BODY都没有长度的要求。而长度的要求来自浏览器和服务器`。
-- `正因为GET请求在URL中传送参数，所以受到浏览器和服务器的制约`。
-- `浏览器通常都会限制url长度在2K个字节，而(大多数)服务器最多处理64K大小的url。`

**为什么GET相对POST会更快？**
[http GET 和 POST 请求的优缺点和误区 --前端优化](https://blog.csdn.net/zzk220106/article/details/78595108/)

-- `GET产生一个TCP数据包;POST产生两个TCP数据包。`
-- `GET会将数据缓存起来，而POST不会。` 
![这里写图片描述](https://img-blog.csdn.net/20180701213650702?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
![这里写图片描述](https://img-blog.csdn.net/20180701213702116?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

1. GET与POST都有自己的语义，不能随便混用。

2. 据研究，在网络环境好的情况下，发一次包的时间和发两次包的时间差别基本可以无视。而在网络环境差的情况下，两次包的TCP在验证数据包完整性上，有非常大的优点。

3. 并不是所有浏览器都会在POST中发送两次包，Firefox就只发送一次。


**为什么POST相对GET会更安全？**

-- `因为GET参数直接暴露在URL上，在地址栏可见，所以不能用来传递敏感信息`。

[HTTP 方法：GET 对比 POST](http://www.w3school.com.cn/tags/html_ref_httpmethods.asp)
[前端：Get 和 Post的区别](https://blog.csdn.net/happy_xiahuixiax/article/details/72859673)

----------

表格元素
====

`<table>`
---------
tr 元素定义表格行，th 元素定义表头，td 元素定义表格单元。
```
<table border="1">
  <tr>
    <th>Month</th>
    <th>Savings</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
</table>
```

----------


常用标签
====



`1---<a>`
-----
-- 作用：定义超链接。
-- 属性：

 - `href`：规定链接指向的页面的 URL。
 - `target`：规定在何处打开链接文档。值`_blank`：在新窗口打开。
![这里写图片描述](https://img-blog.csdn.net/20180701163905855?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbXBsZW9uZV8=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
[测试](http://www.w3school.com.cn/tiy/t.asp?f=html_a_target_framename)

* `重定向：重定向(Redirect)就是通过各种方法将各种网络请求重新定个方向转到其它位置。`


`2---<img>`
-------

`<img>` 标签创建的是被引用图像的占位空间。



`3---<iframe>`
--------------
-- 作用：创建包含另外一个文档的内联框架（即行内框架）。

----------



通用属性
====

 - id
 - class
 - style
 - title：title属性用于显示省略的内容（或补充/提示说明的内容）：当光标移动到元素内容上时显示title里的内容。
 - accesskey:元素快捷键
 - tabindex：元素移动顺序
 - draggable：元素拖动
 - contenteditable:元素是否允许编辑
 - hidden:隐藏元素
 - spellchcheck：元素检查
 - contextmenu:元素快捷菜单
 - data-yourvalue：自定义属性
 - 

