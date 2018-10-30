# googleFeedback
![](https://user-gold-cdn.xitu.io/2018/5/22/16386e2e8dca1808?w=419&h=259&f=gif&s=1950244)
![](https://user-gold-cdn.xitu.io/2018/5/17/1636cec56d528280?w=255&h=420&f=gif&s=1070950)

### DOCUMENT
#### 1.Install
```
<body>
    <div id="feedback"></div>
    <button id="btn"></button>
<body>
<script src="react-googlefeedback/dist/googlefeedback.js"></script>
<script>
    new Feedback({
        container: document.getElementById('feedback'),
        trigger: document.getElementById('btn'),
        theme: '#3986FF',
        proxy: 'http://127.0.0.1:5000',
        title: "Send feedback",
        placeholder: "Describe your issue or share your ideas",
        requiredTip: "A description is required",
        editTip: "Click to highlight or hide info",
        loadingTip: "Screenshot loading...",
        checkboxLabel: "Include screenshot",
        cancelLabel: "CANCEL",
        confirmLabel: "SEND",
        hightlightTip: 'Hightlight issues',
        hideTip: 'Hide sensitive info',
        editDoneLabel: 'DONE',
        license: `Go to the
                <a href="" >Legal Help page </a>
                to request content changes for legal reasons. Some
                <a href="">account and system information </a>
                may be sent to Google. We will use the information you give us to help address technical                  issues and to improve our services, subject to our
                <a href=""> Privacy Policy</a>and<a href="">Terms of Service</a>.`,
        send: function (data) {
            console.log(data)
        }
    });
</script>
```
### 3.Documentation
| name | description | dataType | isRequired |
|-|-|-|-|
|container|component container element|element|✓|
|trigger|the element used to trigger the opening of the component|element|✓|
|theme|set component theme color|string|✗ default: #3986FF|
|license|license|html string|✗ the default value is Google’s Privacy Policy|
|proxy|proxy address, this value can be set if cross-domain resources exist in the page|string|✗ default: ''|
|title|dialog headline text|string|✗|
|placeholder|text input prompt|string|✗|
|requiredTip|text required prompt|string|✗|
|editTip|prompt to edit text|string|✗|
|loadingTip|loading image tips|string|✗|
|checkboxLabel|check box label|string|✗|
|cancelLabel|cancel button label|string|✗|
|confirmLabel|confirm button text|string|✗|
|hightlightTip|Highlight button text tip|string|✗|
|hideTip|Hide button text tip|string|✗|
|editDoneLabel|Edit confirmation button text|string|✗|
|send|send button handler function, will return the collected data|function|✓|

### 4.Cross domain agent
Need to start a service for proxy.
first install [html2canvas-proxy](https://www.npmjs.com/package/html2canvas-proxy)
```
npm install html2canvas-proxy --save
```
Use proxy in Nodejs
```
var proxy = require('html2canvas-proxy');
var express = require('express');
var app = express();
app.use('/', proxy());
```

### 使用文档
在页面中引入js文件使用：
```
<body>
    <div id="feedback"></div>
    <button id="btn"></button>
<body>
<script src="react-googlefeedback/dist/googlefeedback.js"></script>
<script>
    new Feedback({
        container: document.getElementById('feedback'),
        trigger: document.getElementById('btn'),
        theme: '#3986FF',
        proxy: 'http://127.0.0.1:5000',
        title: '发送反馈',
        placeholder: '请说明您的问题或分享您的想法',
        requiredTip: '必须添加说明',
        editTip: '点击编辑高亮或隐藏信息',
        loadingTip: '正在加载屏幕截图...',
        checkboxLabel: '包含截图',
        cancelLabel: '取消',
        confirmLabel: '发送',
        hightlightTip: '突显问题',
        hideTip: '隐藏敏感信息',
        editDoneLabel: '完成',
        license: `如出于法律原因需要请求更改内容，请前往
                <a href="" >法律帮助</a>
                页面。系统可能已将部分
                <a href="">帐号和系统信息</a>
                发送给Google。我们将根据自己的
                <a href="">隐私权政策</a>和<a href="">服务条款</a>
                使用您提供的信息帮助解决技术问题和改进我们的服务。`,
        send: function (data) {
            console.log(data)
        }
    });
</script>
```
### 3.参数说明
| 参数 | 功能 | 类型 | 是否必填 |
|-|-|-|-|
|container|组件容器元素|element|✓|
|trigger|用于触发组件打开的元素|element|✓|
|theme|设置组件主题颜色|string|✗ 默认值 #3986FF|
|license|协议内容|html字符串|✗ 默认值为谷歌的隐私条款协议|
|proxy|代理地址，如果页面中存在跨域资源可以设置这个值|string|✗ 默认空值|
|title|弹出标题文字|string|✗|
|placeholder|文字输入提示|string|✗|
|requiredTip|文字必填提示|string|✗|
|editTip|提示编辑文子|string|✗|
|loadingTip|加载图片提示|string|✗|
|checkboxLabel|勾选框文字|string|✗|
|cancelLabel|取消按钮文字|string|✗|
|confirmLabel|确认按钮文字|string|✗|
|hightlightTip|高亮按钮文字提示|string|✗|
|hideTip|隐藏按钮文字提示|string|✗|
|editDoneLabel|编辑确认按钮文字|string|✗|
|send|发送按钮处理函数，会传回收集的数据|function|✓|
### 4.跨域代理
需要启动一个服务用于代理。
首先安装[html2canvas-proxy](https://www.npmjs.com/package/html2canvas-proxy)
```
npm install html2canvas-proxy --save
```
在node中使用代理
```
var proxy = require('html2canvas-proxy');
var express = require('express');
var app = express();
app.use('/', proxy());
```

