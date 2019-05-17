# Mysql学习笔记
## 查询数据库
show databases;(分号一定要加)
## 在数据库服务器中创建数据库
create database text；(text是数据库的名字)
## 删除数据库
drop database (database后面加数据库的名称)
## 选择要操作的数据库
use sys(use后面跟数据库名字)
## 退出服务器
exit;
## 创建一个数据表
create table 表名(字段名称 字段类型,字段名称 字段类型......);
下面是一个有着,学号，性名，性别，年纪，年龄，入学日期的表
create table student(
    -> num int(6),
    -> name varchar(10),
    -> sex varchar(2),
    -> age int,
    -> schooldate date);
## 查看当前数据库中有那些表
 show tables;
 ## 查看表中的数据
 select * from student;(student是名字什么都行)
 ## 查看一个表的结构
 desc 表名;
 ## 删除数据表
 drop table 表名;
## 对表的结构进行增、删、改、查的操作
增加字段:
alter table 表名 add 字段名 字段类型
alter table book add count int;
修改字段:
alter table 表明名 modify 字段名称 字符类型
alter table book modifu price int;
删除字段:
alter table 表名 drop 字段名 
alter table book drop count;
## 向表中插入数据
insert into 表名(想插入的字段名称,...) values(想插入的字段的值)
insert into 表明 values(表中所有字段的值)
## 删除sql语句格式
### 清空表
delete from 表名;
### 删除指定的某一行
delete from 表名 where 条件表达式;
## 修改表中记录
update 表明 set 字段名=新的字段值,.... where 条件表达式
# mysql约定（不允许去做某些事情）
## 唯一约束
unique(写在你要加的字段里面)
create table stu(num int unique);
null 任何一个null都不等于另一个null
## 非空约束
not null
同一个字段可以加上多个约束不需要用逗号隔开
非空约束和唯一约束的一个组合我们称为组件约束
## 主键约束
非空约束和唯一约束的一个组合我们称之为主键约束
prmary key
## mysql的自动增长策略
auto_increment
create table stu(num int primary kauto_increment)
## 外键约束
foreign key（外键约束关键字
下面为外键约束实际操作
 create table stu(num int primary key auto_increment , name varchar(11), clazznum int,foreign key(clazznum) references clazz(num) );
在msqyl中外键必须得是另一张表的主键

# mysql查询
select * from 表名 查询出该表名下的所有数据
## 了解查询语句的格式
select {字段1,字段2,字段n} from 表名当我们需要将表中所有字段数据都查出来时
只需要要把字段替换成*即可
select 表达式 {算数表达式（加、减、乘、除）} from 表名
在字段前面加distinct可以实现去重效果
## 条件查询
### where条件表达式
select * from 表名 where 条件表达式；
select * from emp where deptno = 20;
分别有 等值比较 大于 小于 大于等于 小于等于 不等于 （不等于的符号是<>)
比较时字符串类型的数据必须要加引号
### 多个条件查询
and 并且
or 或者
关键字in代表这个取值中只要有一个匹配就是符合条件
关键值实际操作
select * from emp where sal = 800  or sal=1600 or sal=950;
select * from emp where sal in(800,1600,950);
not in 不在这个范围之间的
select * from emp where sal not in(800,1600,950);
between and 相当于大于等于和小于等于
select * from emp where sal >= 1600 and sal<= 3000;
select * from emp where sal between 1600 and 3000;
空永远不等于空
null和null做等值判断时结果永远是假
判断一个字段的数值是否为null需要用到关键字is
如果想判断不等于null需要用到is not
## mysql函数
### mysql常用函数
数学函数


 


