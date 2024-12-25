[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# java.path 库模块帮助文�?
搜索目录规则

1、JDK HOME 指定�?Java 编译器根目录

搜索目录的优先顺序：
1、用户调�?java.path.setJdkHome() 设置的目�?2、进程环境变�?%JAVA\_HOME% 设置的目�?3、搜索包�?javac.exe 的目�?这会检�?Path% 环境变量里的所有目�?4、自注册表查�?JDK 目录
5、搜索默认安装位置等

2、JRE HOME 指定�?Java 运行时器根目�?
搜索目录的优先顺序：
1、用户调�?java.path.setJreHome() 设置的目�?2、用户调�?java.path.setJdkHome()，j 设置的目�?3、进程环境变�?%JRE\_HOME% 设置的目�?4、进程环境变�?%JAVA\_HOME% 设置的目�?5、搜索包�?javac.exe 的目�?这会检�?Path% 环境变量里的所有目�?6、自注册表查�?JDK 目录
7、搜索默认安装位置等�?
JVM 也是�?JRE 目录下查找，搜索顺序基本如上�?但搜�?JVM 会排�?64位JRE，仅查找包含可用�?32 �?jvm.dll�?JVM 用于调用 java 构造函数创建虚拟机，例如：
`var jvm = java()` 创建 Java 虚拟机或者调用任何获�?JVM 目录以后�?如果成功获取到可用的 JVM 路径，那么在一个进程实例中将不能再以任何方式修�?JVM 路径�?调用 java.path.setJreHome() 或修�?%JRE\_HOME% 环境变量都不能再改变 JVM 路径�?
在调�?java.openProcess,java.popenProcess 创建 Java 进程时，
则优先查�?4 �?JRE 运行时目录下�?java.exe, javaw.exe�?也可以支�?32 �?JRE�?
## java.path 成员列表

### java.path.findJre()

参数指定�?JRE 根目下是否包�?java.exe,javaw.exe

成功返回 JRE 目录

### java.path.findJvm()

参数指定�?JRE 根目下是否包含有�?jvm.dll

成功返回 true

### java.path.jdkHome()

用于获取 JDK 编译器根目录

关于初始化JDK,JRE目录的规则细节请参�?java.path 库函数文�?
### java.path.jdkHomeFromRegistry

自注册表查找安装�?JDK 目录

### java.path.jdkHomeFromRegistry(x64,version)

自注册表查找安装�?JDK 目录,

找到目录则返�?JDK 根目�?内部版本�?

所有参数可�?@x64 指定是否查询 64位注册表,32位系统忽略此参数,

version 用一个字符串指定内部版本�?

例如 Java 8 的内部版本号�?"1.8"

### java.path.jreBin()

返回 JRE 运行时目录下�?/bin 目录

关于初始化JDK,JRE目录的规则细节请参�?java.path 库函数文�?
### java.path.jreHome()

查找包含 64�?�?32�?java.exe,javaw.exe �?
JRE 运行时目录，用于调用 java.openProcess,java.popenProcess

以创�?Java 进程。搜索顺序为�?4位优先）�?
关于初始化JDK,JRE目录的规则细节请参�?java.path 库函数文�?
### java.path.jreHomeFromProgramFiles(version,x64,jdkOnly)

在默认安装目录搜�?JRE 目录,

可选用 @version 指定版本,

@x64 如果�?true 则仅搜索 64 �?JRE,32位系统忽略此参数,

@jdkOnly 如果�?true 则仅搜索 JDK 目录

在默认安装目录搜�?JRE 目录,

可选用 @version 指定版本,

@x64 如果�?true 则仅搜索 64 �?JRE,32位系统忽略此参数,

@jdkOnly 如果�?true 则仅搜索 JDK 目录

### java.path.jreHomeFromRegistry

自注册表查找安装�?JRE 目录

### java.path.jreHomeFromRegistry(x64,version)

自注册表查找安装�?JRE 目录,

找到目录则返�?JDK 根目�?内部版本�?

所有参数可�?@x64 指定是否查询 64位注册表,32位系统忽略此参数,

version 用一个字符串指定内部版本�?

例如 Java 8 的内部版本号�?"1.8"

### java.path.jvm()

用于获取创建 Java 虚拟机的 32 �?jvm.dll 路径,

此路径初始化成功即不允许修改�?
关于初始化JDK,JRE目录的规则细节请参�?java.path 库函数文�?
### java.path.jvmHome()

包含可创�?Java 虚拟机的 JRE 运行时根目录,

此路径一旦获取成功在当前进程中即不允许再修�?
�?
关于初始化JDK,JRE目录的规则细节请参�?java.path 库函数文�?
### java.path.setJdkHome()

指定第一优先级检测的 JDK 根目录，

在该目录下查�?Java 编译�?javac.exe �?
如该目录不符合要求则继续搜索其他合适的目录�?
### java.path.setJreHome()

指定第一优先级检测的 JRE 运行时根目录�?
在该目录下查�?4位或32�?java.exe,javaw.exe 以调�?
java.openProcess,java.popenProcess 创建 Java 进程�?
优先在该目录下搜�?JVM 用于创建 java 虚拟机对象，

如该目录不符合要求则继续搜索其他合适的目录�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/java/path.md)

