QAQ
=====

#文件路径#
    <link rel="stylesheet" type="text/css" href="http://assets.haoyuyuan.com/vendor/plugins/igrow/sbdialog/style.css">

    <script src="http://assets.haoyuyuan.com/vendor/plugins/igrow/sbdialog/sb-dialog-1.0.0.js" type="text/javascript"></script>

#调用dialog#

    var dialog = new QAQ.Dialog({
        id          : '',//选填dialog的id
        cls         : '.x1 .x2',dialog的类
        backdrop    : false,//默认点击dialog背景时 不关闭dialog
        keyboard    : true,//默认 按键盘escape 关闭dialog
        title       : "对话框标题",
        close       : true,//暂时无用

        content     : '',//dialog的模板 3种模式  1. content:'<p>我是dialog的内容</p>' 2.contentUrl:'/views/dialog模板.html' 3.contentSelector:'#模板id'
        
        width       : 420,//选填
        zIndex      : 999,//暂时无用
        position    : 'center',//暂时无用
        modal       : true, //是否显示遮罩
        renderTo    : 'body',//暂时无用
        destroy     : true,//暂时无用
        header      : true,//暂时无用
        drag        : false,//是否可拖拽
        winResize   : false//浏览器缩放时是否重新定位
    });
    //关闭
    dialog.close();

#注:若模板中含有angularjs#

    需要传入两个额外参数 $scope $compile
    var dialog = new QAQ.AADialog({
        compile:$compile//必填
        scope:$scope//必填
    });

#通用dialog#

    QAQ.MMDialg.alert('警告框')
    QAQ.MMDialg.confirm('确认框',function(){//回调函数})
    QAQ.MMDialg.info('消息框','消息类型')  消息类型: 1 success 2 error 3 warning 4 message

#显示loading#
    QAQ.Loading.show('死命加载中...');
    QAQ.Loading.hide();
 
