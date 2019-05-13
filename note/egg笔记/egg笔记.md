###
# 3秒跳转网页
<meta http-equiv="refresh" content="5;URL=/landing">
###点击子元素删除他的父级
$("#d1").click(function(){
    $(this).parent().hide();
});
###用jQuery实现点击div变蓝效果
<script src="../public/js/jquery1.js"></script>
        <script>
    $('.one').click(function(){
        $('.one').css({"background-color":"#0090ff"})
        $('.two').css({"background-color":"#e0e4e7"})
        $('.three').css({"background-color":"#e0e4e7"})
        $('.four').css({"background-color":"#e0e4e7"})
    })

### 安装模板依赖

npm install --save egg-view-nunjucks

### 配置插件

修改文件config/plugin.js

``` js
module.exports = {
  // had enabled by egg
  // static: {
  //   enable: true,
  // }
  nunjucks: {
    enable: true,
    package: 'egg-view-nunjucks',
  }
};
```

修改文件config/config.default.js

``` js
//添加下面的选项
config.view = {
defaultViewEngine: 'nunjucks'
}

