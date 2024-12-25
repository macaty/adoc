[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 远程CALL

使用raw库函数raw.remoteApi可以在外部进程中创建远程CALL函数.

## 什么是CALL

CALL 的本意在编程术语中指的是函数调用,用于将程序的执行交给其他的代码段，通常是一个子程序(函数)，同时保存必要的信息，从而使被调用段执行完毕后返回到调用点继续执行�?请参�? [函数](../../../language-reference/function/definitions.html)

这里我们提到�?CALL 是指 REMOTE CALL、游�?CALL，指一种注入外�?EXE 程序从外部调用函数的技�?�?CALL 一般使�?OD 等工具，�?CALL 的使用一般需要编写复杂的汇编代码，在aardio 中推出了一种通用 CAL L技术，可以象声明普�?API 函数一样声�?CALL,并且使用�?CALL 函数就象普通函数一样简单�?
请参�? [进程](../../std/process/process.html)

## raw.remoteApi

### 1\. 声明 CALL

语法�?
`func_call = raw.remoteApi( 进程ID|进程句柄,函数原型, 这里是函数地址,调用约定="stdcall" )`

说明�?
第一个参数为进程ID或进程句柄�?
函数原型、调用约定的使用方法与声明API的语法完全一致�?
请参�? [定义API函数](api.html) [原生数据类型](datatype.html)

### 2\. 在目标进程创�?DLL API

语法�?
`var func_call = raw.remoteApi(  进程ID|进程句柄,函数原型, DLL文件�?函数名字,调用约定="stdcall")`

说明�?
第一个参数为进程 ID 或进程句�?

函数原型、调用约定的使用方法与声明API的语法完全一�?请参�? [定义API函数](api.html) [原生数据类型](datatype.html)

调用约定默认为stdcall

## 示例

```aardio aardio
import winex;

//遍历桌面所有窗�?for hwnd,title,tid,pid in winex.each() {

     if(  title!="" && winex.isVisible(hwnd) /*不然下面的看不到�?/){

          var messageBox_call;

          try{
             //在目标进程内声明一个函数，加载 user.dll，并获取 user.dll 中的 MessageBoxW 函数指针
            messageBox_call = raw.remoteApi(pid
                 ,"void ( int hWnd, ustring text,ustring caption ,INT uType )"
                 ,"User32.dll","MessageBoxW");//DLL名以及函数名也可以更换为一个函数地址
         }

          if(messageBox_call){
             //象普通函数一样使�?            messageBox_call(0,"这是一个外部进程！在此进程加载了User32.dll，并获取执行了MessageBoxW 函数指针","aardio call" ,0)

             break ;
          }
     }
 }

```

## 使用 process 库创�?CALL

使用 process 库创建的进程对象拥有更高的权限，请参�? [prcs.remoteApi](../../std/process/process.html#remoteApi)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/remoteApi.md)

