[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# orphanWindow

orphanWindow �?aardio 实现的一种全新的窗口模式�?
orphanWindow 即悬浮窗口，指的是普通的控件窗口孤立出来成为独立窗口，但是仍然可以显示在原来的位置，如影随形的跟随父窗口移动、显示、隐藏。在外观上用户仍然以为这是父窗口上的子窗口，感觉不到这是一个独立的窗口。orphanWindow 与子窗口不同的是可以显示在父窗口的显式区域之外�?
orphanWindow 用法很简单：

首先在窗体设计器中拖好控件的位置（控件可以拖到窗口的外面），然后调用控件�?orphanWindow() 函数就行了�?
我们还可以这样写�?`winform.custom.orphanWindow(,hwndBuddy)`

�?hwndBuddy 指定为外部窗口句柄，就可以将外部进程窗口也转化为 aardio 中独有的 orphanWindow，成为吸附在 aardio 窗口上的伪子窗口。这可以用来解决一些比较复杂的问题，实现一些难以实现的效果。例�?ruffle.exe 运行时以独立窗口播放动画，将这个外部进程的独立窗口嵌入为子窗口时效果并不理想。�?aardio �?process.ruffle 扩展库使�?orphanWindow 实现了一个动画控件，可以非常方便地将 ruffle 嵌入�?aardio 窗口中作为控件使用�?
在传统窗体中，要让一个控件完美透明，并且完美浮动在其他控件前面，是一件比较麻烦的事�?例如 plus 控件也有一些限制，使用剪切背景等方法修正透明带来的闪烁，但是你不能把plus控件浮动在一个按钮前面且显示透明动画�?
一个窗体的子窗口总是显示在父窗口的内部，例如要将子窗口一部分显示在父窗口外面，并且在桌面上透明，这个实现起来就很麻烦了�?
orphanWindow 就是用来解决这些问题�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/orphanWindow.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/orphanWindow.md')
