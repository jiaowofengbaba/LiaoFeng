## 解决数据库插入不了中文
create database eggtest charset utf8;
utf8可让数据显示中文
## 链接数据库
mysql -u root -p
# 下载依赖，安装egg-sequelize和mysql2
npm install --save egg-sequelize mysql2
### 在egg项目中配置egg-sequelize

``` js
// config/plugin.js
exports.sequelize = {
    enable: true,
    package: 'egg-sequelize'
}
```

``` js
// config/config.default.js
  config.sequelize = {
    dialect: 'mysql', 
    database: 'army',  //数据库名
    host: 'localhost',
    port: '3306',
    username: 'root',  //用户名
    password: '',      //密码
    operatorsAliases: false,
  }