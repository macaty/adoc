[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 脚本调用本地函数

```aardio aardio
//Preact
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 脚本调用本地函数";right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

sciter.external = {
    func = function(str){
         return "Hello, "+str+"!";
    }
}

sciter.html = /**
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
    <script src="https://lib.baomitu.com/preact/10.5.14/preact.umd.min.js"/>
    <script src="https://lib.baomitu.com/preact/10.5.14/hooks.umd.min.js"/>
    <title>Document</title>
</head>
<script type="module">
    const { h, render, Component } = preact;
    const { useState, useEffect, useCallback } = preactHooks;
    JSX = h;

    function Counter() {
      const [value, setValue] = useState(0);
      const increment = useCallback(() => {
        setValue(value + 1);
      }, [value]);

      // https://zh-hans.reactjs.org/docs/hooks-effect.html
      // https://preactjs.com/guide/v10/hooks/#useeffect
      const [time, setTime] = useState(Date.now());

      useEffect(() => {
        let timer = setInterval(() => {
          setTime(Date.now());
        }, 1000);

        return function cleanup() {
          clearInterval(timer);
        };
      }, []);

      return (
        <div>
          <h2>
            当前时间:<span>{new Date(time).toLocaleTimeString()}</span>
          </h2>
          当前计数: {value}
          <br />
          <button onClick={increment}>
            点这里增加计数，体验 React Hooks
          </button><br />
          调用 aardio 函数 external.func("Sciter") 的返回值： { external.func("Sciter") }
          <br /><br />
现在 Sciter JS 已经可以兼容 Preact �?br />
通过 Preact  Hooks 就可�?�?Sciter JS 里使�?React Hooks 写网页了�?br />
<br />
React hooks 简洁优�? 大幅降低了前端开发的门槛和学习成本�?br />
只要熟悉 useState, useEffect, useCallback, useContext 等几个非常简单的 Hooks 的用法，<br />
你就可以运用自如，强烈推荐大家学习和使用�?br /><br />
        </div>
      );
    }

    render(<Counter />, document.getElementById("preact"));
  </script>
<body >
    <div id="preact"></div>
</body>
</html>
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/reactor.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/reactor.md')

