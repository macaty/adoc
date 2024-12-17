[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 菜单

```aardio aardio
//窗口程序 - 菜单
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="菜单用法演示";right=497;bottom=345)
winform.add()
/*}}*/

/*
注意使用菜单需要先调用 import win.ui.menu，不然发布后会报错�?开发环境下运行，为了加快启动速度，不会百分百排除所有没有引用的库，
当然大家也可以像其他开发工具那样，每次都发布成 EXE 文件后再运行�?*/
var menuFile = win.ui.popmenu(winform);//创建弹出菜单
menuFile.add(
    "打开",
    function(id){
            winform.msgbox("打开文件")
    }
)

//------------------------------------
var menuHelp = win.ui.popmenu(winform);//创建弹出菜单
menuHelp.add(
    "关于",
    function(id){
            winform.msgbox("关于")
    }
)
menuHelp.add(); //添加分隔�?
menuHelp.addTable( {
    { "帮助";
        function(id){
            winform.msgbox("帮助")
        }
    };
    { /*---分隔�?--*/ };
    { "退�?;
        function(id){
            winform.close()
        }
    };
} )

var menuRadio = win.ui.popmenu(winform);//创建弹出菜单
menuRadio.onMenuItemClick = function(id){
    menuRadio.selId = id;
    winform.msgbox( menuRadio.selText )
}

menuRadio.add("a" )
menuRadio.add("b" )
menuRadio.add("c" )

var menu = win.ui.menu(winform);//创建主菜�?menu.add('文件',menuFile)
menu.add('帮助',menuHelp)
menu.add('选择其中一�?,menuRadio)

//主菜单构建完成后要用下面这句更新,menu.addTable()会自动调用redraw()
//menu.redraw();

menu.addTable( {
    { "测试菜单";
            {
                {   "子菜�?;
                    function(id){
                        winform.msgbox("测试菜单->子菜�?)
                    }
                };
                {   "子菜�?";
                    function(id){
                        winform.msgbox("测试菜单->子菜�?")
                    }
                }
            }
    };
    { "测试菜单2";
            {
                {   "子菜�?;
                    function(id){
                        winform.msgbox("测试菜单2->子菜�?)
                    }
                };
                {   "子菜�?";
                    function(id){
                        winform.msgbox("测试菜单2->子菜�?")
                    }
                }
            }
    };
} )

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Menu/menuTable.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Menu/menuTable.md')

