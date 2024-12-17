[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: .NET 名字空间分析工具

```aardio aardio
//.NET 名字空间分析工具
import win.ui;
/*DSG{{*/
var winform = win.form(text=".NET 名字空间分析工具";right=830;bottom=469)
winform.add(
button={cls="button";text="分析";left=673;top=7;right=820;bottom=43;dr=1;dt=1;z=3};
edit={cls="edit";left=15;top=54;right=816;bottom=456;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editNameSpace={cls="edit";left=177;top=12;right=546;bottom=41;dl=1;dr=1;dt=1;edge=1;multiline=1;z=2};
editNetVersion={cls="edit";text="4.0";left=599;top=12;right=654;bottom=41;edge=1;z=5};
static={cls="static";text=".NET Framework 名字空间�?;left=12;top=10;right=169;bottom=35;align="right";center=1;dl=1;dt=1;transparent=1;z=4};
static2={cls="static";text="版本�?;left=549;top=10;right=597;bottom=35;align="right";center=1;transparent=1;z=6}
)
/*}}*/

winform.edit.limit = -1;
winform.button.oncommand = function(id,event){
    if(!#winform.editNameSpace.text){
        return winform.editNameSpace.showErrorTip("请输�?.NET 名字空间")
    }
    winform.edit.text = "";

    thread.invoke(
        function(winform,netNamespace,netVersion){
            winform.button.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?}

            //创建 HTML + HTTP 客户�?            import web.rest.htmlClient;
            var htmlClient = web.rest.htmlClient();

            //创建 JSON + HTTP 客户�?            import web.rest.jsonClient;
            var jsonClient = web.rest.jsonClient();

            //声明远程 API
            var apiUrl = "https://learn.microsoft.com/en-us/dotnet/api/_splitted/{namespace}/toc.json?view=netframework-"+netVersion;
            var tocApi = jsonClient.api(apiUrl);

            //抓取 JSON 并自动解�?            var tocInfo = tocApi[netNamespace].get();
            if(!tocInfo){
                winform.button.disabledText = null;
                winform.msgboxErr("获取数据失败");
                return;
            }

            var map = {}
            for(i,item in tocInfo.items[1][["children"]] ){
                var apiName = item.uid;
                var url = inet.url.joinpath(apiUrl,item.href);
                url = inet.url.canonicalize(url)

                //抓取 HTML 并解�?                var htmlDoc = htmlClient.get( url,{view="netframework-"+netVersion});

                //查找程序集名�?                var assembly;
                for ele in htmlDoc.eachQuery(tagName="dl"){

                    var moniker = ele["data-moniker"];
                    if( moniker && string.find(moniker,"netframework-"+netVersion)){
                        if(ele.dd[1]){
                            assembly = ele.dd[1].innerText()
                            if(..string.endWith(assembly,".dll")){
                                break;
                            }
                        }
                    }
                }

                if(!assembly) continue;

                winform.edit.print(apiName,assembly)

                if(!map[assembly]){
                    map[assembly] = {}
                }

                table.push(map[assembly],apiName);
            }

            import web.json;
            winform.edit.text = web.json.stringify(map,true);
            winform.button.disabledText = null;

        },winform,winform.editNameSpace.text,winform.editNetVersion.text
    )
}

winform.edit.text = /*****************
//aardio 导入 .NET 名字空间示例
import dotNet;

//导入 System，下级名字如果在同一程序集内，那么在使用时按需自动导入�?dotNet.import("System");

//如果下级名字空间不在同一程序集内，必须用哪个导入哪个，不会覆盖已存在的父名字空间�?dotNet.import("System.Security.Cryptography","mscorlib");

//不会自动导入或替换上级名字空间，例如下面的代码不能替�?dotNet.import("System");
dotNet.import("System.Security.Cryptography.X509Certificates","System");

/*
.NET 很多自带的名字空间在不同�?DLL 实现�?所以我们需要用这个工具，分析一个名字空间在哪个 DLL 里的成员最多�?就用�?DLL 导入该名字空间，可以少写 dotNet.import 语句�?*/
*****************/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/framework.toc.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/framework.toc.md')

