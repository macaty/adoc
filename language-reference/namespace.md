[aardio 文档](../index.htm "aardio 编程语言文档首页")

# aardio 名字空间

## 什么是名字空间

名字空间组织、归类、标识一组具名对象的名字，是模块化编程的重要基础�?
- 在名字空间内部定义的对象名字由名字空间管理�?
- 引用外部名字空间的名字时需要在对象名字前添加名字空间前缀�?
- 不同的名字空间中可以有相同的名字而互不干扰，有效的避免了名字污染�?
- 一个名字空间可以包含另一个名字空间，这些名字之间使用成员操作�?`.` 连接为完整的名字空间路径�?

## 定义名字空间

aardio 使用 namespace 语句定义名字空间�?
如果一个不存在的变量首次被赋�? var 语句声明的局部变量除�?，则会自动加入到当前名字空间�?
请参考： [赋值语句](statements/assignment.html)

定义名字空间语法�?
```aardio aardio
namespace namespaceName{
  //名字空间内部代码
}

```

名字空间可以嵌套，默认每�?namespace 语句总是在当前名字空间内部创建新的名字空间，如下�?
```aardio aardio
namespace namespaceName1{

    namespace namespaceName2{

        //名字空间内部代码
    }
}

namespaceName1.namespaceName2.member = 123

```

名字空间也可以省略语句块标记，表示名字空间作用域直至该代码文件结束：

```aardio aardio
namespace namespaceName

//名字空间内部代码，名字空间的作用域直到文件结�?
```

如果在名字空间前面加上两个连续的小圆�?`..` 作为前缀，则该名字空间为全局名字，如下：

```aardio aardio
import console;
namespace namespaceName{

    namespace ..globalNamespaceName{

        //名字空间内部代码
        member = 123
    }
}

console.log( globalNamespaceName.member );

console.pause(true);

```

要点�?
- 名字空间其实也是一个普通的 table 对象�?
- 访问非当前名字空间的成员变量，可以加上有效的名字空间前缀�?- 访问顶层名字空间要使�?`..` 操作符�?
## global �?self 名字空间

1. global [#](#global)

global 为默认的全局名字空间，当aardio代码文件加载时，默认都运行在 global 名字空间�?
1. self [#](#self)

self 表示当前名字空间�?
默认的名字空间为 global，也就是�?self 默认指向 global�?
## import 语句 [\#](\#import)

import 语句可以将外部名字空间导入当前名字空间（并且总是会同时导入全局名字空间）�?
标准库通常都是将外部名字空间导入到 global 名字空间，并且在非全局名字空间中使�?`..` 操作符访问其他全局名字空间�?
```aardio aardio
//�? console 库导�?console 名字空间
import console;

//定义新的名字空间
namespace namespaceName{

    //非全局名字空间使用  .. 操作符访问其他全局名字空间�?    ..console.log("调用导入�?console 库函�?)
}

console.pause();

```

如果导入未定义的名字空间，import 语句会尝试自库文件导入名字空间�?
aardio 库文件的物理路径与名字空间路径保持一致，对于模块化编程提供良好的支持�?
注意：名字空间不能是单个下划�?可以包含下划�?! aardio 使用 `_.aardio` 文件创建库目录下的默认库，除此之�?aardio 不建议在库名字空间中使用任何下划线。如果在 IDE 中右键创建库或改动库名，aardio 将会自动移除下划线。如果您一定要在库名字中包含下划，则必须在资源管理器中手动改名�?
请参�? [import](../library-guide/import.html)

## with 语句 [\#](\#with)

with 语句用于将一个表达式返回�?table 对象绑定为当前名字空间，with 语句执行结束释放绑定。名字空间作用域为当前函数体（以及内部函数），单个代码文件属于匿名函数�?
with 语句必须执行完成（没有中途跳出）才能恢复当前函数名字空间�?
示例�?
```aardio aardio
import console;

var tab = {}

with tab{
    name = "测试";
    ..console.log(name);
}

console.logPause( tab.name )

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/namespace.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/namespace.md')

