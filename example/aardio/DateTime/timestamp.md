[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 时间�?
```aardio aardio
//时间�?//Unix 时间�?0 表示 ISO8601 时间 1970-01-01T00:00:00Z
import console.int;
import fsys.time;

//Unix 时间戳，返回数值，以毫秒为单位
var stamp = time.stamp();
console.log(stamp);

//Unix 时间戳，返回字符串，以毫秒为单位
var stamp = time.stamp(true);
console.log(stamp);

//Unix 时间戳，返回字符串，以秒为单�?var stamp = time.stamp(true,1);
console.log(stamp);

//Unix 时间戳，以秒为单�?var stamp = tonumber( time() );
console.log(stamp);

//Unix 时间戳，返回字符串，以毫秒为单位
var fileTime = fsys.time().now();
var stamp = fileTime.stamp(true);
console.log(stamp);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/timestamp.md)

