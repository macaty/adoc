[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.media 库模块帮助文�?
## fsys 成员列表

### fsys.media("媒体文件路径","其他选项",通知窗口)

打开媒体文件,支持 MP3�?
参数@2,@3为可选参�?
如果指定了通知窗口，操作完成以后窗口会收到 \_MM\_MCINOTIFY 消息

如果同一线程已打开同一文件，则返回已打开�?fsys.media 对象，并移动播放位置到开始处�?
fsys.media 创建的对象在超出变量作用域后会自动释�?
对象关闭后会自动关闭正在播放的媒体文�?
所以不要使用临时变量播放媒体文�?
### fsys.media()

[返回对象:fsysMediaObject](#fsysMediaObject)

## fsys.media 成员列表

### fsys.media.closeAll()

全部关闭

### fsys.media.execute("MCI媒体控制命令",通知窗口句柄)

发送MCI媒体控制命令

如果指定通知窗口句柄则在命令尾部添加"notify",

成功返回true,可选的返回消息,

失败返回false,错误信息

### fsys.media.getErrorString(错误代码)

返回错误信息

### fsys.media.playRepeat("音频文件路径",播放次数)

创建线程并重复播放指定的wav或mp3文件,

参数@1指定文件路径或资源文件路�?
参数@2指定播放次数

### fsys.media.playSound("WAVE文件路径",选项)

播放WAVE文件,参数@2可�?
WAVE文件可指定内嵌资源或内存文件,如果为null空值则停止播放

选项不指定时默认为\_SND\_ASYNC,也即启用异步播放,

选项指定�?时同步播放并等待播放完成,同步播放建议放到工作线程�?
## fsysMediaObject 成员列表

### fsysMediaObject.close()

关闭

### fsysMediaObject.deviceId

打开的设备标识符，数值�?
\_MM\_MCINOTIFY 消息�?lParam 参数里存放的就是这里�?deviceId

### fsysMediaObject.hwndCallback

指定用于接收\_MM\_MCINOTIFY通知消息的窗口句�?
\_MM\_MCINOTIFY可用于获取指令执行状�?
### fsysMediaObject.isPaused()

是否已暂�?
### fsysMediaObject.isPlaying()

是否正在播放

### fsysMediaObject.isStopped()

是否已停止播�?
### fsysMediaObject.length()

音频长度

### fsysMediaObject.mode()

返回当前模式�?
所有设备都存在 "not ready", "paused", "playing", "stopped" 等模�?

一些设备可能返�?"open", "parked", "recording", "seeking" 等�?
### fsysMediaObject.path()

打开的文件路�?
### fsysMediaObject.pause()

暂停

### fsysMediaObject.play("repeat")

循环播放,

仅适用于mp3，wav文件不支�?
### fsysMediaObject.play("wait")

播放并等待，

重新播放声音应该调用要seek(1)回到开始位�?
此操作会阻塞代码向后执行,最好是在工作线程里执行

### fsysMediaObject.play()

播放声音

可选添加多个文本指令参�?
无参数时不会阻塞当前线程�?
fsys.media 对像在析构时，会自动关闭声音，所以在声音播放时，要保持变量在生命周期内，

重新播放声音应该调用要seek(1)回到开始位�?
### fsysMediaObject.position()

返回当前播放位置

### fsysMediaObject.ready()

是否准备就绪可继续处理命�?
### fsysMediaObject.resume()

继续

### fsysMediaObject.seek(位置)

移动到指定位�?
参数�?表示移动到开始位置，

在播放声音以后重新播放声音时可调用此函数重新回到声音文件的开始位�?
### fsysMediaObject.send("MCI媒体控制命令")

使用$PATH表示打开的媒体文件路�?不要加引�?
如果传入多个参数则使用string.format格式�?
[所有可用指令](javascript:if(confirm('https://docs.microsoft.com/en-us/windows/desktop/Multimedia/multimedia-command-strings  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://docs.microsoft.com/en-us/windows/desktop/Multimedia/multimedia-command-strings')

### fsysMediaObject.step(-1)

负数向前,正数向后,省略跳到下一�?
### fsysMediaObject.stop()

停止播放

### fsysMediaObject.volume()

无参数获取音�?
指定数值参数设置音�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/media.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/media.md')

