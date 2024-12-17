[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 閫氳繃 .NET 璋冪敤 UWP 鎺ュ彛

```aardio aardio
//aardio 閫氳繃 .NET 璋冪敤 UWP 鎺ュ彛
//鏍囧噯搴?dotNet.ocr, 鎵╁睍搴?dotNet.toastListener 閮借繍鐢ㄤ簡浠ヤ笅鏂规硶缂栬瘧 DLL 銆?import dotNet.uwpCompiler

/*
濡傛灉鍙傛暟@2 鏈寚瀹?Windows.winmd锛岄粯璁ゅ湪 C:\Program Files (x86)\Windows Kits\10\UnionMetadata
鏈�鏂扮増鏈琒DK鐩綍涓嬫煡鎵炬鏂囦欢锛岀敓鎴愮殑DLL绋嬪簭闆嗗苟涓嶄緷璧?Windows.winmd 鏂囦欢锛屼粎缂栬瘧鏃堕渶瑕併�?*/
var uwpCompiler = dotNet.uwpCompiler( "\ocr.dll" )//"~\lib\dotNet\ocr\.res\ocr.dll"

//鍚敤缂栬瘧浼樺寲
uwpCompiler.Parameters.CompilerOptions = "/optimize"

//璁剧疆寰呯紪璇慍#婧愮爜
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

//缂栬瘧骞惰繑鍥炵▼搴忛泦
var assembly = uwpCompiler.CompileOrFail();

import console;
if(assembly) console.logPause("缂栬瘧鎴愬姛",uwpCompiler.Parameters.OutputAssembly);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/uwpCompiler.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/uwpCompiler.md')

