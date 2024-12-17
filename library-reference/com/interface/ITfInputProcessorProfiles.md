[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# com.interface.ITfInputProcessorProfiles 库模块帮助文�?
## com.interface.ITfInputProcessorProfiles 成员列表

### com.interface.ITfInputProcessorProfiles.Create()

创建输入法配置接口对�?
[返回对象:ITfInputProcessorProfilesObject](#ITfInputProcessorProfilesObject)

## ITfInputProcessorProfilesObject 成员列表

### ITfInputProcessorProfilesObject.GetLanguageProfileDescription(languageProfile)

获取输入语言描述

### ITfInputProcessorProfilesObject.GetLanguageProfileDescription(rclsid,langid,guidProfile)

获取输入语言描述

### ITfInputProcessorProfilesObject.activeProfileByDescription()

按参数指定的描述激活输入语言配置文件

### ITfInputProcessorProfilesObject.each(langid)

```aardio aardio
for( languageProfile in ITfInputProcessorProfilesObject.each() ){
    /*遍历输入语言配置文件*/
}

```

### ITfInputProcessorProfilesObject.findProfileByDescription()

按参数指定的描述查找输入语言配置文件

返回TF\_LANGUAGEPROFILE结构�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/com/interface/ITfInputProcessorProfiles.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/com/interface/ITfInputProcessorProfiles.md')

