[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 输入法与键盘状态检�?
aardio 标准�?[key.ime](../../../library-reference/key/ime.html) 提供输入法相关函数�?
key.ime.state 函数则用于检测输入法与键盘状态，标准�?key.ime.stateBar 用于创建显示输入法状态的工具界面。基�?key.ime.stateBar 实现的开源软�?[ImTip](javascript:if(confirm('https://imtip.aardio.com/  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://imtip.aardio.com/') 目前已经成为了流行的桌面软件�?
## 一、输入法状态检测原理与规则

我们先了解两个用于表示输入法状态的变量�?
- opened: 活动窗口收到 WM\_IME\_CONTROL,IMC\_GETOPENSTATUS 消息返回的值�?- convMode: 活动窗口收到 WM\_IME\_CONTROL,IMC\_GETCONVERSIONMODE 消息返回的值�?
opened 用于表示当前是否打开输入法�?
convMode 则用于指示输入法的转换模式（中、英、标点符号、全角、半角等）�?
基本规则�?
- 输入法打开时，opened 应返回非零值（ 1 ），输入法关闭时 opened 则应返回 0 。输入法打开但是切换到英模式文时 opened 应当仍然返回 1，但 convMode 应当返回 0（IME\_CMODE\_ALPHANUMERIC）�?- 输入法关闭时，opened 应当返回 0�?  �?convMode 可能等于 1（IME\_CMODE\_NATIVE），也可能等�?0（IME\_CMODE\_ALPHANUMERIC�?�?  对于中文输入法，只有 OpenStatus �?1 并且 convMode & IME\_CMODE\_NATIVE 才表示中文输入状态�?- 中文输入法打开以后，无论中英输入模式，键盘布局�?HKL ）的语言 ID 都应�?0x804�?这与操作系统输入法设置中，中文输入法只能自中文键盘中添加的规则一致。有些老旧的输入法会强行添加「简体中文美式键盘」，这是不妥的，安装这种输入法会导致输入状态与键盘布局错乱。实际上 Windows 10 开始已经移除了这个键盘，应改为「英文美式键盘」�?- convMode & 0/\*IME\_CMODE\_ALPHANUMERI\*/ 表示默认英文字母数字输入模式
- opened �?1 时，convMode & 1/\*IME\_CMODE\_NATIVE\*/ 表示打开输入法，IME\_CMODE\_NATIVE 还有 IME\_CMODE\_CHINESE，IME\_CMODE\_JAPANESE，IME\_CMODE\_HANGUL 等别名�?- opened �?1 并且 onvMode & 1/\*IME\_CMODE\_NATIVE\*/ 时，convMode & 2/\*IME\_CMODE\_KATAKANA\*/ 表示日文片假名输入模式�?- convMode & 0x100/\*IME\_CMODE\_NOCONVERSION\*/ 表示关闭输入法，这时候即�?opened �?1 仍然表示关闭输入法。这种用法比较罕见�?- opened �?1 并且 convMode & 0x400/\*IME\_CMODE\_SYMBOL\*/ 为中文标点模式�?- convMode & 8/\*IME\_CMODE\_FULLSHAPE\*/ 为英文全角标点�?
convMode 还有一些其他状态，中文输入法一般用不到�?
[ImTip 检测输入法的实现源码](#key-ime-state)

## 二、输入法兼容�?
- 操作系统自带的所有微软输入法都返回了正确的状态，�?ImTip 可以完美兼容�?- 第三方输入法的实现各异，但在 [ImTip](javascript:if(confirm('https://imtip.aardio.com/  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ�����·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ���?'))window.location='https://imtip.aardio.com/') 发布后主流输入法大多兼容了上述规则�?- 个别输入法会返回错误的状态，主要分为以下三种情况�?[#](#quirksMode)


  1. 仅中英文标点�?convMode 状态是正确的，其他错误�?  2. opened 中文返回 2，英文返�?1，convMode 无效�?  3. 有时会返回正确的 opened �?convMode, 但一会正确一会错误，错误�?convMode 会无规律地变化为各种奇怪的数值。这种输入法还会干扰其他输入法导致别的输入法状态混乱�?
可尝试在不同窗口切换一下英文全半角、中英文标点等并查看 ImTip 能否正确显示状态，多切换几个窗口如果出错就是有问题。第 1、第 2 种情况可以在 ImTip 中勾选怪异模式解决�?不能同时安装多个有问题的输入法，因为 ImTip 会检测输入法列表并自动切换不同的兼容模式 ），�?3 种情况可能是该输入法问题比较严重，勾选怪异模式无法解决�?
至于第三方输入法工具则更为混乱，早年我写过文章，�?ImTip 发布之前网上流传的代码基本都是错的。例如有的开发者看到中文状态下 convMode 是某个数值就以为这个固定的数值就表示中文输入状态，其实这是未经过严谨测试望文生义，别人切换几个状态或者换个输入法你的程序就乱套了�?
## 三、key.ime.state 函数 [\#](\#key-ime-state)

ImTip 检测输入法状态的功能�?aardio 标准库的 key.ime.state 函数提供，此函数的关键源码如下：

```aardio aardio
namespace key.ime{

    conversionLangIds =  {[0x804] = 0x409;[0x404] = 0x409;[0xC04] = 0x409;[0x1404] = 0x409;[0x412] = 0x409;[0x0411] = 0x409} ;

    state = function(hwnd){
        if(!hwnd) {
            hwnd = ::User32.GetForegroundWindow();
            if(..winex) hwnd = ..winex.getFocus(hwnd,true) : hwnd;
        }

        var opened = getOpenStatus(hwnd);
        var convMode = getConversionMode(hwnd);
        var langId = getCurrentLangIdByHwnd(hwnd);

        if (opened && langId==0x409) opened = false;

        if(convMode === null) return false,,langId;

        var symbolMode = 1/*_IME_SYMBOLMODE_HALFSHAPE*/;
        if(!opened && (convMode==1 || convMode==0 ) && ! conversionLangIds[langId] ) symbolMode = 0;
        elseif( (convMode & 0x400/*_IME_CMODE_SYMBOL*/) && opened ) symbolMode = 3/*_IME_SYMBOLMODE_SYMBOL*/;
        elseif(convMode & 8/*_IME_CMODE_FULLSHAPE*/) symbolMode = 2/*_IME_SYMBOLMODE_FULLSHAPE*/;
        elseif(convMode & 0x100/*_IME_CMODE_NOCONVERSION*/) opened = false;

        /*
        首个返回值为是否启用输入转换（例如输入中、日、韩等文字），false 为英文输入状态，
        第二个返回�?symbolMode 用一个数值表示标点模式：
        1. 英文半角标点
        2. 英文全角标点
        3. 中文标点
        0. �?null 已关闭输入转�?        */
        return opened && (convMode & 3/*_IME_CMODE_LANGUAGE*/),symbolMode,langId,convMode;
    }
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/key/imeState.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/key/imeState.md')

