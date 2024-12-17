[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 取硬盘序列号

```aardio aardio
//取硬盘序列号
import console;

//方法一：得到所有硬盘序�?分区�?import sys.storage;
var devices = sys.storage.getDevices()
for(idx,drives in devices){
    var property = sys.storage.queryProperty( idx );
    if(!property) continue ;
    console.log( property.productId )
    console.log( property.serialNumber )
    for(j=1;#drives;1){
        console.log( drives[j] )
    }
}

//方法二：取所有分区信息、分区序列号
import sys.volume;
var drives = sys.volume.getLogicalDrives()
for(i,drv in drives){
    var info = sys.volume.getInfo( drv)  ;
    if(info)
          console.log(
            "分区:"+info.drive,
            "序列�?+ info.serial,
            info.serialNum,"文件系统:" + info.fsys,
            "压缩:" + ((info.flag & 0x8000/*_FILE_VOLUME_IS_COMPRESSED*/) ? "�? : "�?)
            );

}

import sys.hd; //需要管理权�?console.log( "物理序列�?, ..sys.hd.getInfo()[["sSerialNumber"]] );

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Storage/storage.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Storage/storage.md')

