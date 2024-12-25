[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.size 库模块帮助文�?
## fsys.size 成员列表

### fsys.size.GB

```aardio aardio
0x40000000;

```

### fsys.size.KB

```aardio aardio
0x400;

```

### fsys.size.MB

```aardio aardio
0x100000;

```

### fsys.size.bytes

```aardio aardio
1;

```

### fsys.size.format(长度,长度高位,单位大小,精度)

格式化大�?所有参数可�?
默认自动计算最大单位大�?精度默认为最�?位小�?
返回值依次为:大小,单位大小,单位名称

建议改用math.size64实现此函数的功能

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/size.md)

