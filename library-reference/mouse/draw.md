[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# mouse.draw 库模块帮助文�?
## mouse.draw 成员列表

### mouse.draw.ellipse(x,y,a,b,precision)

x,y 中心所在的屏幕坐标(像素)

a,b 长轴和短轴的长度(像素)

precision 边缘精细�?
### mouse.draw.involute(fx,fy)

画渐开�?
fx,fy 宽高,参数可以忽略(默认为屏幕范�?

### mouse.draw.involute2(x,y,R,n)

画渐开�?

x,y 基圆圆心

R 基圆半径

n 渐开线周波数

### mouse.draw.line(x1,y1,x2,y2)

画直�?
x1,y1 起始坐标

x2,y2结束坐标

### mouse.draw.move

```aardio aardio
mouse.draw.move = function(x,y){

    mouse.move(x,y,true)
    sleep(10)

    return true;/*继续画线*/
}

```

### mouse.draw.poly(x,y,r,n)

x,y 中心所在的屏幕坐标(像素)

r 多边形外接圆半径(像素)

n 多边形的边数

### mouse.draw.rect(x1,y1,x2,y2)

画矩�?
x1,y1 起始坐标

x2,y2结束坐标

### mouse.draw.rectInvolute(step,n,x1,y1,x2,y2)

画方形仿渐开�?
step 步长

n 起始正方形边�?指定中间忽略不扫描的正方形边�?默认等于20)

x1,y1 扫描范围坐标,参数可省�?默认等于 1 X 1)

x2,y2 扫描范围坐标2,参数可省�?默认等于屏幕大小)

### mouse.draw.rectInvolute2(x,y,m,n=5,k=50)

x,y 坐标

m 扫描范围

n 扫描速度,可省�?默认等于5)

k 扫描密度,可省�?默认等于50)

### mouse.draw.sin(w,h)

画正弦曲�?
w,h �?�?可省�?默认取屏幕范�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/mouse/draw.md)

