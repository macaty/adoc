[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# 使用拆分控件( splitter )

## 使用拆分条控件的要点

1. 使用控件�?split 函数拆分多个控件�?
   例如:


   ```aardio aardio
   winform.splitter1.split( winform.edit1,winform.edit2 )

   ```


   参数也可以是控件数组，每个控件数组必须包含位于拆分条同一侧的控件�?
   例如:


   ```aardio aardio
   winform.splitter1.split( winform.edit1,{ winform.edit2,winform.edit22} )

   ```

2. 在调整窗口大小时，拆分条会负责让被拆分的控件吸附在自己的两侧�?
   但是被拆分控件以及拆分条本身的其他固定边距属性、自适应大小属性应当自行根据需要设置�?

## 使用拆分条控件的具体步骤

首先，在窗体上放三个文本框�?
窗体样式是“resizeable�?就是可以拖动窗体边框改变窗体大小�?
现在我们的需求是：窗体变大时，第一个文本框大小不变( edit1 )，第二个文本�? edit2 )，第三个文本�? edit3 )会自动放大�?
首先，我们在 edit1 �?edit2 控件之间放一�?splittter1控件�?控件属性中设为水平拆分 �?
�?edit2 �?edit3 控件之间放一�?splittter2 控件�?控件属性中设为水平拆分 �?
然后�?CTRL+ U  切换到代码视图添加代码如下：

```aardio aardio
winform.splitter1.split( winform.edit1,winform.edit2 )
winform.splitter2.split( winform.edit2,winform.edit3 )

```

split函数指定拆分控件管理的是哪两个控件，控件的参数顺序随意，该函数会自动识别出前后控件�?
split 函数的参数也可以指定多含多个控件的数组，数组中必须包含位于拆分条同一侧的控件，例如：

```aardio aardio
winform.splitter1.split( winform.edit1,{winform.edit2,winform.edit22,winform.edit23} )

```

�?CTRL+ U 切换到窗体设计器，所有控件设置固定边距属性，

固定左边�?固定右边距为true�?
这样在窗体放大时可以保持宽度�?
edit1 控件就不用管了，我们不希望他的宽度会变化�?
然后 edit2控件，我们设置他的『自适应大小 / 高度』属性是可变的（设属性值为 true ）�?
至于 edit3 控件，我们直接设置他的控件属性『固定底边距』为 true�?
最后我们需要设置文本框的最小尺寸，�?CTRL+ U 切换到代码视图添加代码如下：

```aardio aardio
winform.splitter1.ltMin = 20;
winform.splitter1.rbMin = 30;
winform.splitter2.ltMin = 40;
winform.splitter2.rbMin = 50;

```

ltMin 中的 lt �?left,top 的缩写，代表左边或上面的控件�?
rbMin 中的 rb �?right,bottom 的缩写，代表右边或下面的控件�?
以上完整程序�?aardio 代码如下�?
```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="使用拆分控件";right=406;bottom=396)
winform.add(
edit1={cls="edit";text="edit1";left=23;top=12;right=382;bottom=65;dl=1;dr=1;edge=1;multiline=1;z=1};
edit2={cls="edit";text="edit2";left=23;top=72;right=382;bottom=176;ah=1;dl=1;dr=1;edge=1;multiline=1;z=2};
edit3={cls="edit";text="edit3";left=23;top=185;right=382;bottom=382;db=1;dl=1;dr=1;edge=1;multiline=1;z=3};
splitter1={cls="splitter";left=23;top=66;right=382;bottom=71;dl=1;dr=1;horz=1;z=4};
splitter2={cls="splitter";left=23;top=178;right=382;bottom=183;dl=1;dr=1;horz=1;z=5}
)
/*}}*/

winform.splitter1.split( winform.edit1,winform.edit2 )
winform.splitter2.split( winform.edit2,winform.edit3 )

winform.splitter1.ltMin = 20;
winform.splitter1.rbMin = 30;
winform.splitter2.ltMin = 40;
winform.splitter2.rbMin = 50;

winform.show()
win.loopMessage();

```

请将上面的源代码复制�?aardio 编辑器中�?
然后，请按【F5】功能键运行代码，试试拖动窗体的边框，注意文本框的变化�?
## 用多个拆分条拆分多组控件示例

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="使用拆分�?splitter)控件在窗口上拆分多个控件";right=801;bottom=486)
winform.add(
edit1={cls="edit";text="edit1";left=4;top=8;right=204;bottom=194;db=1;dl=1;dt=1;edge=1;multiline=1;z=1};
edit2={cls="edit";text="edit2";left=4;top=205;right=204;bottom=475;db=1;dl=1;dt=1;edge=1;multiline=1;z=4};
edit3={cls="edit";text="edit3";left=214;top=8;right=791;bottom=475;db=1;dl=1;dr=1;dt=1;z=3};
splitterHorz={cls="splitter";left=5;top=197;right=204;bottom=202;dl=1;frame=1;horz=1;z=5};
splitterVert={cls="splitter";left=204;top=8;right=212;bottom=475;db=1;dl=1;dt=1;frame=1;z=2}
)
/*}}*/

//指定需要拆分的控件（拖动拆分条可改变被拆分控件的大小）
winform.splitterHorz.split(winform.edit1,winform.edit2);

//指定需要拆分的控件，参数也可以指定包含多个控件的数�?winform.splitterVert.split( {
    winform.edit1,winform.edit2 //数组中的控件须位于拆分条同一�?    },winform.edit3 )

winform.splitterVert.ltMin = 20; //左边控件最小宽�?winform.splitterVert.rbMin = 500; //右边控件最小宽�?
winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/ctrl/splitter.md)

