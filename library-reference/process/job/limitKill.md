[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.job.limitKill 库模块帮助文�?
## process.job 成员列表

### process.job.limitKill

使用子进程对象的 assignToJobObject 函数绑定此对�?

则进程退出时子进程自动终�?
[返回对象:processJobLimitKillObject](#processJobLimitKillObject)

创建新的 process.job.limitKill 作业对象

### process.job.limitKill()

[返回对象:processJobLimitKillObject](#processJobLimitKillObject)

### process.job.limitKill(limitFlags)

创建新的 process.job.limitKill 作业对象�?
limitFlags 可指定以下值：

\_JOB\_OBJECT\_LIMIT\_SILENT\_BREAKAWAY\_OK 下级进程不自动继承作业对�?
\_JOB\_OBJECT\_LIMIT\_BREAKAWAY\_O 允许创建下级进程时指�?CREATE\_BREAKAWAY\_FROM\_JOB

## processJobLimitKillObject 成员列表

### processJobLimitKillObject.assignProcess(processId)

将参数指定的进程绑定当前作业对象,

参数可以指定使用数值指定进程ID，或使用指针指定进程句柄,

也可以传�?process �?process.popen 对象

### processJobLimitKillObject.isIn(processId)

判断参数指定的进程是否属于当前作业对�?

参数可以指定使用数值指定进程ID，或使用指针指定进程句柄,

也可以传�?process �?process.popen 对象

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/process/job/limitKill.md)

