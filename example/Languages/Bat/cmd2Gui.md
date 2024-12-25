[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: DOS命令行窗口化工具

```aardio aardio
//命令行窗口化
//相关范例：进�?> 管道
import win.ui;
import win.ui.menu;
import process.popen;
/*DSG{{*/
var winform = win.form(text="DOS命令行窗口化工具";right=760;bottom=595;bgcolor=16777215;)
winform.add(
btnCls={cls="button";text="清屏";left=560;top=564;right=634;bottom=588;db=1;dr=1;font=LOGFONT(name='宋体');z=5};
button={cls="button";text="运行";left=481;top=564;right=555;bottom=588;db=1;dr=1;font=LOGFONT(name='宋体');z=1};
editCmd={cls="edit";text="dir c:\";left=233;top=564;right=465;bottom=588;db=1;dl=1;dr=1;edge=1;font=LOGFONT(name='宋体');z=4};
editCon={cls="edit";left=11;top=9;right=748;bottom=553;bgcolor=0;color=16777215;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='宋体');hscroll=1;link=1;multiline=1;vscroll=1;z=2};
static={cls="static";text="命令�?;left=180;top=568;right=227;bottom=584;align="center";db=1;dl=1;font=LOGFONT(h=-14;name='宋体');transparent=1;z=3}
)
/*}}*/

onMenu = function(id){
    var str = winform.menu.getString(id,0x0/*_MF_BYCOMMAND*/);
    str = string.replace(str,"\S+\s*$","")
    winform.editCmd.text = str;
}

var menu = win.ui.menu(winform);//创建主菜�?menu.add( "DOS命令",{
    { "ver 显示版本信息";onMenu  };
    { "regedit /s 注册表文件名 导入注册�?;onMenu  };
    { "regedit /e 注册表文件名 导出注册�?;onMenu  };
    { "cacls 文件�?查看文件的访问用户权限列�?";onMenu  };
    { "set 环境变量名称=要指派的�?设置环境变量 ";onMenu  };
    { "set 显示当前所有的环境变量";onMenu  };
    { "set p 显示出当前以字符p开头的所有环境变�?;onMenu  };
    { "echo 信息 在屏幕上显示出信�?;onMenu  };
} )
menu.add( "网络命令", {
        { "net"; {
            { "use"; {
                {"use \\ip\ipc$ "" "" /user:"" "" 建立IPC空链�?;onMenu  };
                {"use \\ip\ipc$ ""密码"" /user:""用户�?" 建立IPC非空链接";onMenu  };
                {"use h: \\ip\c$ ""密码"" /user:""用户�?" 直接登陆后映射对方C：到本地为H:";onMenu  };
                {"use h: \\ip\c$ 登陆后映射对方C：到本地为H:";onMenu  };
                {"use \\ip\ipc$ /del 删除IPC链接";onMenu  };
                {"use h: /del 删除映射对方到本地的为H:的映�?;onMenu  };
            } }

            {"账户"; {
                {"password 密码 更改系统登陆密码";onMenu  };
                {"user guest 12345 用guest用户登陆后用将密码改�?2345";onMenu  };
                {"user 用户�?密码 /add 建立用户";onMenu  };
                {"user guest /active:yes 激活guest用户";onMenu  };
                {"user 查看有哪些用�?;onMenu  };
                {"user 帐户�?查看帐户的属�?;onMenu  };
                {"localgroup administrators 用户�?/add 把“用户”添加到管理员中使其具有管理员权�?;onMenu  };
            } }

            {"共享"; {
                {"share 查看本地开启的共享";onMenu  };
                {"share ipc$ 开启ipc$共享";onMenu  };
                {"share ipc$ /del 删除ipc$共享";onMenu  };
                {"share c$ /del 删除C：共�?;onMenu  };
                {"view 查看本地局域网内开启了哪些共享 ";onMenu  };
                {"view \\ip 查看对方局域网内开启了哪些共享";onMenu  };
                {"logoff 断开连接的共�?;onMenu  };
            } }

            {"NT服务"; {
                {"start 查看开启了哪些服务";onMenu  };
                {"start 服务�? 开启服�?;onMenu  };
                {"stop 服务�?停止某服�?;onMenu  };
                {"pause 服务�?暂停某服�?;onMenu  };
            } }

            {"时间"; {
            {"time \\目标ip 查看对方时间";onMenu  };
            {"time \\目标ip /set 同步时间";onMenu  };
            {"time \\目标ip /set /yes 同步时间并取消确�?;onMenu  };

            } }
        }}
        {"netstat"; {
            {"netstat -a 查看开启了哪些端口";onMenu  };
            {"netstat -n 查看端口的网络连接情�?";onMenu  };
            {"netstat -an 查看端口";onMenu  };
            {"netstat -v 查看正在进行的工�?;onMenu  };
            {"netstat -p 协议�?查看某协议使用情�?;onMenu  };
            {"netstat -p tcq/ip 查看tcp/ip协议使用情况";onMenu  }
            {"netstat -s 查看正在使用的所有协议使用情�?;onMenu  }
            {"nbtstat -A ip 看对方最近登陆的用户�?;onMenu  }
        } }
        {"nbtstat"; {
            {"nbtstat -A ip 看对方最近登陆的用户�?;onMenu  }
        } }
        {"tracert -参数 ip 跟踪路由";onMenu }
        {"ping ip(或域�? 向对方主机发送默认大小为32字节的数�?;onMenu  }
        {"ipconfig /all 显示全部网卡配置信息";onMenu  };
        {"telnet ip 端口 远程登陆服务�?;onMenu  }
        {"netsh 查看或更改本地网络配置情�?;onMenu  }
        {"arp -a 查看全部ARP缓存";onMenu  }
} )
menu.add( "文件命令", {
        {"dir 查看文件";onMenu  }
        {"dir /Q 显示文件及目录属系统哪个用户";onMenu  }
        {"dir /T:C 显示文件创建时间,";onMenu  }
        {"dir /T:A 显示文件上次被访问时�?";onMenu  }
        {"dir /T:W 上次被修改时�?";onMenu  }
        {"attrib 文件�?目录�? 查看某文�?目录)的属�?";onMenu  }
        {"attrib 文件�?-A -R -S -H H 去掉某文件的存档,只读,系统,隐藏属�?;onMenu  }
        {"attrib 文件�?+A +R +S +H 添加某文件的存档,只读,系统,隐藏属�?;onMenu  }
        {"del -F 文件�?�?F参数后就可删除只读文�?;onMenu  }
        {"del -F 文件�?/AR�?AH�?AS�?AA分别表示删除只读、隐藏、系统、存档文�?;onMenu  }
        {"del -F /A-R�?A-H�?A-S�?A-A表示删除除只读、隐藏、系统、存档以外的文件";onMenu  }
        {"DEL/A-S *.*  删除当前目录下除系统文件以外的所有文�?;onMenu  }
        {"del /S /Q 目录 删除目录及目录下的所有子目录和文�?;onMenu  }
        {"rmdir /s /Q 目录 /S 删除目录及目录下的所有子目录和文�?";onMenu  }
        {"move 要移动的文件�?存放移动文件的路�?移动文件 ";onMenu  }
        {"fc one.txt two.txt > 3st.txt 对比二个文件并把不同之处输出�?st.txt文件�?";onMenu  }
        {"copy 路径\文件�? 路径\文件�? /y 复制文件1到指定的目录为文�?";onMenu  }
        {"copy c:\srv.exe \\ip\admin$ 复制本地c:\srv.exe到对方的admin�?";onMenu  }
        {"cppy 1st.jpg/b+2st.txt/a 3st.jpg �?st.txt的内容藏身到1st.jpg中生�?st.jpg新的文件";onMenu  }
        {"copy \\ip\admin$\*.* c:\   复制对方admini$共享下的所有文件至本地C�?";onMenu  }
        {"xcopy 要复制的文件或目�?";onMenu  }
        {"for 对一组文件中的每一个文件执行某个特定命�?";onMenu  }
        {"findstr ""Hello"" aa.txt 在aa.txt文件中寻找字符串hello";onMenu  }
        {"find 文件�?查找某文�?";onMenu  }
        {"format 盘符 /FS:类型 格式化磁�?;onMenu  }
        {"md 目录�?创建目录 ";onMenu  }
        {"replace 源文�?要替换文件的目录 替换文件 ";onMenu  }
        {"ren 原文件名 新文件名 重命名文件名";onMenu  }
        {"tree 以树形结构显示出目录 ";onMenu  }
        {"tree -f 将列出第个文件夹中文件名�?";onMenu  }
        {"type 文件�?显示文本文件的内�?;onMenu  }
        {"more 文件�?逐屏显示输出文件";onMenu  }
} )
menu.add( "IIS服务命令", {
        {"iisreset /reboot 重启win2k";onMenu  }
        {"iisreset /start 启动Internet服务";onMenu  }
        {"iisreset /start 停止Internet服务";onMenu  }
        {"iisreset /restart 重新启动Internet服务";onMenu  }
        {"iisreset /status 显示Internet服务状�?";onMenu  }
        {"iisreset /enable  启用Internet服务的重新启�?;onMenu  }
        {"iisreset /disable 禁用Internet服务的重新启�?;onMenu  }
        {"iisreset /rebootonerror 当启动、停止或重新启动Internet服务�?若发生错误将重新开�?";onMenu  }
        {"iisreset /noforce 若无法停止Internet服务,将不会强制终止Internet服务 ";onMenu  }
} )
menu.add( "设置", {
    {"自动清屏";
        function(id){
            winform.autoCls = !winform.menu.checked(id,0)
            winform.menu.check(id,winform.autoCls,0)
        }
    }
} )

import win.path;
import string.cmdline;

//输入字符到子进程
winform.editCon.wndproc = function(hwnd,message,wParam,lParam){
    if( message == 0x102/*_WM_CHAR*/){
        if( winform.process ){

            if( winform.editCon.mbc ){
                table.push( winform.editCon.mbc,wParam & 0xFF )

                winform.process.write( string.pack( winform.editCon.mbc  ) );
                winform.editCon.mbc = null;
                return;
            }

            if( wParam <= 0x80 ){
                if( wParam == 13 ){
                    winform.process.write('\r\n');
                }
                elseif( wParam >= 32 && wParam <= 126 ){ //可打印字�?                    winform.process.write( string.pack( wParam & 0xFF  )  );
                }
            }
            else {
                winform.editCon.mbc = { wParam & 0xFF  };
            }
        }
    }
}

winform.button.oncommand = function(id,event){
    if( winform.autoCls ){
        winform.btnCls.oncommand();
    }

    if( winform.process ){
        winform.process.process.terminate();
        winform.process.close();
    }

    winform.editCon.setFocus()

    var cmdline = winform.editCmd.text;
    winform.process = process.popen.cmd(cmdline) // 创建进程

    if(!winform.process){
        winform.editCon.print('错误的命令行或参�?);
        winform.editCmd.selectAll();
        return;
    }

    //将命令行输出自动转发到文本框
    winform.process.logResponse(winform.editCon);
}

winform.btnCls.oncommand = function(id,event){
    winform.editCon.text = ""
}

winform.editCmd.onOk = function(){
    winform.button.oncommand();
    return true;
}

winform.onOk = winform.editCmd.onOk

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/cmd2Gui.md)

