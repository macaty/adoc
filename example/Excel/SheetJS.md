[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: web.view - 鎿嶄綔 Excel 琛ㄦ牸

```aardio aardio
//SheetJS
import win.ui;
/*DSG{{*/
var winform = win.form(text="web.view - 鎿嶄綔 Excel 琛ㄦ牸";right=800;bottom=469;bgcolor=16777215)
winform.add()
/*}}*/

import web.view;
var wb = web.view(winform);

//瀵煎嚭 aardio 鍑芥暟缁?JavaScript
wb.external = {
    saveXlsxFile = function(buffer,filename){
        import crypt;
        import process;

        var buffer = crypt.decodeBin(buffer);
        string.save(filename,buffer);

        process.exploreSelect(filename);
    };
}

wb.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <style type="text/css">
    html,body{ height:100%; margin:0; }
    </style>
    <script src="https://cdn.bootcdn.net/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <script src="https://lf26-cdn-tos.bytecdntp.com/cdn/expire-1-M/handsontable/8.3.2/handsontable.full.min.js"></script>
    <link rel="stylesheet" href="https://lf26-cdn-tos.bytecdntp.com/cdn/expire-1-M/handsontable/8.3.2/handsontable.full.min.css" />
</head>
<body>
    <div id="header"></div>
    <div id="container">
        <div class="lside"> </div>
        <div class="rside"> </div>
    </div>
</body>

<script type="text/javascript">

    //https://docs.sheetjs.com/docs/api/parse-options

    let data = [
        ['bookType', 'extension', 'sheets', 'Description'],
        ['xlsx', '.xlsx', 'multi', 'Excel 2007+ XML Format'],
        ['xlsb', '.xlsb', 'multi', 'Excel 2007+ Binary Format'],
    ]

    //鍒涘缓宸ヤ綔绨?    let book = XLSX.utils.book_new()

    //鍒涘缓宸ヤ綔琛?    let sheet = XLSX.utils.aoa_to_sheet(data)
    XLSX.utils.book_append_sheet(book, sheet, 'Sheet1')

    //杈撳嚭涓烘枃浠?    var xlsxData = XLSX.write(book,{bookType:"xlsx",type:"base64"})

    //浣滀负鍙傛暟浼犵粰 aardio 鍑芥暟
    aardio.saveXlsxFile(xlsxData,"/test.xlsx")

    //璇诲彇 XLSX 鏂囦欢
    let book2 = XLSX.read(xlsxData , {bookType:"xlsx",type:"base64"})

    //杈撳嚭涓?HTML 琛ㄦ牸
    let sheet1 = book2.Sheets[book2.SheetNames[0]]
    //document.body.innerHTML = XLSX.utils.sheet_to_html( sheet1 );

    //杞崲涓烘暟缁?    let array = XLSX.utils.sheet_to_json(sheet1);

    //鏄剧ず Excel
    const hot = new Handsontable(document.body, {
        data: array,
        rowHeaders: true,
        colHeaders: true,
        height: 'auto',
        autoWrapRow: true,
        autoWrapCol: true,
        licenseKey: 'non-commercial-and-evaluation'
    });
</script>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Excel/SheetJS.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Excel/SheetJS.md')

