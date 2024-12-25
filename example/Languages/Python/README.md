[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 错误调试/提问必读

```aardio aardio
//错误调试/提问必读

/*
Python 常见问题解答、提问前必读
https://api.aardio.com/cdn/python/faq/
*/

import console.int;
import py3;

/*
一般执�?Python 代码出错会报错，直接显示错误信息�?但有些地方是返回 null （因为可能需要用这些函数 null 值做检测而不是报错）�?*/
py3.import("不存在的模块");//例如这个函数出错就返�?nul

//可以�?py3.lasterr() 查看错误信息
console.log(py3.lasterr());

//打开控制台查�?Python 输出的错误信�?console.open();

// Python �?sys.excepthook 自定义异常处理，类似 aardio �?global.onError
py3.exec(`
import sys
import traceback

def handle_exception(exc_type, exc_value, exc_traceback):
    if issubclass(exc_type, KeyboardInterrupt):
        sys.__excepthook__(exc_type, exc_value, exc_traceback)
        return
    print("Uncaught exception", exc_type, exc_value)
    traceback.print_exception(exc_type, exc_value, exc_traceback)

sys.excepthook = handle_exception

# 这将触发未捕获的异常
x = 1 / 0
`)
console.more(1)

// Python �?try 捕获错误，用 traceback 打印错误堆栈�?aardio 代码有个类似�?debug 库）
py3.exec(`
import traceback

try:
    # 可能会引发异常的代码
    x = 1 / 0
except Exception as e:
    print(f"An error occurred: {e}")
    traceback.print_exc()
`)
console.more(1)

//或者用 logging 模块
py3.exec(`
import logging
import traceback

logging.basicConfig(level=logging.ERROR)

try:
    # 可能会引发异常的代码
    x = 1 / 0
except Exception as e:
    logging.error("An error occurred", exc_info=True)
`)
console.more(1)

/*
或者用 contextmanager 模块�?with 语句封装 try ... except ... finall （与 aardio 里的 with 完全不是一回事�?�?contextmanager 用于配合 with 语句管理上下文�?*/
py3.exec(`
from contextlib import contextmanager
import traceback

@contextmanager
def handling_exceptions():
    try:
        yield
    except Exception as e:
        print(f"An error occurred: {e}")
        traceback.print_exc()

with handling_exceptions():
    # 可能会引发异常的代码
    x = 1 / 0
`)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/README.md)

