[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: + R 语言 （Shiny�? WebView2 界面

```aardio aardio
//aardio 调用 R 语言 - Web 交互界面
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio + R 语言 （Shiny�? WebView2 界面";right=759;bottom=469)
winform.add()
/*}}*/

import process.r;
import wsock.tcp.server;

//安装 R 包，如果已安装忽略不操作
process.r.require("shiny");

//R 代码
var rCode = `
library(shiny)
library(jsonlite)

ui <- fluidPage(
  titlePanel("JavaScript in Shiny"),
  sidebarLayout(
    sidebarPanel(
      sliderInput("numPoints",
                  "点的数量:",
                  min = 10,
                  max = 100,
                  value = 30),
      actionButton("genPlot", "生成图表")
    ),
    mainPanel(
      plotOutput("distPlot"),

      # 在HTML页面中插入JavaScript代码
      tags$script(HTML("

        Shiny.addCustomMessageHandler('sendJsonData',async function(data) {

            //调用 aardio 函数
            var ret = await aardio.nativeMsgbox(data);

            window.myJsonData = data;  // 存储数据供JavaScript使用
        });

        $(document).on('shiny:inputchanged', function(event) {
          if (event.name === 'genPlot' && event.value > 0) {
            //Shiny.onInputChange('jsData', JSON.stringify(window.myJsonData));
          }
        });
      "))
    )
  )
)

server <- function(input, output, session) {
  data <- reactive({
    data.frame(x = rnorm(input$numPoints), y = rnorm(input$numPoints))
  })

  output$distPlot <- renderPlot({
    req(input$genPlot > 0)
    plot(data()$x, data()$y, main = "随机分布�?)
  })

  observeEvent(input$genPlot, {
    jsonData <- toJSON(data(),dataframe="values")
    session$sendCustomMessage(type = 'sendJsonData', message = jsonData)
  })
}

# 获取空闲端口
args<-commandArgs(T)
port<-as.integer(args[1])

# 运行 Shiny 应用
shinyApp(ui = ui, server = server, options = list(port = port, host = '127.0.0.1'))
`; //可以添加不定个数的启动参�?
//启动 R，分配空闲端口（安全、不会相互冲突）
var port = wsock.tcp.server.getFreePort('127.0.0.1');
var r = process.r.start(rCode,port);
//r.logResponse( );

import web.view;
var wb = web.view(winform);

//导出 aardio 函数，可在网页上调用以下函数
wb.external = {
    nativeMsgbox = function(obj){
        winform.msgbox( obj )
    }
}

wb.go("http://127.0.0.1:"+port);

winform.show(3/*_SW_MAXIMIZE*/);
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/R/shiny.md)

