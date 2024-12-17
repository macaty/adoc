[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 复选列表框 响应通知消息演示

```aardio aardio
//checklist
import win.ui;
/*DSG{{*/
var winform = win.form(text="复选列表框 响应通知消息演示";right=349;bottom=249;max=false;)
winform.add(
checklist={cls="checklist";left=20;top=45;right=326;bottom=224;bgcolor=16777215;edge=1;items={};z=1};
static={cls="static";text="请点选项�?;left=22;top=21;right=268;bottom=45;transparent=1;z=2}
)
/*}}*/

winform.checklist.items = { {"测试项目"};{"测试项目2"};{"测试项目3"} }
winform.checklist.addItem("测试项目4")
winform.checklist.addItem("测试项目5")

//项目勾选状态变更触发此事件
winform.checklist.onCheckedChanged = function(checked,item){
    if(checked){
        winform.static.text = "选中:" + item;
    }
    else {
        winform.static.text = "取消选中:" + item;
    }
}

import win.ui.menu;
winform.checklist.onRightClick = function(item,subItem,hitFlags){

        //创建弹出菜单
        var popmenu = win.ui.popmenu(winform);
        popmenu.add('删除',function(id){
            winform.checklist.delItem( item)
        } )

        popmenu.popup();
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/ListView/checklist.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/ListView/checklist.md')

