[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 执行Rake命令

```aardio aardio
//执行Rake命令
import win.ui;
/*DSG{{*/
var winform = win.form(text="执行Rake命令";right=759;bottom=469)
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/rake.md)

