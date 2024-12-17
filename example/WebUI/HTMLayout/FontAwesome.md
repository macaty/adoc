[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTMLayout - FontAwesome鍥炬爣瀛椾綋

```aardio aardio
//鍥炬爣瀛椾綋
import win.ui;
/*DSG{{*/
mainForm = win.form(text="HTMLayout - FontAwesome鍥炬爣瀛椾綋";right=759;bottom=469;border="dialog frame")
mainForm.add()
/*}}*/

import web.layout;
import web.layout.fontAwesome;//鍙互鏍规嵁闇�瑕佺紪杈戝瓧浣撴枃浠剁Щ闄ょ敤涓嶅埌鐨勫浘鏍?wbLayout = web.layout( mainForm );

wbLayout.html = /**
<!doctype html>
<html><head></head><body>
<span style="font-size:60px;"><i class="fa fa-bell-o" /> 閾冮摏</span> <br>
<span style="color:red"><i class="fa fa-pencil-square fa-5x " /> 缂栬緫</span><br>
<button><i class="fa fa-pencil"/> 缂栬緫</button>
</body></html>
**/
//鎵�鏈夊彲鐢ㄦ牱寮忚璁块棶瀹樼綉 http://fontawesome.io/cheatsheet

mainForm.show()
wbLayout.querySelector("button").state.focus = false;

return win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/FontAwesome.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/FontAwesome.md')

