###Mysql学习笔记
#查询数据库服务器？
show databases;(分号一定要加)
#在数据库服务器中创建数据库
create database text；(text是数据库的名字)
 #创建一个数据库
create database 数据库名 [其他选项];
例如我们需要创建一个名为 samp_db 的数据库, 在命令行下执行以下命令:
create database samp_db character set gbk;
#删除数据库
drop database (database后面加数据库的名称)
#选择要操作的数据库
use sys(use后面跟数据库名字)
#退出服务器
exit;
create table 表名(字段名称 字段类型,字段名称 字段类型......);
下面是一个有着,学号，性名，性别，年纪，年龄，入学日期的表
create table student(
    -> num int(6),
    -> name varchar(10),
    -> sex varchar(2),
    -> age int,
    -> schooldate date);
#查看当前数据库中有那些表
 show tables;
#创建一个数据表
 #查看表中的数据
 select * from student;(student是名字什么都行)
 #如何查看一个表的结构
 desc 表名;
 #删除数据表
 drop table 表名;
#对表的结构进行增、删、改、查的操作
增加字段:
alter table 表名 add 字段名 字段类型
alter table book add count int;
修改字段:
alter table 表明名 modify 字段名称 字符类型
alter table book modifu price int;
删除字段:
alter table 表名 drop 字段名 
alter table book drop count;
#向表中插入数据
insert into 表名(想插入的字段名称,...) values(想插入的字段的值)





 


