[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: UPnP 绔彛鏄犲皠鏌ョ湅宸ュ叿

```aardio aardio
//绔彛鏄犲皠绠＄悊
import win.ui;
/*DSG{{*/
var winform = win.form(text="UPnP 绔彛鏄犲皠鏌ョ湅宸ュ叿";right=966;bottom=622)
winform.add()
/*}}*/

import web.view;
var wb = web.view(winform);

import sys.upnp.nat;
var natUpnp = sys.upnp.nat();

//娴嬭瘯娣诲姞绔彛鏄犲皠锛岄櫎绗竴涓弬鏁颁互澶栫殑鍏朵粬鍙傛暟閮藉彲浠ョ渷鐣?natUpnp.add(9973,"TCP",9973,,"娣诲姞绔彛鏄犲皠娴嬭瘯")

wb.external = {
    getMappingCollection = function(){
        return web.json.stringifyArray(natUpnp.getTable());
    };
    deleteItem = function(externalPort,protocol){
        return natUpnp.remove(externalPort,protocol)
    };
    natUpnpValid = function(){
        return natUpnp.valid();
    };
}

wb.html = /**
<!DOCTYPE html><html>
<head>
    <meta charset="utf-8" />
    <title>WebView2</title>
    <script src="https://lib.baomitu.com/react/17.0.2/umd/react.production.min.js"></script>
    <script src="https://lib.baomitu.com/react-dom/17.0.2/umd/react-dom.production.min.js"></script>
    <script src="https://lib.baomitu.com/antd/4.17.0-alpha.3/antd.min.js"></script>
    <link rel="stylesheet" href="https://lib.baomitu.com/antd/4.17.0-alpha.3/antd.min.css">
    <script src="https://unpkg.com/@babel/standalone@7/babel.min.js"></script>
    <style type="text/css">
    </style>
</head>
<body>

<script type="text/babel">
    const { useState,useEffect,useCallback,useRef } =  React;
    const { Button,Table,DatePicker,Alert,Tooltip,Space,Tag,Popconfirm } = antd;

    const App = () => {
            const [data,setData] = useState([]);
            const [valid,setValid] = useState(true);

            useEffect(
                async ()=> {
                    var ds = JSON.parse(await aardio.getMappingCollection());
                    setData(ds);

                    if(!ds.length){
                        setValid(await aardio.natUpnpValid());
                    }
                },[]
            )

            return (
                <div style={{ width: '100%', margin: '0 auto', padding:'10px' }}>
                { !valid && <Alert message="褰撳墠缃戠粶涓嶆敮鎸?UPnP 鑷姩绔彛鏄犲皠" type="error" showIcon  closable  /> }
                <Table size="middle"  dataSource={data} columns={[
                        {
                            title: '鍗忚',
                            dataIndex: 'protocol',
                            width: 300,
                        },
                        {
                            title: '澶栫綉绔彛',
                            dataIndex: 'externalPort',
                        },
                        {
                            title: '鍐呯綉绔彛',
                            dataIndex: 'internalPort',
                        },
                        {
                            title: '鍐呯綉涓绘満',
                            dataIndex: 'internalClient',
                        },
                        {
                            title: '鎻忚堪',
                            dataIndex: 'description',
                        },
                        {
                            title: '鍚敤',
                            dataIndex: 'enabled',
                            render: enabled => (
                                <>
                                    <Tag color={ enabled  ? 'green' : '#CCC' } >
                                        {enabled ? "鍚敤" : "绂佺敤"}
                                    </Tag>
                                </>)
                        },
                        {
                            title: '鎿嶄綔',
                            key: 'action',
                            render: (text, record) => (
                            <Space size="middle">
                                <Popconfirm title={"纭畾鍒犻櫎澶栫綉鏄犲皠绔彛锛?+record.externalPort+" 鍗忚锛?+record.protocol+" 鍚?} onConfirm={ async ()=>{
                                    await aardio.deleteItem(record.externalPort,record.protocol)
                                    setData(JSON.parse(await aardio.getMappingCollection()));
                                } } okText="纭" cancelText="鍙栨秷">
                                    <a>鍒犻櫎</a>
                                </Popconfirm>
                            </Space>
                            ),
                        },
                ]} />

                </div>
            );
    };

    ReactDOM.render(<App />, document.querySelector('#app'));
</script>

<div id="app"></div>
</body>
**/

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/sys.upnp.nat.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/sys.upnp.nat.md')

