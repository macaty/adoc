[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# CSS-script 脚本

## CSS-script 入门概述

CSS-script （又�?`CSSS!`）是 [HTMLayout](_.html) 在标�?CSS 语法基础上扩展的一种简单脚本语言，以实现一些简单的交互行为�?CSS-script 基于标准CSS语法，通常是以一个属性名称（该名称以惊叹号结�?标明触发的事件，以逗号分隔语句（可不是一般编程语言中使用的分号哦），而以分号结束语句块（不是大括号哦），这些非常规的规则为是了遵守CSS语法规范�?
让我们看看下面这�?CSS-script 脚本:

```css css
.item {
      hover-on! :
            ele = $1( input.url ) ,
            ele:empty == true ?
                  (self.value = "empty") #
                  (self.value = "filled"),
            ele:hover = true,
            self::width = ele.box-content-width(),
            self.$(.icon) -> @(ele) ele::background-color = rgb(255,0,0)
      ;
}

```

它（CSS-script）的格式看起来就像是个扩展的 CSS 属性一�?

## CSS-script 脚本语法规则

### 基本规则

- CSS-script 语句使用逗号","作为语句结束�?
- CSS-script 使用分号结束语法块�?- CSS-script 中的字符串只能双引号标识, 不能使用单引�?"string").
- CSS-script 中使用关键字 self 表示当前对象.

CSS-script 嵌入标准 CSS 并遵守CSS语法规则,受限�?CSS 语法，脚本并不使用分号分隔语句，也不会使用大括号表示语句块，而是使用逗号分隔语句，使用分号结束语法块�?
### CSS-script 标志�?
标志符可以使用英文字�? `-`, `_` 或�?`$` 符号,在这些后面可以附加数字，

注意CSS允许横线作为标志符的一部分，这与其他编程语言不同，如果你需要用横线表示操作符，例如负号，那么清添加空格以区别�?
### CSS-script 关键�?
CSS-script 支持下面的关键字

`true` `false` `null` `self`

true 表示逻辑真，false 表示逻辑否，null 表示空值，

�?self 表示自身，这里的 self 可不�?aardio 中表示当前名字空间的 self 对象�?
实际上他更像 aardio 中表示自身的 this 或�?owner 对象。在 CSS-script 脚本中，

self 指当前触发事件的节点（类�?javascript 中的 this 对象)

### CSS-script 操作�?
`<` `>` `<=` `==` `!=` `>=` `&&` `||+` `-` `\*` `/` `%` `^` `|` `&`

### CSS-script 三元操作�?
这个语法的作用类似条件判断语�?

也有点像 aardio 中的三元操作符（区别是在CSS-script中使�?`#` 号，而不是类�?aardio �?C++ 中的冒号，当然原因也很简单，冒号�?CSS 语法占用�?)

CSS-script 示例�?
`self:value > 12 ?( self:current = true, self.scroll-to-view());`

上面这句代码是指，如果当前节点的值大�?2，那么选中当前节点( 改变current状�?，并且滚动到视图范围�?
### CSS-script 数据类型

CSS-script 变量用到的类型如下：

null - 空�?

boolean 逻辑值，两个可选�?true �?false;

integer - 32位整数�?

float - 64bit浮点�?实际上这里指的是aardio或C++中的double类型);

string - UNICODE 字符�?

object - DOM节点对象(引用);

object-set - DOM节点对象的集合，函数 $() 返回这样的类�?

function-reference - CSS-script中定义的函数

### CSS-script 字面�?
支持整数，浮点小数，文本, 长度单位，以及正则表达式等字面量 :

1. 整数格式 -\> `[0-9]+ | '0x' [0-9A-Fa-f]+ | ''' character ''' | key-code-literal`

2. 浮点数格�?-\> `[0-9]+ '.' [0-9]+浮点数格�?-> [0-9]+ '.' 'e'|'E'`

3. 文本字面�?-\> `'"' [.]* '"'`

4. 正则字面�?-\> `'/' ['/ig'] ';'`

5. 长度字面�?-\> `| immediately followed by one of: 'pt' | 'px' | 'pc' | '%' | 'em' | 'ex' | 'in' | 'cm' | 'mm'`


数值支�?`0x` 前缀表示的十六进制数值，也可以在数值前使用正负号。而文本需要放在双引号中。正则字面量则与 JavaScrip 类似，至于长度大小等可以使用px(像素) pt(�?等单位，与CSS相同�?
### CSS-script 键盘代码字面�?
键盘代码放在单引号中，可以是单个英文字母，也可以是下面的值：

`'RETURN' | 'LEFT' | 'RIGHT' | 'UP' | 'DOWN' | 'PRIOR' | 'NEXT' | 'TAB' | 'HOME' | 'END' | 'DELETE' | 'INSERT' | 'BACK'`

如果按下组合键，例如 `Ctrl+X` 则在键名前加�?`^`.

字面量使用示�?

`34` \- 表示普通整�?
`0xAFED1234` \- 表示十六进制整数

`1.52` \- 表示浮点�?
`1.e2` \- 表示浮点�?
`1.e-2` \- 浮点�?Hello world!" - 字符�?
`12pt`\- 表示12象素.

`'A'` \- 表示A的键盘代码，实际是一个数�?
使用键盘代码的示例：

```css css
key-on!:  key-code() == '^A'? ... # // Ctrl+A 组合�?      key-code() == '^NEXT'? ... ; // Ctrl+PgDown 组合�?
```

### CSS-script 注释语法

注释语句被忽略不会被编译，类似aardio的注释语法有两种格式:

单行注释以斜杠开�?

`// <text-no-crlf> end-of-line`

块注释（可包含换行）语法也类�?aardio:

`/* <text> */`

### CSS-script 语句

CSS-script 脚本使用逗号 `,` 分隔语句�?
语句块以分号 ';'.结束 ，下面是支持的语法规�?

1. 赋值语�?

   `<左�? '=' <表达�?`

2. 变量声明:

   `<变量�? <b>'='</b> <表达�?`

3. 语句�?
   语句块是一系列使用逗号分隔的语句，语法规则如下�?
   `'('  <expression> [, <expression>]*  ')'`

4. CSS-script 条件语句

   语法规则:

   `<logical-expresion> '?' <when-true-expression> [ '#'  <when-false-expression> ]`

   CSS-script 的条件判断语句格式很简�?


   类似 Javascript或aardio�?�?三元操作�?�?? �?: �?组合，区别是�?号代替了冒号:

   `判断条件 ? (条件为真时的操作)`

   或�?

   `判断条件 ? (条件为真时的操作)`

5. CSS-script 循环

   不支持循环，但是函数可以支持尾递归调用.

6. CSS-script Return 语句

   return 语句用在函数中返回一个�?

   return

7. CSS-script For each, 枚举语句

   语法规则如下�?
   `<object-set> '->'  <reference-to-function-with-single-parameter>`

   枚举通常被用于处理元素集�?格式如下:

   `集合 -> @(参数�? 操作语句`

   aardio中类似的遍历集合的代码如下：

   `for 局部变量名 in 集合{ }`

   范例:


   ```css css
   input.number {
       value-changed! :
         total = 0,
         $(input.number) -> @(el) total = total + el:value,
         $1(td#total):value = total;
     }

   ```


   上面代码的解�? 设页面上有一个HTML节点 `<input class="number">` 在它的值发生改变量触发下面的操�?

   - 定义一个变�?total 并且初始化他的值为 0,

   - 定义一个函�?`@(el) total = total + el:value`,

   - 枚举所有匹配CSS选择�?`input.number` 的节点，并执�?`->` 操作符后面指定的函数,

   - �?total 的值赋于第一个匹配CSS选择�?`td#total` 的节�?
### CSS-script 访问 DOM 节点的属性、状态值、CSS 样式

1. 可以使用成员操作符圆点访问节点的属�?

例如对于当前节点:  有下面的脚本代码:

t = self.type

将会获取节点的type属性并赋值给变量 t.

1. 节点的状态使用单个冒�?`:` 作为成员操作�?

支持的CSS状态例�? `:hover`, `:active`, `:link`, `:checked`, `:current` 等等�?
�?CSS-script 中有如下状态可在执行时使用:

**状�?*

**说明**

ele:value

元素DOM节点对象的�? **注意在CSS-script�?value 是作为一个状态值来访问，不是属性值，是以不能写为 ele.value, 而应当改用冒号写�?ele:value** ), 对于输入框这个值为输入的文�? 其他元素为内部的文本.

ele:index

元素在子元素的序�? 取值从 1 开始到 self.parent().children()

ele:hover

ele:active

ele:empty

ele:readonly

ele:disabled

ele:focusable

部分CSS-script中常用的布尔型状�? (true/false)

1. CSS 属性使用两个冒�?`::` 作为成员操作�?:


下面是一个范例，在定时器中逐渐的将对象改变为透明状态�?
```css css
self::opacity = self::opacity + 0.1 #
return cancel;

```

### Self 对象

�?CSS-script 脚本事件中表示当前节�?
### Cancel

这个关键字是专用�?return 语句，以终止事件继续传�?

### CSS-script 函数

1. 定义函数

对于一般的函数, 定义的格式如�?

```css css
foo = @( a, b ) c = a + b, return c

```

aardio 中类似的定义函数的代码如下：

```aardio aardio
foo = function( a, b ) {
    c = a + b; return c;
}

```

CSS-script 也支持匿名函数定义�?
1. 调用函数

CSS-script 脚本调用函数比较简�?下面的脚本调用函数foo()，传入参�?,2，并将返回值赋值给变量bar:

```css css
bar = foo(1,2)

```

## CSS-script 脚本常用函数

### �?CSS-script 中获�?HTML 页面元素的所有函数如�?

CSS-script函数

函数说明

$1(.item)

获取匹配 ".item" 的第一个元�?
类似aardio中的wbLayout.queryEle()函数(唯一的区别是在aardio中需要将CSS选择器参数放在引号中 - 即使用字符串包含CSS选择�?

$(.item)

获取所有匹�?".item" 的元�?

类似aardio中的wbLayout.queryEles()函数(在aardio中需要将CSS选择器参数放在引号中 - 即使用字符串包含CSS选择�?

$(.item) 返回的集合可以象单个元素一样直接使�?例如:

$(.item).属�?= �?

返回值也可以用于枚举, 例如: $(.item)->ele(ele) ele.属�?= �?

ele.$1(.item)

获取ele子元素中匹配".item"的第一个元�?
ele.$(.item)

获取ele子元素中匹配".item"的所有元�?
类似aardio中的ele.queryElements()函数

ele.$1p(.item)

获取父元素中匹配".item"的最近的一个元�?

类似aardio中的ele.queryParent()函数

ele.$p(.item)

获取父元素中所有匹�?.item"的元�?

ele.parent()

获取父元�?
ele.next()

获取同级的下一个元�?
ele.previous()

获取同级的上一个元�?
ele.child(3)

ele.children()

获取�?个子元素. 参数范围 1 �?ele.children().

可以通过 ele.children() 获取子元素的数目.

CSS 选择器参数中可以使用变量(包含在尖括号�?, 示例:

```css css
ncol = 2, $( table td:nth-child(< ncol >)).some-attr = "hi!";

```

上面�?CSS-script 脚本对所有符合CSS选择�?`table td:nth-child(2)` 规则的节点改变属�?`some-attr` 的值为 `"hi!"`

### CSS-script 脚本其他全局函数

- int(val)- 转换一个值为整数r;
- float(val)- 转换一个值为浮点数，类似aardio中的tonumber;
- length(val) - 转换一个值为长度值（包含单位);
- min(val1, val2 ... valN)- 返回最小数;
- max(val1, val2 ... valN)-返回最大数;
- limit(val, minval, maxval) - 返回一个值是并限定允许的最小或最大�?

### CSS-script 脚本 String 字符串对象的一些成员函�?
- string.length - 取字符串长度
- string.toUpper() - 将字符串转为大写;
- string.toLower() - 将字符串转为小写
- string.slicestr(start\[, length = -1\]) - 截取字符串，参数一指定开始位置，参数二指定长度，如果小于零，则截取到尾部�?

### CSS-script 脚本 HTML 节点对象提供的一些内置函�?
ele.children() - 返回子节点数�?
ele.child(n:integer) - 返回指定子节�?参数为索�?
ele.next() -返回下一个兄弟节�?
ele.previous() -返回上一个兄北节�?
ele.parent() - 返回父节�?
ele.text-width("string") - 计算当前节点在当前样式下显式指定文本所需的像素宽�?

ele.min-intrinsic-width(), ele.max-intrinsic-width() - 节点最�?最大内容宽�?
ele.min-intrinsic-height(), ele.max-intrinsic-height() - 节点最�?最大内容高�?
ele.system-scrollbar-width(),ele.system-scrollbar-height() - 系统设定的滚动条宽度,高度

ele.system-border-width() - 系统设定的边框宽�?
ele.system-small-icon-width(),ele.system-small-icon-height() - 系统设定的小图标宽度,高度

ele.foreground-image-width(),ele.foreground-image-height() - 当前节点的前景图片高�?高度

ele.background-image-width(),ele.background-image-height() - 当前节点的背景图片高�?宽度

ele.box-type-what() 返回节点位置大小等相关参�?

其中type必须被替换为以下名字之一�?\- margin - margin box (节点包含外边距空�?

\- border - border box(节点包含边框空间);

\- padding - padding box (节点包含内边距空�?;

\- content - content box (节点内容空间).

\- inner - inner box(节点内部空间);

\- what part of the name is one of:

what必须被替换为以下名字之一�?\- left - 左边�?

\- right - 右边�?

\- top - 顶边�?
\- bottom - 底边�?

\- width - 宽度;

\- height - 高度;

例如 `self.box-border-width()` 返回包含节点包含边宽的宽度�?
ele.x-parent() 获取相对父节点的x坐标;

ele.x-root() 获取相对HTML根节点的x坐标

ele.x-view() 获取相对当前窗口的x坐标

ele.x-screen() 获取相对屏幕的x坐标

ele.y-parent() 获取相对父节点的y坐标;

ele.y-root() 获取相对HTML根节点的y坐标

ele.y-view() 获取相对当前窗口的y坐标

ele.y-screen() 获取相对屏幕的y坐标

ele.scroll-to-view() 滚动节点到当前视�?
ele.start-animation(duration)

开始执行动�?该函数触�?animation-start! animation-step! animation-end!等事件，

duration 参数指定动画持续时间�?例如�?self.start-animation(0.4s) 启动动画 - 持续时间�?00ms(毫秒)

ele.stop-animation()

停止执行动画。最好不要同时启动多个动画效果，停止当前动画再启动效的动画�?
ele.start-timer(period:integer)

启动定时器，参数指定时间间隔，以毫秒为单位，该函数触�?timer! 事件，在该事件中调用return cancel取消定时器，

也可以调�?stop-timer() 函数取消定时器�?
ele.stop-timer()

取消定时�?
注意 CSS-script 脚本中使用横线作为标志符的一部分是合法的,

这在其他编程语言,以及aardio里是行不通的. 请注意区�?

## CSS-script 触发事件(Active CSS attributes)

在前面的示例中，hover-on! 是我们的脚本要处理的事件标识.
当具�?.item 类的元素被鼠标悬停时, 会触发此事件并执行里面的代码.

下面�?CSS-script 完整的事件支持列�?

- `hover-on!`

  鼠标悬停在节点上触发，类似aardio中的 wbLayout.onMouseEnter 事件

- `hover-off!`

  鼠标离开节点时触发，类似aardio中的 wbLayout. onMouseLeave 事件

- `active-on!`

  鼠标按下时触发，类似aardio中的 wbLayout.onMouseDown 事件

- `active-off!`

  鼠标抬起时触�? 类似aardio中的 wbLayout.onMouseUp 事件

- `focus-on!`

  获得输入焦点时触�?

- `focus-off!`

  失去输入焦点时触�?

- `key-on!`�?`key-off!`

  键盘的按键按�?抬起时触发，通过 key-code() 函数获取按键信息.
  key-code() 获得的按键信息可能是一个用单引号包含的有效字符('a', '4', '$')或是下列预定义值之一:
  'RETURN', 'LEFT', 'RIGHT', 'UP', 'DOWN', 'PRIOR', 'NEXT', 'TAB', 'HOME', 'END', 'DELETE', 'INSERT', 'BACK'

- `click!`�?`double-click!`

  鼠标单击，或双击时触发，必须绑定了所有允许接收单击，或双击事件的behavior，储�?button , hyperlink 等等。其他节点一般不会触发这两个事件（这些节点也可通过在CSS中指�?behavior:clickable; 启用该事件） �?
- `animation-start!`�?`animation-step!`�?`animation-end!`

  动画控制事件animation-start! 在调用了元素�?element.start-animation() 方法后触�?animation-step! 事件处理的最后必须返回一个整�?下次执行的间隔毫秒数). 例如: return 500;

- `timer!`

  定时触发器，配合 start-timer(ms) �?stop-timer() 函数使用.start-timer(ms) 中的参数单位为毫�?

- `size-changed!`

  元素大小发生改变时触�?
- `value-changed!`

  input 类控件的值发生变时时触发

- `assigned!`

  这个属性很有意思，就是在你�?CSS �?`assigned!` 这个属性赋值时触发�?  换句话说，其实就是你写在这后面的脚本作为CSS属性被应用到节点时触发，而不是等待用户的什么交互。这个事件的作用类似于在behavior 里的 onAttach 事件�?

## �?aardio 中使�?CSS-script 脚本

aardio 调用 HTMLayout 并使�?CSS-script 脚本�?aardio 代码示例�?
```aardio aardio
import win.ui;
var winform = ..win.form( text="CSS-script 脚本示例" )
winform.add()

import web.layout; //首先导入HTMLayout支持�?var wbLayout = web.layout(winform); //创建HTMLayout窗体

wbLayout.html = /*********
<html>
<head>
  <style>

  //下面的选择符表示拥�?autofocus属性的节点，并且状态为可以获取焦点(focusable)
  [autofocus]:focusable {
    assigned!: self:focus = true; //assigned!事件表示加载脚本即时执行
  }
  </style>
<head>
<body>
  在页面加载以后，第二个文本框自动得到焦点:<br/>
  <input type="text" value="测试文本�? /><br/>
  <input type="text" value="看我自动得到焦点�? autofocus />
</body>
</html>
*********/

winform.show()
win.loopMessage();

```

## �?aardio 中调�?HTMLayout 与响�?CSS-script 事件

假设�?HTMLayout 打开的网页有一�?HTML 节点内容是这样：

```html html
<label for="id">

```

那么我们可能如下编写 CSS，下面的 CSS 选择�?`[for]` 匹配所有指定了 for 属性的节点，在 CSS 选择器中，中括号内问指定 HTML 属性�?
```css css
   [for] {
     hover-on!  : $1(#< self.for >):hover = true;
     hover-off! : $1(#< self.for >):hover = false;
     active-on! : $1(#< self.for >):focus = true;
     cursor:pointer;
   }
   input:hover {
     outline: 4px glow blue 1px;
   }

```

在上面的代码中，鼠标悬停或离开节点导致节点 for 属性绑定的节点同步改变 `:hover` 状态。而点�?lable 节点�?`for` 属性绑定的节点将获得输入焦点�?
下面是用 aardio 编写的完整范例：

```aardio aardio
import win.ui;
var winform = win.form( bottom=399;text="响应 CSS-script 事件";right=599 )

import web.layout;
wbLayout = web.layout(winform)

wbLayout.html = /**
<input type="text" />

<input type="text" id="myText" value="" />
<label for="myText" >鼠标放到这里，并点击这里</lable>
**/

wbLayout.css = /**
[for]
   {
     hover-on!: $1(#< self.for >):hover = true;
     hover-off!: $1(#< self.for >):hover = false;
     active-on!: $1(#< self.for >):focus = true ;
     cursor:pointer;
   }
   input:hover {
     outline: 4px glow blue 1px;
   }
**/

winform.show();
win.loopMessage();

```

下面是另一�?aardio 编写的示例：

```aardio aardio
import win.ui;
var winform = ..win.form( text="HTMLayout - CSS-script 脚本事件触发例子" )

import web.layout;
var wbLayout = web.layout(winform);

wbLayout.html = /*********
<html>
  <head>
    <style>
      p#test {
        border:1px solid black; //定义边框
        width: 30%; //定义宽度
        hover-on!: self.start-timer(400); //鼠标悬停�?开始定时器,间隔400毫秒
        hover-off!: self.stop-timer(),
                    $1(popup#for-test):popup = false ; //注意冒号作为成员操作符时改变节点的状�?
         //注意下面用到了条件语�?问号前面是条�?        timer!: self:hover ? self.show-popup($1(popup#for-test),3,9), /*参数表示在右下角弹出提示 */
                return cancel;//阻止事件继续传�?      }

      popup#for-test  {
        margin-top:10px; /*指定顶边�?*/
      }

    </style>
  </head>
<body>
  自定义提�?  <p #test>请将鼠标放在这里</p>

  <popup #for-test>
    哈哈,你成功了
  </popup>

</body>
</html>

*********/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/web/layout/css-script.md)

