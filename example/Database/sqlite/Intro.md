[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 入门

```aardio aardio
//sqlite �?- 入门
import win.ui;
/*DSG{{*/
mainForm = win.form(text="sqlite 入门";right=425;bottom=498)
mainForm.add(
button={cls="button";text="查询";left=297;top=7;right=396;bottom=42;z=2};
editResult={cls="edit";left=12;top=61;right=400;bottom=491;edge=1;multiline=1;z=3};
editUser={cls="edit";text="小王";left=14;top=11;right=282;bottom=40;edge=1;multiline=1;z=1}
)
/*}}*/

import sqlite;
var db = sqlite("/intro2.db");//打开数据库连�?参数指定硬盘文件路径

//创建数据�?if( not db.existsTable("工作日志�?) /*是否已存在指定的�?/ ) {
    /*
    sqlite 可以�?MSSQL 那样将表名等标识符放在方括号�?避免表名是保留字�?,
    也可以将 MYSQL 那样将表示放在反引号�?键盘左上角波浪线下面的符�?,
    也可以按 ANSI SQL 约定放在双引号里,更可以放在单引号里�?
    SQL里面一般应当用单引号包含字符串( 各种数据库都支持的标准写�?)
    双引号在 ANSI SQL 中规定用来包含表�?- 一个容易让人误解的规定,所�?MSSQL 用了中括�?�?MYSQL 用了反引号�?    */
    db.exec( "CREATE TABLE [工作日志表]( 姓名,工作地点,时间);" );
}

//创建预处理命�?�?@ 字符作为 SQL 命名参数的前缀
var cmd = db.prepare("INSERT INTO [工作日志表] VALUES ( @姓名,@工作地点,@时间 );")

//执行命令语句,插入测试数据,并指�?SQL 命名参数
cmd.step(
    姓名 = "小张";
    工作地点 = "北京";
    时间 = time.now();
);

//插入测试数据,函数唯一的表参数首尾�?{ } 可以省略
cmd.step( {
    姓名 = "小王";
    工作地点 = "上海";
    时间 = time.now();
} );

//响应按钮事件
mainForm.button.oncommand = function(id,event){

    //查询一条数�?查询多条请改�?db.each() 或�?db.getTable() 函数
    var result  = db.stepQuery("SELECT * FROM [工作日志表] WHERE ??",{ {
        姓名 = mainForm.editUser.text;
    } } )
    /*
    SQL语句�?@ 字符开始的命名参数使用参数表的名值对元素格式�?
    SQL语句�?? �??? 占位符使用参数表的数组元素格式化,

    其中 ?? 格式化为标识�?其他占位符格式化为参数值�?    ??占位符用于格式化的参数如果是一个表，表中的键值对�?AND 为分隔符,并将数组值转换为IN语句�?    */

    if(result){
        mainForm.editResult.print( result.姓名 );
        mainForm.editResult.print( result.工作地点 );
        mainForm.editResult.print( result.时间 );
    }
}

mainForm.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/sqlite/Intro.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/sqlite/Intro.md')

