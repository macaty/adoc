[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.rawInput 库模块帮助文�?
## win.rawInput 成员列表

原始输入（RAW INPUT）钩子�?
相比 key.hook，RAW INPUT 支持的输入设备更多一些，例如游戏手柄，触摸屏........等等�?
[参考文档](javascript:if(confirm('https://learn.microsoft.com/en-us/windows/win32/inputdev/about-raw-input?redirectedfrom=MSDN  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://learn.microsoft.com/en-us/windows/win32/inputdev/about-raw-input?redirectedfrom=MSDN')

### win.rawInput.getData()

[返回对象:rawInputDataObject](#rawInputDataObject)

### win.rawInput.getData(lparam)

返回原始输入钩子数据�?
### win.rawInput.register(窗口对象或句�?

注册原始输入（RAW INPUT）钩子窗口�?
## rawInputDataObject 成员列表

### rawInputDataObject.data.hid

[返回对象:rawInputHidObject](#rawInputHidObject)

### rawInputDataObject.data.keyboard

[返回对象:rawInputKeyboardObject](#rawInputKeyboardObject)

### rawInputDataObject.data.mouse

[返回对象:rawInputMouseObject](#rawInputMouseObject)

### rawInputDataObject.header

[返回对象:rawInputHeaderObject](#rawInputHeaderObject)

## rawInputHeaderObject 成员列表

### rawInputHeaderObject.device

设备句柄

### rawInputHeaderObject.dwType

0 为鼠标，1 为键盘，3 为游戏手柄或其他输入设备

### rawInputHeaderObject.param

WM\_INPUT 消息 wParam 参数�?
### rawInputHeaderObject.size

字节大小

## rawInputHidObject 成员列表

### rawInputHidObject.count

HID 输入总数，指�?rawData 数组的大�?
### rawInputHidObject.rawData.?

输入原始数据�?
这是一个字节数组的数组�?
u单个字节数组的大小与 sizeHid 属性一致�?
所有字节数组的总数也就�?rawData 的数组长度与 count 属性一致�?
### rawInputHidObject.sizeHid

每个 HID 输入的字节大小，指定 rawData 数组元素的数组大�?
## rawInputKeyboardObject 成员列表

### rawInputKeyboardObject.extraInformation

附加信息

### rawInputKeyboardObject.flags

扫描码选项

### rawInputKeyboardObject.makeCode

扫描�?
### rawInputKeyboardObject.message

消息

### rawInputKeyboardObject.vKey

虚拟键码

## rawInputMouseObject 成员列表

### rawInputMouseObject.buttonData

鼠标按钮数据

### rawInputMouseObject.buttonFlags

鼠标按钮转换状�?
### rawInputMouseObject.extraInformation

附加信息

### rawInputMouseObject.flags

选项

### rawInputMouseObject.lastX

X坐标移动�?
### rawInputMouseObject.lastY

Y坐标移动�?
### 自动完成常量

\_RIM\_TYPEHID=2

\_RIM\_TYPEKEYBOARD=1

\_RIM\_TYPEMOUSE=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/rawInput.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/rawInput.md')

