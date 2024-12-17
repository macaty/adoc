[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.wxmp.message 库模块帮助文�?
## web.wxmp 成员列表

### web.wxmp.message

微信公众号消息接口，目前仅支持明文消息�?
### web.wxmp.message()

参数指定消息令牌（公众号开发服务器配置中查看）�?
创建对象时会自动鉴权，令牌校验失败自动退出本次请求�?
调用代码不需要再检测鉴权结果�?
[返回对象:webWxmpMessageObject](#webWxmpMessageObject)

## webWxmpMessageObject 成员列表

### webWxmpMessageObject.requestXml()

解析服务器请�?XML，返回数据表对象（table 对象）�?
webWxmpMessageReq.

### webWxmpMessageObject.responseXml()

```aardio aardio
webWxmpMessageObject.responseXml(
    ToUserName = postData.FromUserName;
    FromUserName = postData.ToUserName;
    MsgType = "news";
    ArticleCount = 1;
    Articles = {
        item = {
            {
                Title = "标题";
                Description = "描述";
                PicUrl =  "图像网址";
                Url =  "文章网址";
            }
        }
    };
    /*将参数中的表对象转换�?XML 并输出为 HTTP 应答数据�?表中的键值按公众号格式生成为 XML 节点�?如果值为表，则表中的键值对生成�?XML 子节点�?如果表为数组，则表中的数组项生成为同�?XML 子节点数组（上面�?item 就是数组�?这里演示�?postData 应为 requestXml 解析的请求数据�?CreateTime 会自动添加到应答 XML，不需要指定�?/
)

```

## webWxmpMessageReq 成员列表

### webWxmpMessageReq.Content

文本消息内容

### webWxmpMessageReq.CreateTime

请求时间�?
### webWxmpMessageReq.Event

事件类型，例�?"subscribe"

### webWxmpMessageReq.EventKey

事件 KEY �?
### webWxmpMessageReq.FromUserName

用户 OpenID

### webWxmpMessageReq.Idx

多图文时是第几篇文章，仅来自文章才有这个字段

### webWxmpMessageReq.MsgDataId

消息的数�?ID，仅来自文章才有这个字段

### webWxmpMessageReq.MsgId

消息 ID�?4 位整数，注意这是字符�?
### webWxmpMessageReq.MsgType

消息类型，例�?"event",

### webWxmpMessageReq.PicUrl

图像地址

### webWxmpMessageReq.ToUserName

开发者微信号

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/wxmp/message.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/wxmp/message.md')

