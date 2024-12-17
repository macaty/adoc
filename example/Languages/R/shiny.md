[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: + R 璇█ 锛圫hiny锛? WebView2 鐣岄潰

```aardio aardio
//aardio 璋冪敤 R 璇█ - Web 浜や簰鐣岄潰
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio + R 璇█ 锛圫hiny锛? WebView2 鐣岄潰";right=759;bottom=469)
winform.add()
/*}}*/

import process.r;
import wsock.tcp.server;

//瀹夎 R 鍖咃紝濡傛灉宸插畨瑁呭拷鐣ヤ笉鎿嶄綔
process.r.require("shiny");

//R 浠ｇ爜
var rCode = `
library(shiny)
library(jsonlite)

ui <- fluidPage(
  titlePanel("JavaScript in Shiny"),
  sidebarLayout(
    sidebarPanel(
      sliderInput("numPoints",
                  "鐐圭殑鏁伴噺:",
                  min = 10,
                  max = 100,
                  value = 30),
      actionButton("genPlot", "鐢熸垚鍥捐〃")
    ),
    mainPanel(
      plotOutput("distPlot"),

      # 鍦℉TML椤甸潰涓彃鍏avaScript浠ｇ爜
      tags$script(HTML("

        Shiny.addCustomMessageHandler('sendJsonData',async function(data) {

            //璋冪敤 aardio 鍑芥暟
            var ret = await aardio.nativeMsgbox(data);

            window.myJsonData = data;  // 瀛樺偍鏁版嵁渚汮avaScript浣跨敤
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
    plot(data()$x, data()$y, main = "闅忔満鍒嗗竷鍥?)
  })

  observeEvent(input$genPlot, {
    jsonData <- toJSON(data(),dataframe="values")
    session$sendCustomMessage(type = 'sendJsonData', message = jsonData)
  })
}

# 鑾峰彇绌洪棽绔彛
args<-commandArgs(T)
port<-as.integer(args[1])

# 杩愯 Shiny 搴旂敤
shinyApp(ui = ui, server = server, options = list(port = port, host = '127.0.0.1'))
`; //鍙互娣诲姞涓嶅畾涓暟鐨勫惎鍔ㄥ弬鏁?
//鍚姩 R锛屽垎閰嶇┖闂茬鍙ｏ紙瀹夊叏銆佷笉浼氱浉浜掑啿绐侊級
var port = wsock.tcp.server.getFreePort('127.0.0.1');
var r = process.r.start(rCode,port);
//r.logResponse( );

import web.view;
var wb = web.view(winform);

//瀵煎嚭 aardio 鍑芥暟锛屽彲鍦ㄧ綉椤典笂璋冪敤浠ヤ笅鍑芥暟
wb.external = {
    nativeMsgbox = function(obj){
        winform.msgbox( obj )
    }
}

wb.go("http://127.0.0.1:"+port);

winform.show(3/*_SW_MAXIMIZE*/);
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/R/shiny.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/R/shiny.md')

