[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.api 库模块帮助文�?
## win 成员列表

### win.api

用于声明 win 用到的全局 WinAPI

### 全局常量

### ::BeginDeferWindowPos

````aardio aardio
::User32.api( "BeginDeferWindowPos", "ptr(int numWins)" )
```

<a id="::CallWindowProc"></a>
### ::CallWindowProc
 ```aardio
::User32.api("CallWindowProc","int(ptr lpPrevWndFunc,addr hwnd,INT Msg,ADDR wParam,addr lParam)" )
```

<a id="::ClientToScreen"></a>
### ::ClientToScreen
 ```aardio
::User32.api( "ClientToScreen", " int(addr hwnd,struct &lpPoint ) " )
```

<a id="::CopyImage"></a>
### ::CopyImage
 ```aardio
::User32.api("CopyImageW", "ptr(ptr hlmage, INT uType,int cx,int cy,INT flags)")
```

<a id="::CreateWindowEx"></a>
### ::CreateWindowEx
 ```aardio
::User32.api( "CreateWindowExW", " int(INT exStyle,ustring className,ustring windowName,INT style,int x,int y,int width,int height,addr hwndParent,addr hMenu,pointer hlnstance,ptr lpParam)" )
```

<a id="::DefWindowProc"></a>
### ::DefWindowProc
 ```aardio
::User32.api( "DefWindowProc", "int(addr hwnd,INT msg,ADDR wParam,addr lParam) " );
```

<a id="::DeferWindowPos"></a>
### ::DeferWindowPos
 ```aardio
::User32.api( "DeferWindowPos", "ptr(PTR hWinPo,addr hwnd,addr instAffer,int x,int y, int cx, int Cy,INT fags)" )
```

<a id="::DestroyCursor"></a>
### ::DestroyCursor
 ```aardio
::User32.api("DestroyCursor","int(ptr hCursor)")
```

<a id="::DestroyIcon"></a>
### ::DestroyIcon
 ```aardio
::User32.api("DestroyIcon","int(ptr hIcon)")
```

<a id="::DestroyWindow"></a>
### ::DestroyWindow
 ```aardio
::User32.api( "DestroyWindow", "int(addr hwnd )" );
```

<a id="::EndDeferWindowPos"></a>
### ::EndDeferWindowPos
 ```aardio
::User32.api( "EndDeferWindowPos", "bool(PTR hWinPos)" )
```

<a id="::GetClassInfoEx"></a>
### ::GetClassInfoEx
 ```aardio
::User32.api("GetClassInfoEx", "int(ptr,utf16,struct&)")
```

<a id="::GetClientRect"></a>
### ::GetClientRect
 ```aardio
::User32.api( "GetClientRect", " int(addr hwnd,struct &lpRect ) " )
```

<a id="::GetCursor"></a>
### ::GetCursor
 ```aardio
::User32.api("GetCursor","ptr()")
```

<a id="::GetSystemMetrics"></a>
### ::GetSystemMetrics
 ```aardio
::User32.api("GetSystemMetrics","int(int)")
```

<a id="::GetWindowLong"></a>
### ::GetWindowLong
 ```aardio
::User32.api("GetWindowLong","int(addr hwnd,int nIndex)" )
```

<a id="::GetWindowRect"></a>
### ::GetWindowRect
 ```aardio
::User32.api( "GetWindowRect", " int(addr hwnd,struct &lpRect ) " )
```

<a id="::InvalidateRect"></a>
### ::InvalidateRect
 ```aardio
::User32.api( "InvalidateRect", " int(addr hwnd,struct rect,bool erase) " )
```

<a id="::LoadBitmap"></a>
### ::LoadBitmap
 ```aardio
::User32.api("LoadBitmapW", "ptr(ptr,ustring)")
```

<a id="::LoadCursor"></a>
### ::LoadCursor
 ```aardio
::User32.api("LoadCursorW", "ptr(ptr,ustring)")
```

<a id="::LoadIcon"></a>
### ::LoadIcon
 ```aardio
::User32.api("LoadIconW", "ptr(ptr,ustring)")
```

<a id="::LoadImage"></a>
### ::LoadImage
 ```aardio
::User32.api("LoadImageW", "ptr(ptr hInst,ustring name,INT uType,int cxDesired,int CyDesire,INT fuLoad)")
```

<a id="::MapWindowPoints"></a>
### ::MapWindowPoints
 ```aardio
::User32.api( "MapWindowPoints", "int(addr from,addr to,struct &points,INT len)");
```

<a id="::MoveWindow"></a>
### ::MoveWindow
 ```aardio
::User32.api( "MoveWindow", "int( addr hwnd, int x,int y,int w,int h,bool repaint)" )
```

<a id="::PostMessage"></a>
### ::PostMessage
 ```aardio
::User32.api("PostMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")
```

<a id="::PostThreadMessage"></a>
### ::PostThreadMessage
 ```aardio
::User32.api("PostThreadMessageW","addr(int idThread,INT msg,ADDR wParam,addr lParam)");
```

<a id="::PtInRect"></a>
### ::PtInRect
 ```aardio
::User32.api( "PtInRect", "int(struct, int, int)" );
```

<a id="::RedrawWindow"></a>
### ::RedrawWindow
 ```aardio
::User32.api("RedrawWindow","bool(addr hwnd,struct lprcUpdate,ptr hrgnUpdate,INT flags)");
```

<a id="::RegisterClassEx"></a>
### ::RegisterClassEx
 ```aardio
::User32.api( "RegisterClassEx", " word(struct wc) " )
```

<a id="::RegisterWindowMessage"></a>
### ::RegisterWindowMessage
 ```aardio
::User32.api("RegisterWindowMessageW","INT(ustring)");
```

<a id="::ScreenToClient"></a>
### ::ScreenToClient
 ```aardio
::User32.api( "ScreenToClient", " int(addr hwnd,struct &lpPoint ) " )
```

<a id="::SendMessage"></a>
### ::SendMessage
 ```aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam)")
```

<a id="::SendMessageByInt"></a>
### ::SendMessageByInt
 ```aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,int &wParam,int &lParam)")
```

<a id="::SendMessageByStr"></a>
### ::SendMessageByStr
 ```aardio
::User32.api("SendMessageW","addr(int,INT,int,ustring &lParam)")
```

<a id="::SendMessageByString"></a>
### ::SendMessageByString
 ```aardio
::User32.api("SendMessageW","addr(int,INT,int,string &lParam)")
```

<a id="::SendMessageByStruct"></a>
### ::SendMessageByStruct
 ```aardio
::User32.api("SendMessageW","addr(int,INT,int,struct &lParam)")
```

<a id="::SendMessageInt"></a>
### ::SendMessageInt
 ```aardio
::User32.api("SendMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")
```

<a id="::SendMessageTimeout"></a>
### ::SendMessageTimeout
 ```aardio
::User32.api("SendMessageTimeoutW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam,INT flags,INT timeout,int & resultult)")
```

<a id="::SetCursor"></a>
### ::SetCursor
 ```aardio
::User32.api("SetCursor","int(ptr hCur)")
```

<a id="::SetWindowLong"></a>
### ::SetWindowLong
 ```aardio
::User32.api("SetWindowLong","int(addr hwnd,int nIndex,int dwNewLong)" )
```

<a id="::SetWindowPointer"></a>
### ::SetWindowPointer
 ```aardio
::User32.api("SetWindowLong","ptr(addr hwnd,int nIndex,ptr ptrNew)" )
```

<a id="::SetWindowPos"></a>
### ::SetWindowPos
 ```aardio
::User32.api("SetWindowPos","boolean(addr hwnd,addr hwndlnsertAfter,int X,int Y,int cx,int cy,int Flags)")
```

<a id="::SystemParametersInfo"></a>
### ::SystemParametersInfo
 ```aardio
::User32.api("SystemParametersInfo","int(INT act, INT param, struct& pvParam,INT winIni)");
```

<a id="::UpdateWindow"></a>
### ::UpdateWindow
 ```aardio
::User32.api( "UpdateWindow", "bool(addr) " )
```

[Markdown 格式](api.md)

````

