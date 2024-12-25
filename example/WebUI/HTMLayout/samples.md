[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.layout(HTMLayout) 界面范例浏览�?
```aardio aardio
//界面预览
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="web.layout(HTMLayout) 界面范例浏览�?;right=856;bottom=542;)
winform.add(
tab={cls="tab";left=236;top=9;right=843;bottom=530;db=1;dl=1;dr=1;dt=1;edge=1;z=2};
treeview={cls="treeview";left=23;top=10;right=231;bottom=527;asel=false;bgcolor=15793151;db=1;dl=1;dt=1;edge=1;hscroll=1;infoTip=1;vscroll=1;z=1}
)
/*}}*/

import fsys;
import zlib.unzip;
import inet.downBox;
if( !..io.exist("/html_samples" ) ){
    if( ..win.msgboxTest(  "HTMLayout范例尚未安装,您需要下载安装HTMLayout范例�?","aardio") ){

        var downBox = inet.downBox(winform,"aardio- 下载HTMLayout范例",true)
        if( not downBox.download(
            "http://download.aardio.com/v10.files/demo/htmlayout_samples.zip"
            ,"/htmlayout_samples.zip"
            ,null,null,"")
        ) {
            return;
        }

        try{
            import console;
            zlib.unzip.extract( "/htmlayout_samples.zip","/",
                function(fileName,extractPath,fileInfo,size,unitSize,unitName){
                    console.log("正在解压�?,extractPath)
                    return true;
                }
            )
            io.close()
        }
        catch(e){
            fsys.delete( "/html_samples" )
        }

        if( !..io.exist("/html_samples" ) ){
            winform.msgboxErr("下载HTMLayout范例失败","aardio")
        }
        fsys.attrib("/html_samples",/*移除*/,0x2/*_FILE_ATTRIBUTE_HIDDEN*/)
    }
}

import fsys.codepage;
var frmPreview = winform.tab.add( text="效果预览"; bottom=140;right=325 )
var frmSourceCode = winform.tab.add( text="编辑源码";right=599;bottom=390 )
frmSourceCode.add(
btnHelp={ dr=1;bottom=385;text="HTMLayout中文教程";left=20;top=353;z=3;db=1;right=159;cls="button" };
btnExplore={ disabled=1;dr=1;bottom=385;text="浏览 ...";left=200;top=353;z=5;db=1;right=314;cls="button" };
richedit={ dr=1;dl=1;bottom=346;vscroll=1;right=591;left=7;dt=1;top=6;multiline=1;z=1;db=1;hscroll=1;edge=1;cls="richedit" };
btnCreateProject={ dr=1;disabled=1;bottom=385;right=473;left=319;top=353;z=2;db=1;text="另存�?HTMLayout工程";cls="button" };
btnSave={ dr=1;disabled=1;bottom=385;text="保存更改";left=481;top=353;z=4;db=1;right=587;cls="button" }
)
frmSourceCode.btnCreateProject.oncommand = function(id,event){
     createDemoProject();
}
frmSourceCode.btnHelp.oncommand = function(id,event){
    import process;;
    process.openUrl("http://bbs.aardio.com/forum.php?mod=forumdisplay&fid=128&filter=typeid&typeid=132")
}
frmSourceCode.richedit.modifyEvent(,0x1/*_ENM_CHANGE*/);
frmSourceCode.richedit.oncommand = function(id,event){
    if( event == 0x300/*_EN_CHANGE*/ ){
        frmSourceCode.btnSave.disabled = false
    }
}
frmSourceCode.btnSave.oncommand = function(id,event){
    ..fsys.codepage.save(getCurrentHtmlFileUrl(), frmSourceCode.richedit.text,"UTF-8");
    loadHtmlFile();
}
frmSourceCode.btnExplore.oncommand = function(id,event){
    exploreFile();
}

import web.layout;
import web.layout.behavior.tabs;
import web.layout.behavior.shellIcon;
import web.layout.behavior.lightBoxDialog;
import web.layout.behavior.collapsibleByIcon;
import web.layout.behavior.grid;
import web.layout.behavior.sortableGrid;
import web.layout.behavior.scroller;
import web.layout.behavior.dropdown;
import web.layout.behavior.popup;
import web.layout.behavior.expandableList;
import web.layout.behavior.collapsibleList;
import web.layout.behavior.sizer;
import web.layout.behavior.gripper;
import web.layout.behavior.splitter;

var wbLayout = web.layout(frmPreview);
/*
import web.layout.debug; //导入该库以显示HTMLayout错误
wbLayout.attachEventHandler( web.layout.debug ); //为CSSS!添加全局函数 debug;
*/

getCurrentHtmlFileUrl = function(){
    if(!winform.treeview.lastClickItem)
        return;

    var path = winform.treeview.getItemText(winform.treeview.lastClickItem )
    if( #path ){
        if( string.find(path,":") ){
            //中文标题,使用子节点获取真实目�?            var hitem = winform.treeview.getChildItem(winform.treeview.lastClickItem)
            path = winform.treeview.getItemText( hitem );
            path = fsys.getParentDir(path)
            frmSourceCode.btnCreateProject.disabled = true;
            return io.joinpath("/html_samples",path)
        }

        frmSourceCode.btnCreateProject.disabled = false;
        return io.joinpath("/html_samples",path)
    }
}

import fsys.dlg;
var templateLayout = /********************
import win.ui;
/*DSG{{*/
var winform = win.form( bottom=399;text="aardio form";right=599 )
/*}}*/

import web.layout;
import web.layout.behavior.tabs;

var wbLayout = web.layout(winform);
wbLayout.go("${URL}")

wbLayout.onButtonClick = function (ltTarget,ltOwner,reason,behaviorParams) {

}

winform.show()
win.loopMessage();

            ********************/

var templateLayoutHtml = /********************
import win.ui;
/*DSG{{*/
var winform = win.form( bottom=399;text="aardio form";right=599 )
/*}}*/

import web.layout;
import web.layout.behavior.tabs;
var wbLayout = web.layout(winform);

import web.layout.debug; //导入该库以显示HTMLayout错误
wbLayout.attachEventHandler( web.layout.debug ); //为CSSS!添加全局函数 debug;

wbLayout.html = /*********
${HTML}
*********/

wbLayout.onButtonClick = function (ltTarget,ltOwner,reason,behaviorParams) {

}

winform.show()
win.loopMessage();

            ********************/

import ide;
import fsys.dlg.dir;
createDemoProject = function(){
    var targetDir = fsys.dlg.dir(,,"请选择工程保存目录");
    if(!targetDir)return;
    targetDir = io.joinpath(targetDir,"/HTMLayout范例工程/")
    fsys.createDir(targetDir);
    fsys.copy( "~\extensions\wizard\project\win",targetDir)
    targetDir = io.joinpath(targetDir,"win")
    var samplesPath = getCurrentHtmlFileUrl();

    if( wbLayout.loadFileCount > 1 ){
        var samplesDir = fsys.getParentDir(samplesPath);
        fsys.copy( samplesDir,io.joinpath(targetDir,"\res") );

        var url = fsys.path.relative( samplesPath ,fsys.getParentDir(samplesDir),true)
        string.save(io.joinpath(targetDir,"default.main.aardio"),( string.replace(templateLayout,"@${URL}",io.joinpath("\res",url) ) ) )
    }
    else {
            string.save(io.joinpath(targetDir,"default.main.aardio"),( string.replace(templateLayoutHtml,"@${HTML}",fsys.codepage.load(samplesPath) ) ) )
    }

    ide.openDocument(io.joinpath(targetDir,"default.aproj"))
}

frmSourceCode.richedit.wndproc = function(hwnd,message,wParam,lParam){
    if( message == 0x204/*_WM_RBUTTONDOWN*/  ){
       owner.popMenu( {
        { "在IDE中创建HTMLayout工程"; createDemoProject }
       } );
    }
}

wbLayout.onDataLoaded = function(lParam) {
    var dataLoaded = raw.convert(lParam,{
        struct hdr = ::NMHDR();
        ustring  uri;
        ptr data;
        INT dataSize;
        INT dataType;
        INT status;
    });
    if( ! string.startWith(dataLoaded.uri,"data:",true) ){
        wbLayout.loadFileCount = wbLayout.loadFileCount + 1;
    };
    frmSourceCode.btnCreateProject.disabled = false;
}

import inet.http;
var http = inet.http();
import fsys.codepage;
loadHtmlFile = function(){
    var path = getCurrentHtmlFileUrl()
    if(!#path)return;
    winform.text = "web.layout(HTMLayout) 界面范例浏览�?" + path;

    win.ui.waitCursor(true)
    frmSourceCode.richedit.text = "正在加载......"
    wbLayout.write( "<body>正在加载.......</body>" )
    winform.setTimeout(
        function(){
            wbLayout.loadFileCount = 0;
            wbLayout.go(path,,true);
            frmSourceCode.btnExplore.disabled = false;
            frmSourceCode.richedit.text = fsys.codepage.load(path,"UTF-8");
            frmSourceCode.btnSave.disabled = true;
             win.ui.waitCursor(false)
        }
    )
}

import process;
exploreFile = function(){
    var path = getCurrentHtmlFileUrl()
    if(!#path)return;
    if( fsys.isDir(path) )
        process.explore(path)
    else {
        process.explore_select(path)
    }
}

winform.treeview.onnotify = function(id,code,ptr){

    if( code == 0xFFFFFFFE/*_NM_CLICK*/ ){
        var hItem = winform.treeview.hitTest()
        if( hItem ){
             winform.treeview.lastClickItem = hItem
             var path = winform.treeview.getItemText(hItem);
             if( (#path) ? string.endWith(path,".htm",true) ){
                loadHtmlFile()
             }
        }
    }
    elseif(code = 0xFFFFFFFB/*_NM_RCLICK*/){
        var hItem,tvht = winform.treeview.hitTest();
        winform.treeview.setSelected(hItem)
        var menu = win.ui.popmenu(winform)
        menu.add("预览效果",loadHtmlFile )
        menu.add("使用资源管理器浏�?..",exploreFile )
        menu.add("在IDE中创建HTMLayout工程",createDemoProject )
        menu.popup(x,y,true);
    }
}

var tab = {
{ text="cssmap.htm" };
{ text="index.htm" };
{ text="CSS扩展";{
        { text="css-plus\aspect-ratio.htm" };
        { text="css-plus\back-fore.htm" };
        { text="css-plus\big-scrollbar-styling.htm" };
        { text="css-plus\color-transform-gamma.htm" };
        { text="css-plus\color-transform.htm" };
        { text="css-plus\constants.htm" };
        { text="css-plus\content-transform.htm" };
        { text="css-plus\hsl-colors.htm" };
        { text="css-plus\opacity.htm" };
        { text="css-plus\outline-glow-on-black.htm" };
        { text="css-plus\outline-glow.htm" };
        { text="css-plus\outline-styles.htm" };
        { text="css-plus\scroll-manner-styling-flow-grid.htm" };
        { text="css-plus\scroll-manner-styling-table.htm" };
        { text="css-plus\scroll-manner-styling.htm" };
        { text="css-plus\scrollbar-styling.htm" };
        { text="css-plus\small-scrollbar-styling.htm" };
        { text="css-plus\table-of-content.htm" };
        { text="css-plus\theme-images.htm" };
        { text="css-plus\tree-view-lines.htm" }
   }
};
{ text="csss!脚本";{
        { text="csss!\1.htm" };
        { text="csss!\animate-bounce.htm" };
        { text="csss!\animate-cubic.htm" };
        { text="csss!\animate-ease-list.htm" };
        { text="csss!\animation-expand-horz.htm" };
        { text="csss!\animation-expand.htm" };
        { text="csss!\animation-fade.htm" };
        { text="csss!\animation-simple.htm" };
        { text="csss!\animation-slide.htm" };
        { text="csss!\autofocus.htm" };
        { text="csss!\behavior-method-calls.htm" };
        { text="csss!\bound-slider.htm" };
        { text="csss!\calc-basic.htm" };
        { text="csss!\calc-dom.htm" };
        { text="csss!\calc-ext.htm" };
        { text="csss!\chart-custom-methods.htm" };
        { text="csss!\collapsible-by-checkbox.htm" };
        { text="csss!\collapsible-by-icon.htm" };
        { text="csss!\collapsible-when-action.htm" };
        { text="csss!\collapsible-with-behavior.htm" };
        { text="csss!\custom-tooltip-positioning.htm" };
        { text="csss!\dip-units.htm" };
        { text="csss!\dropdown-list.htm" };
        { text="csss!\frame-loading.htm" };
        { text="csss!\grid-sortable.htm" };
        { text="csss!\grid-with-collapsibles.htm" };
        { text="csss!\highlight-links.htm" };
        { text="csss!\keyboard-handling.htm" };
        { text="csss!\label-for-activation.htm" };
        { text="csss!\localization.htm" };
        { text="csss!\loops.htm" };
        { text="csss!\progress.htm" };
        { text="csss!\pure-css-tabs-states.htm" };
        { text="csss!\pure-css-tabs.htm" };
        { text="csss!\scroll-to-view.htm" };
        { text="csss!\show-popup.htm" };
        { text="csss!\size-changed.htm" };
        { text="csss!\slider-and-better-buddy.htm" };
        { text="csss!\styles-link-activation.htm" };
        { text="csss!\table-checkboxes.htm" };
        { text="csss!\text-width.htm" };
        { text="csss!\textarea-method-calls.htm" };
        { text="csss!\total.htm" };
        { text="csss!\use-of-consts.htm" };
        { text="csss!\use-of-other-dom-elements.htm" };
    };
};
{ text="入门";{
        { text="generic\backgrounds.htm" };
        { text="generic\custom-control-border.htm" };
        { text="generic\hidden.htm" };
        { text="generic\iframe.htm" };
        { text="generic\overflows.htm" };
        { text="generic\selectors.htm" };
        { text="generic\sidebars.htm" };
        { text="generic\tabindex_navigation.htm" };
        { text="generic\backgrounds" };
        { text="generic\sidebars" }
    };
};
{ text="推荐";{
        { text="goodies\animated-cursor.htm" };
        { text="goodies\animatedgifs.htm" };
        { text="goodies\cursor.htm" };
        { text="goodies\custom-tags.htm" };
        { text="goodies\data-url.htm" };
        { text="goodies\file-icon.htm" };
        { text="goodies\gifs.htm" };
        { text="goodies\icon.htm" };
        { text="goodies\picture.htm" };
        { text="goodies\pictures" };
        { text="goodies\smiley" };
    }
};
{ text="特效";{
        { text="effects\marquee.htm" };
        { text="effects\reflection.htm" }
    }
};
{ text="鱼眼特效";{
        { text="fisheye\magnifier-4.htm" };
        { text="fisheye\magnifier-left-bottom.htm" };
        { text="fisheye\magnifier.htm" };
        { text="fisheye\magnifieranza.htm" }
    }
};
{ text="绝对定位";{
        { text="abs\abs.htm" };
        { text="abs\abspos.htm" };
        { text="abs\abs_fix.htm" };
        { text="abs\fix_center.htm" };
        { text="abs\menus.htm" };
        { text="abs\rel_abs.htm" }
    }
};
{ text="背景";{
        { text="back\alpha-back.htm" };
        { text="back\backdemo.htm" };
        { text="back\keep-ratio.htm" }
    };
};
{ text="圆角边框";{
        { text="border-radius\border-radius.htm" };
        { text="border-radius\rounded-tabs-at-bottom.htm" };
        { text="border-radius\rounded-tabs.htm" }
    }
};
{ text="字体";{
        { text="@font-face\test.htm" }
    };
};
{ text="svg绘图";{
        { text="svg\gradient-svg.htm" };
        { text="svg\cowboy-svg.htm" };
    }
};
{ text="PNG动画";{
        { text="animated-png\apng.htm" };
        { text="animated-png\disposal.htm" };
        { text="animated-png\loading.htm" }
    }
};
{ text="动画";{
        { text="animations\blend.htm" };
        { text="animations\h-sliding-bar-csss!.htm" };
        { text="animations\h-sliding-bar.htm" };
        { text="animations\popup-animations.htm" };
        { text="animations\sliding-bar-csss!.htm" };
        { text="animations\sliding-bar.htm" };
        { text="animations\sliding-list.htm" }
    }
};
{ text="渐变效果(transition)";{
        { text="transitions\!transition-doc.htm" };
        { text="transitions\accordion.htm" };
        { text="transitions\border-animation.htm" };
        { text="transitions\easing-functions.htm" };
        { text="transitions\flex-units-transition.htm" };
        { text="transitions\folding.htm" };
        { text="transitions\margin-animation.htm" };
        { text="transitions\opacity.htm" };
        { text="transitions\reverse-modes.htm" };
        { text="transitions\to-intrinsic-height.htm" }
    }
};
{ text="交互扩展(behaviors)"; {
        { text="behaviors\accesskeys.htm" };
        { text="behaviors\actions.htm" };
        { text="behaviors\chart.htm" };
        { text="behaviors\colorpopup.htm" };
        { text="behaviors\commands.htm" };
        { text="behaviors\dropdown-with-select.htm" };
        { text="behaviors\dropdown.htm" };
        { text="behaviors\editable-select.htm" };
        { text="behaviors\form-test.htm" };
        { text="behaviors\graphin-live-clock.htm" };
        { text="behaviors\htmlarea.htm" };
        { text="behaviors\hyperlinks.htm" };
        { text="behaviors\light-box-dialog.htm" };
        { text="behaviors\live-clock.htm" };
        { text="behaviors\more_tabs.htm" };
        { text="behaviors\path-behavior.htm" };
        { text="behaviors\scroller.htm" };
        { text="behaviors\select-buddy.htm" };
        { text="behaviors\shell-icon.htm" };
        { text="behaviors\sizer-popup.htm" };
        { text="behaviors\treeview.htm" };
        { text="behaviors\splitters.htm" };
        { text="behaviors\colorpopup" };
        { text="behaviors\more_tabs" }
    }
};
{ text="提交表单"; {
        { text="communication\file-upload.htm" };
        { text="communication\form-submission.htm" }
    }
};

{ text="拖放"; {
        { text="drag-n-drop\drop-target-types.htm" };
        { text="drag-n-drop\gripper.htm" };
        { text="drag-n-drop\menu-dd.htm" };
        { text="drag-n-drop\shopping-cart.htm" };
        { text="drag-n-drop\tabs-reordering.htm" };
        { text="drag-n-drop\tree-view-context.htm" };
        { text="drag-n-drop\tree-view-rtl.htm" };
        { text="drag-n-drop\tree-view.htm" }
    }
};
{ text="窗口控件"; {
    { text="forms\basiccontrols.htm" };
    { text="forms\buttons.htm" };
    { text="forms\custom-ctl-styles.htm" };
    { text="forms\custom-dropdown-selects.htm" };
    { text="forms\datetime.htm" };
    { text="forms\dropdown-select-tree.htm" };
    { text="forms\dropdown-selects.htm" };
    { text="forms\editable-dropdown-selects.htm" };
    { text="forms\edits.htm" };
    { text="forms\form.htm" };
    { text="forms\input-text-and-button.htm" };
    { text="forms\listview.htm" };
    { text="forms\multiselect.htm" };
    { text="forms\path-select.htm" };
    { text="forms\plaintext.htm" };
    { text="forms\popup-selector.htm" };
    { text="forms\progress.htm" };
    { text="forms\scrollbars.htm" };
    { text="forms\selects.htm" };
    { text="forms\slider.htm" };
    { text="forms\table-select.htm" };
    { text="forms\tabs-in-tabs.htm" };
    { text="forms\tabs.htm" };
    { text="forms\textarea.htm" };
    { text="forms\tree-view.htm" };
    { text="forms\tristate-checkbox.htm" }
    };
};
{ text="菜单"; {
        { text="menu\c-menu.htm" };
        { text="menu\context-menu.htm" };
        { text="menu\for-track-popup-test.htm" };
        { text="menu\menu-bar.htm" };
        { text="menu\non-rectangular-menu.htm" };
        { text="menu\popup-menu.htm" }
    }
};
{ text="tooltip提示"; {
        { text="tooltips\month.htm" };
        { text="tooltips\titles.htm" }
    }
};
{ text="编辑�?;{
        { text="editor\index.htm" }
    }
};
{ text="richtext控件"; {
        { text="richtext\help-shortcuts.htm" };
        { text="richtext\plaintext-modes.htm" };
        { text="richtext\plaintext.htm" };
        { text="richtext\richtext-list.htm" };
        { text="richtext\richtext.htm" }
    };
};
{ text="fieldset标签"; {
        { text="fieldset\layout.htm" }
    }
};

{ text="table表格"; {
    { text="fixed-table\collapsible-sections-classic.htm" };
    { text="fixed-table\collapsible-sections.htm" };
    { text="fixed-table\simple-sections.htm" };
    { text="fixed-table\simple.htm" };
    { text="fixed-table\table-fixed-10000-rows-sections.htm" };
    { text="fixed-table\table-fixed-10000-rows.htm" }
    }
};
{ text="布局模式"; {
        { text="flows\columns.htm" };
        { text="flows\demo-at-w3c.htm" };
        { text="flows\dynamic-flow-tmpl.htm" };
        { text="flows\grid-layout-2.htm" };
        { text="flows\grid-layout-3.htm" };
        { text="flows\grid-layout-4.htm" };
        { text="flows\grid.htm" };
        { text="flows\h-flow.htm" };
        { text="flows\template-layout-using-indexes.htm" };
        { text="flows\template-layout.htm" };
        { text="flows\text-fragment.htm" };
        { text="flows\v-flow.htm" };
        { text="flows\content";  {
                    { text="flows\content\flow-and-floats.htm" };
                    { text="flows\content\flow-horizontal-flow.htm" };
                    { text="flows\content\flow-horizontal.htm" };
                    { text="flows\content\flow-template.htm" };
                    { text="flows\content\flow-vertical-flow.htm" };
                    { text="flows\content\flow-vertical.htm" };
                    { text="flows\content\lorem-ipsum.htm" }
            };
        }
    };
};
{ text="for-at"; {
        { text="for-at\buttons.htm" };
        { text="for-at\ext-scrollbars.htm" }
    }
};

{ text="框架应用"; {
        { text="frames\behaviors.htm" };
        { text="frames\border-spacing.htm" };
        { text="frames\frame-splitter-styling.htm" };
        { text="frames\frame1.htm" };
        { text="frames\frame2.htm" };
        { text="frames\frame3.htm" };
        { text="frames\frame4.htm" };
        { text="frames\frames-rtl.htm" };
        { text="frames\frames.htm" };
        { text="frames\frameset-splitter.htm" };
        { text="frames\large-content-in-frames.htm" };
        { text="frames\standalone-frame.htm" };
        { text="sort-of-frames\help.htm" }
    }
};
{  text="网格(grid)"; {
        { text="grid\scrollable-table.htm" };
        { text="grid\sortable-grid.htm" };
        { text="grid\table-tbody-thead.htm" };
        { text="grid\virtual-table.htm" }
    }
};
{ text="水平/垂直对齐"; {
        { text="horizontal-vertical-align\horizontal-align-flow.htm" };
        { text="horizontal-vertical-align\horizontal-align.htm" };
        { text="horizontal-vertical-align\vertical-align.htm" }
    }
};
{ text="include语法"; {
        { text="includes\root.htm" }
        { text="includes\chunk1.htm" };
        { text="includes\chunk2.htm" };
    }
};
{ text="优化"; {
        { text="optimizations\dyn-updates.htm" }
    }
};
{ text="打印"; {
        { text="printing\!readme!.htm" };
        { text="printing\page-break-after.htm" };
        { text="printing\page-break-before.htm" };
        { text="printing\page-break-inside.htm" }
    }
};
{ text="MSVS 起始页效�?; {
        { text="MSVS-start-page\start-page.htm" };
        { text="MSVS-start-page\content\getting-started.htm" };
        { text="MSVS-start-page\content\headlines.htm" };
        { text="MSVS-start-page\content\list-of-projects.htm" };
        { text="MSVS-start-page\content\msdn-recent-news.htm" }
    }
};
{ text="压力测试"; {
        { text="stress\animation.htm" };
        { text="stress\complex_tables.htm" };
        { text="stress\grid-1000-outline-glow.htm" };
        { text="stress\grid-1000-rounded-corners.htm" };
        { text="stress\grid-1000.htm" };
        { text="stress\grid-fixed-1000.htm" };
        { text="stress\grid-fixed-10000.htm" };
        { text="stress\select-10000.htm" };
        { text="stress\table-10000.htm" };
        { text="stress\table-fixed-10000.htm" };
        { text="stress\tabs" ;
            children={
                { text="stress\tabs\form.htm" };
                { text="stress\tabs\grid-1000.htm" };
                { text="stress\tabs\tabs.htm" };
                { text="stress\tabs\tree-view.htm" };
            }
        }
    };
};
{ text="HTML32.htm" };
}

hitem = winform.treeview.insertItem( tab )

winform.show(0x3/*_SW_MAXIMIZE*/)
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/samples.md)

