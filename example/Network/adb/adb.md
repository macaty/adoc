[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 操作安卓手机

```aardio aardio
//操作安卓手机
import console.int;

/*
请先打开安卓手机�?设置 / 更多设置 / 开发者选项 』，
然后启用『USB 调试』，如果看不到开发者选项，可上网查询该手机设备『显示开发者选项』的方法�?
也可以调用下面的函数无线连接手机（需要在手机开发者选项中启用『无线调试』）
process.adb.connect("IP:端口")

adb 文档�?http://developer.android.com/tools/help/adb.html
*/
import process.adb;

/*
查找已连接设备，找不到返�?null�?找到多个设备会自动设置默认设备，找到单个设备时不限定默认设备�?*/
if(!process.adb.findDevice()){
    return console.log("未连接手机设�?)
}

//获取所有设�?var devices = process.adb.getDevices();
console.dumpJson(devices);

//获取当前设备
var serialNo = process.adb.getSerialNo();
console.log("当前设备",serialNo)

var state = process.adb.getState();
console.log(state=="device"?"已连�?:"未连�?)

//执行 ADB 命令并获取结果，成功返回进程输出，失败返�?null，错误信息�?console.log(process.adb.get("get-state"))

//执行 Shell 命令
var adb = process.adb.shell("ls");
var out = adb.readAll(); //读取进程输出，adb 是一�?process.popen 对象，请参考该库函数文档�?console.log(out);

//执行 am start 命令打开程序，例如调用浏览器打开网址
var adb = process.adb.shell("am start -a android.intent.action.VIEW -d 'https://www.aardio.com'");

//或者直接调用下面的函数也可�?process.adb.startUrl("https://www.aardio.com");

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/adb/adb.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/adb/adb.md')

