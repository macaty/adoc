[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 AutoCAD - 入门

```aardio aardio
//aardio 调用 AutoCAD - 入门
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用 AutoCAD 入门";right=759;bottom=469)
winform.add(
edit={cls="edit";left=13;top=12;right=746;bottom=453;edge=1;multiline=1;z=1}
)
/*}}*/

//AutoCAD 接口文档: https://help.autodesk.com/view/OARX/2020/ENU/
import com.cad;
var cad = com.cad(); //兼容 32 �?/ 64 �?AutoCAD
if(!cad) return winform.msgboxErr("未安�?AutoCAD");
cad.Visible = true //必须显示 AutoCAD 窗口，不然访问文档对象等可能会出现异�?
if(cad.GetAcadState().IsQuiescent){
    winform.edit.print("AutoCAD 当前是静止状态�?)
}

winform.edit.printf("AutoCAD 主窗口句�?,cad.HWND)

if( cad.Documents.Count > 0 ){
    winform.edit.printf("AutoCAD 当前打开文档数：%d", cad.Documents.Count);
    winform.edit.printf("AutoCAD 活动文档窗口句柄�?x%x",cad.HWND);

    cad.ActiveDocument.ModelSpace.AddText("测试文本",{10;20;30},5);
}

var pt1 = cad.ActiveDocument.Utility.GetPoint(,'\r\n请选择第一�? ')
var pt2 = cad.ActiveDocument.Utility.GetPoint(,'\r\n请选择第二�? ')
cad.ActiveDocument.ModelSpace.AddLine(pt1,pt2);

var selection = cad.ActiveDocument.SelectionSets.Add("Test_SelectionSet");
selection.Select ( cad.acSelectionSetAll,,,com.word({0}),com.Variant({"LINE"}) );

/*******************
注意 aardio 中的数值数组传�?COM 默认�?double 类型数组�?单个数值，整数默认�?32 位整型（int），小数默认�?64 位浮点数�?double ）�?字符串或字符串数组默认为 BSTR 类型�?
AutoCAD 有些数值或数组参数不使用上述的默认类型�?aardio 提供了以下函数可以明确的声明 COM 参数的类型：
-------------------------------------------------------------------
com.byte() 将参数指定的数值或数组声明�?8 位整型数值�?com.ubyte()  将参数指定的数值或数组声明�?8 位无符号整型数值�?com.word() 将参数指定的数值或数组声明�?16 位整型数值�?com.uword() 将参数指定的数值或数组声明�?16 位无符号整型数值�?com.int() 将参数指定的数值或数组声明�?32 位整型数值�?com.uint() 将参数指定的数值或数组声明�?32 位无符号整型数值�?com.long() 将参数指定的数值或数组声明�?64 位整型数值�?com.ulong() 将参数指定的数值或数组声明�?64 位无符号整型数值�?com.float() 将参数指定的数值或数组声明�?32 位浮点数值�?com.double() 将参数指定的数值或数组声明�?64 位浮点数值�?com.Variant() 将参数指定的值或数组声明为变体类型�?-------------------------------------------------------------------
要注意不同编程语言之间的差别：
VB6/VBA �?Integer �?6位数值，Long �?2位数值，
而在 C# �?int �?2位数�? long �?4位数值，
更重要的不是类型名字，而是存储长度�?
更多细节请参考「aardio 范例 / COM 组件 / 进阶提示 / 参数类型转换�?*******************/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/introduction.md)

