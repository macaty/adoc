[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 执行命令

执行命令以前必须调用 [wb.wait()](wait.html#wait) 等待网页打开.

## wb.exec

1. 函数原型�?
   `wb.exec( "命令",参数,是否显示UI )`

2. 函数说明�?
   在网页上执行命令,除第一个参数必须以�?其他参数可�?可选命令如�?

   2D-Position 允许通过拖曳移动绝对定位的对象�?

   AbsolutePosition 设定元素�?position 属性为"absolute"(绝对)�?

   BackColor 设置或获取当前选中区的背景颜色�?

   BlockDirLTR 目前尚未支持�?

   BlockDirRTL 目前尚未支持�?

   Bold 切换当前选中区的粗体显示与否�?

   BrowseMode 目前尚未支持�?

   Copy 将当前选中区复制到剪贴板�?

   CreateBookmark 创建一个书签锚或获取当前选中区或插入点的书签锚的名称�?

   CreateLink 在当前选中区上插入超级链接，或显示一个对话框允许用户指定要为当前选中区插入的超级链接�?URL�?

   Cut 将当前选中区复制到剪贴板并删除之�?

   Delete 删除当前选中区�?

   DirLTR 目前尚未支持�?

   DirRTL 目前尚未支持�?

   EditMode 目前尚未支持�?

   FontName 设置或获取当前选中区的字体�?

   FontSize 设置或获取当前选中区的字体大小�?

   ForeColor 设置或获取当前选中区的前景(文本)颜色�?

   FormatBlock 设置当前块格式化标签�?

   Indent 增加选中文本的缩进�?

   InlineDirLTR 目前尚未支持�?

   InlineDirRTL 目前尚未支持�?

   InsertButton 用按钮控件覆盖当前选中区�?

   InsertFieldset 用方框覆盖当前选中区�?

   InsertHorizontalRule 用水平线覆盖当前选中区�?

   InsertIFrame 用内嵌框架覆盖当前选中区�?

   InsertImage 用图像覆盖当前选中区�?

   InsertInputButton 用按钮控件覆盖当前选中区�?

   InsertInputCheckbox 用复选框控件覆盖当前选中区�?

   InsertInputFileUpload 用文件上载控件覆盖当前选中区�?

   InsertInputHidden 插入隐藏控件覆盖当前选中区�?

   InsertInputImage 用图像控件覆盖当前选中区�?

   InsertInputPassword 用密码控件覆盖当前选中区�?

   InsertInputRadio 用单选钮控件覆盖当前选中区�?

   InsertInputReset 用重置控件覆盖当前选中区�?

   InsertInputSubmit 用提交控件覆盖当前选中区�?

   InsertInputText 用文本控件覆盖当前选中区�?

   InsertMarquee 用空字幕覆盖当前选中区�?

   InsertOrderedList 切换当前选中区是编号列表还是常规格式化块�?

   InsertParagraph 用换行覆盖当前选中区�?

   InsertSelectDropdown 用下拉框控件覆盖当前选中区�?

   InsertSelectListbox 用列表框控件覆盖当前选中区�?

   InsertTextArea 用多行文本输入控件覆盖当前选中区�?

   InsertUnorderedList 切换当前选中区是项目符号列表还是常规格式化块�?

   Italic 切换当前选中区斜体显示与否�?

   JustifyCenter 将当前选中区在所在格式化块置中�?

   JustifyFull 目前尚未支持�?

   JustifyLeft 将当前选中区所在格式化块左对齐�?

   JustifyNone 目前尚未支持�?

   JustifyRight 将当前选中区所在格式化块右对齐�?

   LiveResize 迫使 MSHTML 编辑器在缩放或移动过程中持续更新元素外观，而不是只在移动或缩放完成后更新�?

   MultipleSelection 允许当用户按�?Shift �?Ctrl 键时一次选中多于一个站点可选元素�?

   Open 目前尚未支持�?

   Outdent 减少选中区所在格式化块的缩进�?

   OverWrite 切换文本状态的插入和覆盖�?

   Paste 用剪贴板内容覆盖当前选中区�?

   PlayImage 目前尚未支持�?

   Print 打开打印对话框以便用户可以打印当前页�?

   Redo 目前尚未支持�?

   Refresh 刷新当前文档�?

   RemoveFormat 从当前选中区中删除格式化标签�?

   RemoveParaFormat 目前尚未支持�?

   SaveAs 将当�?Web 页面保存为文件�?

   SelectAll 选中整个文档�?

   SizeToControl 目前尚未支持�?

   SizeToControlHeight 目前尚未支持�?

   SizeToControlWidth 目前尚未支持�?

   Stop 目前尚未支持�?

   StopImage 目前尚未支持�?

   StrikeThrough 目前尚未支持�?

   Subscript 目前尚未支持�?

   Superscript 目前尚未支持�?

   UnBookmark 从当前选中区中删除全部书签�?

   Underline 切换当前选中区的下划线显示与否�?

   Undo 目前尚未支持�?

   Unlink 从当前选中区中删除全部超级链接�?

   Unselect 清除当前选中区的选中状态�?
3. 调用示例�?

   ```aardio aardio
   //用于取消选中的阴影部�?   wb.exec('Unselect');

   //选中页面上的所有元�?   wb.exec('SelectAll');

   //复制
   wb.exec('Copy');

   //删除选中的区�?   wb.exec('Delete');

   //剪下选中的区�?   wb.exec('Cut');

   //打印整个页面
   wb.exec('print');

   //第二个参数为欲保存的文件�?   wb.exec('SaveAs','my.html');

   //将选中的区块设为指定的背景�?   wb.exec('BackColor','#FFbbDD');

   //指定前景�?   wb.exec('ForeColor','#BBDDCC');

   //指定字体大小
   wb.exec('FontSize',7);

   //字体必须是系统支持的字体
   wb.exec('FontName','标楷�?);

   //字体变粗
   wb.exec('Bold');

   //变斜�?   wb.exec('Italic');

   //将选中的文字加下划�?   wb.exec('Underline');

   //在选中的文字上划粗�?   wb.exec('StrikeThrough');

   //将选中的部分文字变�?   wb.exec('SuperScript');

   //将选中区块的下划线取消�?   wb.exec('Underline');

   //有序列表
   wb.exec('InsertOrderedList');

   //无序列表
   wb.exec('InsertUnorderedList');

   //缩进
   wb.exec('Indent');

   //插入超链接，弹出一个对话框输入URL
   wb.exec('CreateLink','true',true);

   //直接插入超链�?   wb.exec('CreateLink',http://www.aardio.com');
   //重设为button
   wb.exec('InsertButton',"ID");

   //重设为一个fieldset
   wb.exec('InsertFieldSet',"ID");

   //插入一个水平线
   wb.exec('InsertHorizontalRule',"ID");

   //插入一个iframe
   wb.exec('InsertIFrame',"ID");

   //插入一个image,参数三为true需要图片，为false不需要图�?   wb.exec('InsertImage',"ID",true);

   //插入一个checkbox
   wb.exec('InsertInputCheckbox',"ID");

   //插入一个file类型的object
   wb.exec('InsertInputFileUpload',"ID");

   //插入一个hidden
   wb.exec('InsertInputHidden',"ID");

   //插入一个InputImage
   wb.exec('InsertInputImage',"ID");

   //插入一个Password
   wb.exec('InsertInputPassword',"ID");

   //插入一个Radio
   wb.exec('InsertInputRadio',"ID");

   //插入一个Reset
   wb.exec('InsertInputReset',"ID");

   //插入一个Submit
   wb.exec('InsertInputSubmit',"ID");

   //插入一个inputtext
   wb.exec('InsertInputText',"ID");

   //插入一个textarea
   wb.exec('InsertTextArea',"ID");

   //插入一个selectlistbox
   wb.exec('InsertSelectListbox',"ID");

   //插入一个singleselect
   wb.exec('InsertSelectDropdown',"ID");

   //插入一个换�?   wb.exec('InsertParagraph');

   //插入一个marquee
   wb.exec('InsertMarquee',"ID");

   ```


## wb.execEle

1. 函数原型�?
   `wb.execEle( ele,"命令",参数,是否显示UI )`

2. 函数说明�?
   该函数用法与 wb.exec 完全相同.唯一的区别是需要在第一个参数中指定节点(HTML DOM Element)对象.而且函数对指定的节点执行命令,而不是针对整个网页执行命�?

   请参�? [使用 wb.getEle("id") 获取节点](getele.html)


## wb.execWb

1. 函数原型�?
   `返回�?= wb.execWb( 命令ID,参数=null,选项=1 )`

2. 函数说明�?
   第一个参数命令ID是一个数�?可选值如�?

   \_OLECMDID\_OPEN = 1;


    \_OLECMDID\_NEW = 2;


    \_OLECMDID\_SAVE = 3;


    \_OLECMDID\_SAVEAS = 4;


    \_OLECMDID\_SAVECOPYAS = 5;


    \_OLECMDID\_PRINT = 6;


    \_OLECMDID\_PRINTPREVIEW = 7;


    \_OLECMDID\_PAGESETUP = 8;


    \_OLECMDID\_SPELL = 9;


    \_OLECMDID\_PROPERTIES = 10;


    \_OLECMDID\_CUT = 11;


    \_OLECMDID\_COPY = 12;


    \_OLECMDID\_PASTE = 13;


    \_OLECMDID\_PASTESPECIAL = 14;


    \_OLECMDID\_UNDO = 15;


    \_OLECMDID\_REDO = 16;


    \_OLECMDID\_SELECTALL = 17;


    \_OLECMDID\_CLEARSELECTION = 18;


    \_OLECMDID\_ZOOM = 19;


    \_OLECMDID\_GETZOOMRANGE = 20


    \_OLECMDID\_UPDATECOMMANDS = 21


    \_OLECMDID\_REFRESH = 22


    \_OLECMDID\_STOP = 23


    \_OLECMDID\_HIDETOOLBARS = 24


    \_OLECMDID\_SETPROGRESSMAX = 25


    \_OLECMDID\_SETPROGRESSPOS = 26


    \_OLECMDID\_SETPROGRESSTEXT = 27


    \_OLECMDID\_SETTITLE = 28


    \_OLECMDID\_SETDOWNLOADSTATE = 29


    \_OLECMDID\_STOPDOWNLOAD = 30

   第二个参数是该命令需要的参数,这是一个可选参�?一般不需要指�?

   第三个参数可选项如下:

   \_OLECMDEXECOPT\_DODEFAULT = 0;


    \_OLECMDEXECOPT\_PROMPTUSER = 1;


    \_OLECMDEXECOPT\_DONTPROMPTUSER = 2;


    \_OLECMDEXECOPT\_SHOWHELP = 3

   这是一个可选参�?默认参数�?

   该函数一般无返回�?

3. 调用示例�?

   ```aardio aardio
   wb.execWb(1,1)   //打开
   wb.execWb(4,1)   //另存�?   wb.execWb(10,1)   //属�?   wb.execWb(6,1)   //打印
   wb.execWb(6,6)   //打印>不会弹出打印机窗�?/td></tr>
   wb.execWb(7,1)   //打印预览
   wb.execWb(8,1)   //页面设置
   wb.execWb(10,1)   //查看页面属�?   wb.execWb(15,1)   //撤销
   wb.execWb(17,1)   //全�?   wb.execWb(22,1)   //刷新
   wb.execWb(45,1)   //关闭窗体无提�?</td></

   ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/exec.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/exec.md')

