QAQ.js
=====

1. **[对话框](#Dialog)**
2. **[进度提示框](#Loading)**
3. **[消息提示框](#Message)**
4. **[jQuery分页插件](#pagination)**

## 1 对话框


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
* `buttons` [可选] 按钮 
    
        buttons:[{
            name:'确定',
            cls:'.btn-primary',//可选 自定义按钮css类 
            click:function(){
                var dialog = this;
                
                //do something
                dialog.close();
            }
        },{
            name:'取消',
            cls:'.btn-default',//可选 自定义按钮css类
            click:function(){
                var dialog = this;
                
                dialog.close();
            }
        }]
        // 默认提供了几种按钮样式
        btn-default 默认 
        btn-primary 主要 
        btn-success 成功
        btn-info 信息
        btn-warning 警告
        btn-danger 危险

**注:  `content`,`contentUrl`,`contentSelector` 三者选其一**


### 属性

* `$element` dialog容器dom

### 方法

* `close` dialog关闭

### 基于Dialog封装好的通用对话框

    1 警告框 alert
        QAQ.Dialog.alert('我警告你啊');
    2 确认框 confirm
        QAQ.Dialog.confirm('确认不要我了?',function(){
            // 点击确认回调    
            alert('你太狠心了')
        });
    3 消息提示 info
        QAQ.Dialog.info('我只是个消息','info'); // type:1 success 2 error 3 info 4 warning 默认info

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