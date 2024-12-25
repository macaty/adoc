[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过 .NET 调用 UWP 接口

```aardio aardio
//aardio 通过 .NET 调用 UWP 接口
//标准�?dotNet.ocr, 扩展�?dotNet.toastListener 都运用了以下方法编译 DLL �?import dotNet.uwpCompiler

/*
如果参数@2 未指�?Windows.winmd，默认在 C:\Program Files (x86)\Windows Kits\10\UnionMetadata
最新版本SDK目录下查找此文件，生成的DLL程序集并不依�?Windows.winmd 文件，仅编译时需要�?*/
var uwpCompiler = dotNet.uwpCompiler( "\ocr.dll" )//"~\lib\dotNet\ocr\.res\ocr.dll"

//启用编译优化
uwpCompiler.Parameters.CompilerOptions = "/optimize"

//设置待编译C#源码
uwpCompiler.Source = /******
using System;
using System.Reflection;
using System.Collections;
using System.Collections.Generic;
using System.IO;
using System.Threading.Tasks;
using Windows.Graphics.Imaging;
using Windows.Storage;
using Windows.Storage.Streams;
using System.Runtime.InteropServices;
using Windows.Media.Ocr;

namespace aardio
{
    public class UwpOcrResult
    {

        public UwpOcrResult(OcrResult ocrRet)
        {
            ocrResult = ocrRet;
        }

        public int LineCount()
        {
            return ocrResult.Lines.Count;
        }

        public string [] GetWords(int index)
        {
            ArrayList arr = new ArrayList();
            foreach (var word in ocrResult.Lines[index].Words)
            {
                arr.Add(word.Text);
            }

            return (string[])arr.ToArray(typeof(string));
        }

        public object GetWordRects(int index)
        {
            ArrayList arr = new ArrayList();
            foreach (var word in ocrResult.Lines[index].Words)
            {
                double[] rc = { word.BoundingRect.Left, word.BoundingRect.Top, word.BoundingRect.Right, word.BoundingRect.Bottom };
                arr.Add(rc);
            }

            return (object)arr.ToArray(typeof(object));
        }

        private OcrResult ocrResult;

    }

    public class UwpOcrEngine
    {
        public string [] AvailableRecognizerLanguages(){
            ArrayList arr = new ArrayList();
            foreach (var lang in OcrEngine.AvailableRecognizerLanguages)
            {
                arr.Add(lang.LanguageTag);
            }
            return (string [])arr.ToArray(typeof( string));
        }

        public object IsLanguageSupported( string name ){
            Windows.Globalization.Language lang = new Windows.Globalization.Language(name);
            return OcrEngine.IsLanguageSupported(lang);
        }

        public UwpOcrResult Recognize(byte[] imgBuffer, string language){
            return new UwpOcrResult( RecognizeAsync(imgBuffer, language).GetAwaiter().GetResult() );
        }

        async Task<OcrResult> RecognizeAsync(byte[] imgBuffer, string language)
        {
                var randomAccessStream = new InMemoryRandomAccessStream();
                var outputStream = randomAccessStream.GetOutputStreamAt(0);
                var dw = new DataWriter(outputStream);
                var task = new Task(() => dw.WriteBytes(imgBuffer));
                task.Start();
                await task;
                await dw.StoreAsync();
                await outputStream.FlushAsync();

                BitmapDecoder decoder = await BitmapDecoder.CreateAsync(randomAccessStream);
                SoftwareBitmap softwareBitmap = await decoder.GetSoftwareBitmapAsync(BitmapPixelFormat.Bgra8, BitmapAlphaMode.Premultiplied);
                Windows.Globalization.Language lang = new Windows.Globalization.Language(language);

                OcrEngine engine = OcrEngine.TryCreateFromLanguage(lang);
                if (engine != null)
                {
                    OcrResult ocrResult = await engine.RecognizeAsync(softwareBitmap);
                    return ocrResult;
                }

                return null;
        }
    }
}
******/

//编译并返回程序集
var assembly = uwpCompiler.CompileOrFail();

import console;
if(assembly) console.logPause("编译成功",uwpCompiler.Parameters.OutputAssembly);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/uwpCompiler.md)

