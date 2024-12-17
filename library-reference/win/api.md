[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.api 库模块帮助文�?
## win 成员列表

### win.api

用于声明 win 用到的全局 WinAPI

### 全局常量

### ::BeginDeferWindowPos

```aardio aardio
::User32.api( "BeginDeferWindowPos", "ptr(int numWins)" )

```

### ::CallWindowProc

```aardio aardio
::User32.api("CallWindowProc","int(ptr lpPrevWndFunc,addr hwnd,INT Msg,ADDR wParam,addr lParam)" )

```

### ::ClientToScreen

```aardio aardio
::User32.api( "ClientToScreen", " int(addr hwnd,struct &lpPoint ) " )

```

### ::CopyImage

```aardio aardio
::User32.api("CopyImageW", "ptr(ptr hlmage, INT uType,int cx,int cy,INT flags)")

```

### ::CreateWindowEx

```aardio aardio
::User32.api( "CreateWindowExW", " int(INT exStyle,ustring className,ustring windowName,INT style,int x,int y,int width,int height,addr hwndParent,addr hMenu,pointer hlnstance,ptr lpParam)" )

```

### ::DefWindowProc

```aardio aardio
::User32.api( "DefWindowProc", "int(addr hwnd,INT msg,ADDR wParam,addr lParam) " );

```

### ::DeferWindowPos

```aardio aardio
::User32.api( "DeferWindowPos", "ptr(PTR hWinPo,addr hwnd,addr instAffer,int x,int y, int cx, int Cy,INT fags)" )

```

### ::DestroyCursor

```aardio aardio
::User32.api("DestroyCursor","int(ptr hCursor)")

```

### ::DestroyIcon

```aardio aardio
::User32.api("DestroyIcon","int(ptr hIcon)")

```

### ::DestroyWindow

```aardio aardio
::User32.api( "DestroyWindow", "int(addr hwnd )" );

```

### ::EndDeferWindowPos

```aardio aardio
::User32.api( "EndDeferWindowPos", "bool(PTR hWinPos)" )

```

### ::GetClassInfoEx

```aardio aardio
::User32.api("GetClassInfoEx", "int(ptr,utf16,struct&)")

```

### ::GetClientRect

```aardio aardio
::User32.api( "GetClientRect", " int(addr hwnd,struct &lpRect ) " )

```

### ::GetCursor

```aardio aardio
::User32.api("GetCursor","ptr()")

```

### ::GetSystemMetrics

```aardio aardio
::User32.api("GetSystemMetrics","int(int)")

```

### ::GetWindowLong

```aardio aardio
::User32.api("GetWindowLong","int(addr hwnd,int nIndex)" )

```

### ::GetWindowRect

```aardio aardio
::User32.api( "GetWindowRect", " int(addr hwnd,struct &lpRect ) " )

```

### ::InvalidateRect

```aardio aardio
::User32.api( "InvalidateRect", " int(addr hwnd,struct rect,bool erase) " )

```

### ::LoadBitmap

```aardio aardio
::User32.api("LoadBitmapW", "ptr(ptr,ustring)")

```

### ::LoadCursor

```aardio aardio
::User32.api("LoadCursorW", "ptr(ptr,ustring)")

```

### ::LoadIcon

```aardio aardio
::User32.api("LoadIconW", "ptr(ptr,ustring)")

```

### ::LoadImage

```aardio aardio
::User32.api("LoadImageW", "ptr(ptr hInst,ustring name,INT uType,int cxDesired,int CyDesire,INT fuLoad)")

```

### ::MapWindowPoints

```aardio aardio
::User32.api( "MapWindowPoints", "int(addr from,addr to,struct &points,INT len)");

```

### ::MoveWindow

```aardio aardio
::User32.api( "MoveWindow", "int( addr hwnd, int x,int y,int w,int h,bool repaint)" )

```

### ::PostMessage

```aardio aardio
::User32.api("PostMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")

```

### ::PostThreadMessage

```aardio aardio
::User32.api("PostThreadMessageW","addr(int idThread,INT msg,ADDR wParam,addr lParam)");

```

### ::PtInRect

```aardio aardio
::User32.api( "PtInRect", "int(struct, int, int)" );

```

### ::RedrawWindow

```aardio aardio
::User32.api("RedrawWindow","bool(addr hwnd,struct lprcUpdate,ptr hrgnUpdate,INT flags)");

```

### ::RegisterClassEx

```aardio aardio
::User32.api( "RegisterClassEx", " word(struct wc) " )

```

### ::RegisterWindowMessage

```aardio aardio
::User32.api("RegisterWindowMessageW","INT(ustring)");

```

### ::ScreenToClient

```aardio aardio
::User32.api( "ScreenToClient", " int(addr hwnd,struct &lpPoint ) " )

```

### ::SendMessage

```aardio aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam)")

```

### ::SendMessageByInt

```aardio aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,int &wParam,int &lParam)")

```

### ::SendMessageByStr

```aardio aardio
::User32.api("SendMessageW","addr(int,INT,int,ustring &lParam)")

```

### ::SendMessageByString

```aardio aardio
::User32.api("SendMessageW","addr(int,INT,int,string &lParam)")

```

### ::SendMessageByStruct

```aardio aardio
::User32.api("SendMessageW","addr(int,INT,int,struct &lParam)")

```

### ::SendMessageInt

```aardio aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")

```

### ::SendMessageTimeout

```aardio aardio
::User32.api("SendMessageTimeoutW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam,INT flags,INT timeout,int & resultult)")

```

### ::SetCursor

```aardio aardio
::User32.api("SetCursor","int(ptr hCur)")

```

### ::SetWindowLong

```aardio aardio
::User32.api("SetWindowLong","int(addr hwnd,int nIndex,int dwNewLong)" )

```

### ::SetWindowPointer

```aardio aardio
::User32.api("SetWindowLong","ptr(addr hwnd,int nIndex,ptr ptrNew)" )

```

### ::SetWindowPos

```aardio aardio
::User32.api("SetWindowPos","boolean(addr hwnd,addr hwndlnsertAfter,int X,int Y,int cx,int cy,int Flags)")

```

### ::SystemParametersInfo

```aardio aardio
::User32.api("SystemParametersInfo","int(INT act, INT param, struct& pvParam,INT winIni)");

```

### ::UpdateWindow

```aardio aardio
::User32.api( "UpdateWindow", "bool(addr) " )

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/api.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/api.md')

