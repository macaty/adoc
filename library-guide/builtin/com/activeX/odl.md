[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# ODL 语法指南

> �?aardio 中一般不需要改�?\*.odl 类型库声明文件�?保持默认就可以，所有接口函数可�?com.activeX 自动导出�?>
> 如果要自定义类型库，建议继承 aardio.idl 提供�?IDispeatchExecutable 接口�?所�?DISPID 不应大于 10000 （aardio 自动生成 DISPID �?10000 为起始值递增）�?>
> 所�?aardio 表对象、函数对象都实现�?IDispatch 接口�?表对象可�?DISPID\_NEWENUM 调用时返�?IEnumVARIANT 枚举接口�?
## 一、定义类型库（library�?
### 1.1 语法

```odl odl
[attributes]
library 类型库名 {
    importlib("库名");
    [attributes]
    interface/interface_name : IDispatch {
        函数定义;
    };
};

```

### 1.2 语法元素说明

- `attributes`: 可以包括 `helpstring`, `helpcontext`, `lcid`, `restricted`, `hidden`, `control`, `uuid`, `version` 属性，其中 `uuid` 是必须的�?- `library`: 类型库的名字�?- `importlib`: 引入标准库�?- `interface`: 接口定义�?
### 1.3 备注

- `library` 表达式必须出现在任何类型定义之前�?
### 1.4 示例

```odl odl
import "aardio.idl";

[
uuid(27A24EA2-F236-4FE4-A918-44AAB7A8DC5C),
version(1.0)
]
library aardioTestControl {

    importlib("stdole32.tlb");

    [ uuid(EC32DF0E-0947-4DF1-827D-7073D376995D),control ]
    coclass Sample {

        //默认接口
        [default] dispinterface IDispatchExecutable;

        //默认事件源接�?        [default,source] dispinterface IDispatchExecutableEvent;
    };
};

```

## 二、定义自动化接口（dispinterface�?
### 2.1 语法

```odl odl
[attributes]
dispinterface 接口�?{
    函数列表
};

```

### 2.2 语法元素说明

- `attributes`: 一般只要指�?`uuid` 就可以了�?- `functionlist`: 接口中每个函数的原型列表�?
### 2.3 函数定义

```odl odl
[attributes] returntype [calling convention] funcname(params);

```

- `attributes`: 可包�?`helpstring`, `helpcontext`, `string`, `propget`, `propput`, `propputref`, `bindable`, `defaultbind`, `displaybind`, `vararg` 等�?- `params`: 参数列表，可以包�?`in`, `out`, `optional`, `string` 属性�?
### 2.4 备注

- aardio 里最常用的是 dispinterface 接口，否则必须是继承�?IDispatch 的自动化接口�?- dispinterface 接口不能继承自其他接口（因为必须继承自IDispatch）�?- dispinterface 不需要在最后一个参数指定返回值，并且也不需要返�?`HRESULT` 值，而是直接指定实际需要的返回值就可以了�?- 添加 \[out\] 标记参数能声明输出参数，实际�?COM 接口很少用这种输出参数，直接使用返回值更简单�?- 所�?DISPID 的值必须小�?10000 并大于等�?0 ，大�?10000 �?DISPID �?aardio 自动分配�?
### 2.5 示例

```odl odl
    [ uuid(1C8736BC-8C0C-4DB6-9FAD-1C6A0CDF1FA2) ]
    dispinterface  IDispatchSample{
        properties:
        methods:
            [ id(10) ]
            void Test( [in] BSTR str,[in,out] VARIANT *out1,[in,out] VARIANT *out2);
    }

```

## 三、定义接口（interface�?
### 2.1 语法

```odl odl
[attributes]
interface 接口�?[: 父接口名] {
    函数列表
};

```

### 2.2 语法元素说明

- `attributes`: 可以包括 `dual`, `helpstring`, `helpcontext`, `hidden`, `odl`, `oleautomation`, `uuid`, `version` 属性，其中 `odl` �?`uuid` 是必须的�?- `functionlist`: 接口中每个函数的原型列表�?
### 2.3 函数定义

```odl odl
[attributes] returntype [calling convention] funcname(params);

```

- `attributes`: 可包�?`helpstring`, `helpcontext`, `string`, `propget`, `propput`, `propputref`, `bindable`, `defaultbind`, `displaybind`, `vararg` 等�?- `params`: 参数列表，可以包�?`in`, `out`, `optional`, `string` 属性�?
### 2.4 备注

- 接口里的函数返回 `HRESULT` 值，真实返回值指定为返回参数，始终是最后一个参数�?- 双重接口必须�?`IDispatch` 继承�?
### 2.5 示例

```odl odl
[uuid(BFB73347-822A-1068-8849-00DD011087E8), version(1.0)]
interface Hello : IUnknown {
    void HelloProc([in, string] unsigned char* pszString);
    void Shutdown(void);
};

[dual]
interface IMyInt : IDispatch {
    [propget] HRESULT MyMessage([in, lcid] LCID lcid, [out, retval] BSTR* pbstrRetVal);
    [propput] HRESULT MyMessage([in] BSTR rhs, [in, lcid] DWORD lcid);
    HRESULT SayMessage([in] long NumTimes, [in, lcid] DWORD lcid, [out, retval] BSTR* pbstrRetVal);
}

```

## 四、定义组件类（coclass�?
### 3.1 语法

```odl odl
[attributes]
coclass 类名 {
    [attributes2] [interface | dispinterface] 接口�?
};

```

### 3.2 语法元素说明

- `attributes`: `uuid` 属性是必须的，其它属性包�?`helpstring`, `helpcontext`, `version`, `licensed`, `control`, `hidden`, `appobject` 等�?- `attributes2`: `interface` �?`dispinterface` 的可选属性，包括 `source`, `default`, `restricted` 等�?- `interfacename`: �?`interface` �?`dispinterface` 声明的接口名�?
### 3.3 备注

- `coclass` 定义一个类作为一个实现，允许 `QueryInterface` 在接口集之间查询�?
### 3.4 示例

```odl odl
[uuid(BFB73347-822A-1068-8849-00DD011087E8), version(1.0), helpstring("A class"), helpcontext(2481), appobject]
coclass myapp {
    [source] interface IMydocfuncs;
    dispinterface DMydocfuncs;
};

[uuid(00000000-0000-0000-0000-123456789019)]
coclass foo {
    [restricted] interface bar;
    interface bar;
}

```

此文档精简�?ODL 语法的关键要素，便于快速入门和掌握基本写法�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/activeX/odl.md)

