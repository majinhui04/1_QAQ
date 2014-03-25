QAQ.js
=====
1. **[对话框](#Dialog)**
2. **[进度提示框](#Loading)**
3. **[消息提示框](#Message)**
4. **[jQuery分页插件](#pagination)**


This is the link to the [Top] [top] Link.  
我在文章上部定义了:

[top]: #aa "Top of the post."
## 文件路径

    <link rel="stylesheet" type="text/css" href="http://assets.haoyuyuan.com/vendor/plugins/igrow/qaq/1.0.0/style.css">

    <script type="text/javascript" src="http://assets.haoyuyuan.com/vendor/plugins/igrow/qaq/1.0.0/qaq.js" ></script>

## 1 对话框<em id='Dialog'></em> 


### 调用


    var dialog = new QAQ.Dialog({
            title:'对话框'
        }
    });

    // 关闭
    dialog.close();

    //若模板中含有angularjs 使用 **QAQ.AADialog** 传入两个额外参数 $scope $compile
    var dialog = new QAQ.AADialog({
        compile:$compile
        scope:$scope
    });

### 参数说明

* `id` [可选] 指定dialog容器的id
* `cls` [可选] 指定dialog容器的css类
* `title` [可选] 指定dialog的标题
* `width` [可选] [默认值:420] 指定dialog的宽度
* `zIndex` [可选] [默认值:2014] 指定dialog的层级
* `modal` [可选] [默认值:true] 是否显示遮罩
* `drag` [可选] [默认值:false] 是否可拖拽dialog
* `winResize` [可选] [默认值:false] 浏览器缩放时 dialog是否重新定位
* `backdrop` [可选] [默认值:false] 点击dialog背景时 是否关闭dialog 默认不关闭
* `keyboard` [可选] [默认值:false]  按键盘escape时 是否关闭dialog 默认不关闭
* `success` [可选] 成功加载内容后的回调函数
* `content` [可选] html模板字符串 
* `contentUrl` [可选] 模板内容路径 推荐
* `contentSelector` [可选] 模板的选择器 `#xxx` or `.xxx`

**注:  `content`,`contentUrl`,`contentSelector` 三者选其一**


### 属性

* `$element` dialog容器dom

### 方法

* `close` dialog关闭

## 2 进度提示框
    QAQ.Loading.show('死命加载中...');
    QAQ.Loading.hide();

## 3 消息提示框
    QAQ.Message('5秒后自动消失...','info');// 1 success 2 error 3 info 4 warning

## 4 jQuery分页插件pagination

### 调用
    // entries 记录总数
    var entries = 20,
    $('.box').pagination(entries,{items_per_page：20});
    

### 参数说明

* `items_per_page` [可选] [默认值:10] 每页记录数目
* `num_display_entries` [可选] [默认值:10] 页码显示数
* `current_page` [可选] [默认值:0] 当前页码索引
* `num_edge_entries` [可选] [默认值:2] 边界页码显示数
* `link_to` [可选] [默认值:`javascript:;`] 页码链接
* `prev_text` [可选] [默认值:`上一页`] 上一页字符
* `next_text` [可选] [默认值:`下一页`] 下一页字符
* `ellipse_text` [可选] [默认值:`...`] 分页多于显示页码时 显示的字符
* `prev_show_always` [可选] [默认值:`true`] 是否显示上一页标签
* `next_show_always` [可选] [默认值:`true`] 是否显示下一页标签
* `callback` [可选] 点击页码后回调 `callback : function(page){// page为页码索引 }`
 


