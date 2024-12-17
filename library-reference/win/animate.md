[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.animate 库模块帮助文�?
## win 成员列表

### win.animate()

[返回对象:winAnimateObject](#winAnimateObject)

### win.animate(窗口对象)

创建动画窗口

## win.animate 成员列表

### win.animate.fade()

[返回对象:winAnimateObject](#winAnimateObject)

### win.animate.fade(窗口对象)

创建淡入淡出动画窗口，该动画仅支持顶层窗口�?
不支持自定义动画方向,仅支持默认的\_AW\_CENTER选项

### win.animate.roll(窗口对象)

创建滚动动画窗口

### win.animate.slide()

[返回对象:winAnimateObject](#winAnimateObject)

### win.animate.slide(窗口对象)

创建滑动动画窗口�?
该动画不支持 \_AW\_CENTER 选项

## winAnimateObject 成员列表

### winAnimateObject.activate(持续时间,\_AW )

动画显示窗口,

可选用参数@1指定持续时间,省略则默认值为500毫秒

参数@2可选指向动画方�?选项使用 _AW_ 前缀常量,

注意fade效果不能指定方向

### winAnimateObject.hide(持续时间,\_AW )

动画隐藏窗口,

可选用参数@1指定持续时间,省略则默认值为500毫秒

参数@2可选指向动画方�?选项使用 _AW_ 前缀常量,

注意fade效果不能指定方向

### winAnimateObject.show(持续时间,\_AW )

动画显示窗口,

可选用参数@1指定持续时间,省略则默认值为500毫秒

参数@2可选指向动画方�?选项使用 _AW_ 前缀常量,

注意fade效果不能指定方向

### 自动完成常量

\_AW\_ACTIVATE=0x20000

\_AW\_BLEND=0x80000

\_AW\_CENTER=0x10

\_AW\_HOR\_NEGATIVE=0x2

\_AW\_HOR\_POSITIVE=0x1

\_AW\_SLIDE=0x40000

\_AW\_VER\_NEGATIVE=0x8

\_AW\_VER\_POSITIVE=0x4

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/animate.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/animate.md')

