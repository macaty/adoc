[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵цRake鍛戒护

```aardio aardio
//鎵цRake鍛戒护
import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵цRake鍛戒护";right=759;bottom=469)
winform.add(
edit={cls="edit";left=26;top=16;right=737;bottom=435;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

var rakefile = /*
task :purchaseAlcohol,[:arg1, :arg2] do |t, args|
  puts "#{args[:arg1].to_i + args[:arg2].to_i}"
end
*/

string.save("/rakefile",rakefile )

import process.ruby;
var result,err = process.ruby.rake("purchaseAlcohol[123,2]");
winform.edit.print(result,err);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/rake.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/rake.md')

