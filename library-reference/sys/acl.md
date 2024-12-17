[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.acl 库模块帮助文�?
## sys.acl 成员列表

系统用户访问权限控制接口

### sys.acl.daclGrant(sid,objName,objType,trusteeType,premissions)

对@objName指定名称的对象获取@sid指定用户的@premissions参数指定的权�?

@objType可省略，默认值为\_SE\_FILE\_OBJECT,

其他参数请参考函数源码与MSDN

### sys.acl.daclGrantAdmin(objName,objType,premissions)

对@objName指定名称的对象获取管理员用户组的@premissions参数

### sys.acl.daclGrantEveryone(objName,objType,premissions)

对@objName指定名称的对象获取Everyone用户的@premissions参数指定的权�?
### sys.acl.getUserName()

返回当前系统用户�?
### sys.acl.sidAdmin()

创建SID，返回管理员用户组SID句柄

### sys.acl.sidCreate(identifierAuthority,...)

创建SID，返回SID句柄

参数@1使用数值数组指定SID\_IDENTIFIER\_AUTHORITY结构体的�?

后续可使�?�?个参数指定SID子权�?
### sys.acl.sidEveryone()

创建SID，返回Everyone用户SID句柄

### sys.acl.sidFromString(sidStr)

参数传入文本格式SID,

返回SID内存句柄

### sys.acl.sidFromUserName(userName,systemName)

参数@userName传入系统用户�?,省略取当前登录用户名,

@systemName参数可省�?

返回SID内存句柄

### sys.acl.sidStringFromUserName(userName,systemName)

参数@userName传入系统用户�?省略取当前登录用户名

@systemName参数可省�?

返回文本格式SID

### sys.acl.sidStringToUserName(sidStr,systemName)

参数传入文本格式 SID，@systemName 参数可省略�?
返回账户名，账户所在域名，账户类型（SID\_NAME\_USE 枚举�?
### sys.acl.sidToString(sid)

参数传入SID句柄,

返回SID文本格式字符�?
### sys.acl.sidToUserName(sid,systemName)

参数传入SID，@systemName参数可省略�?
返回账户名，账户所在域名，账户类型（SID\_NAME\_USE 枚举�?
### sys.acl.sidWellKnown(sidType,domainSid)

获取通用SID,

参数@1参�?:Advapi32.CreateWellKnownSid函数说明

参数@2可省�?

返回buffer对象不需要释�?
### sys.acl.takeOwnByAdmin(objName,objType)

对objName指定名称的对象获取管理员用户组的所有者权�?\\@nobjType可省略，默认值为\_SE\_FILE\_OBJECT

### sys.acl.takeOwnBySid(sid,objName,objType)

对@objName指定名称的对象获取sid指定用户的所有者权�?

sid应当是sid句柄或内存指�?

@objType可省略，默认值为\_SE\_FILE\_OBJECT

### sys.acl.takeOwnBySidString(sid,objName,objType)

对@objName指定名称的对象获取@sid指定用户的所有者权�?

@si参数指定文本格式SID,注意不是内存指针或句�?

@objType可省略，默认值为\_SE\_FILE\_OBJECT

### sys.acl.takeOwnByUserName(userName,objName,objType)

对@objName指定名称的对象获取@userName参数指定用户的所有者权�?

@objType可省略，默认值为\_SE\_FILE\_OBJECT

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/acl.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/acl.md')

