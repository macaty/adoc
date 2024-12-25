[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: mysql.client �?- 登录插件

```aardio aardio
//mysql.client �?- 登录插件
import console;
import mysql.client;
//导入 caching_sha2_password 插件（MySQL 8.0 默认登录认证方式），
import mysql.plugin.cachingSha2Password;

/*
本地登录没必要启用这个插件，可用下面�?SQL 禁用 caching_sha2_password�?ALTER USER '用户�?@'localhost' IDENTIFIED WITH mysql_native_password BY '密码';
*/

console.showLoading(" 正在连接测试数据�? )
var dbClient,err = mysql.client(
    server = "db4free.net"; //数据库服务器,可省略默认为localhost
    uid = "aardio_mysql";//用户�?可省略默认为root
    pwd = "aardio.com";
);

if(!dbClient){
    console.log("如果是有人无聊修改了密码,请自行到 db4free.net 申请免费数据�?)
    return console.logPause(err);
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/mysql/plugin.md)

