# Mysql学习笔记
# 在cmd命令行中打开mysql 方法mysql -u root -p (有密码就在-p后面加上)
## 查询数据库
用cmd命令行打开数据库mysql -u root -p
show databases;(分号一定要加)
## 在数据库服务器中创建数据库
create database text；(text是数据库的名字)
create database xiaoxu charset utf8;---------- 创建一个名称为xiaoxu的数据库utf8可让数据显示中文
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
create table stu(num int primary auto_increment)
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
## mysql分组函数
group by(意思是代表在哪一个字段进行分组)
如果使用分组函数那么不在分组函数中的字段必须存在于group by
sum是求和 svg是求余 max最大值 min最小值
select sum(sal) total_sal ,deptno from emp group by deptno;
select svg(sal) total_sal ,deptno from emp group by deptno;
# mysql子查询
1子查询情况：将查询结果作为另一个查询的条件
等值比较 in
select ename,sal from emp where sal = (select max(sal) from emp);
2、查出平均工资最大的部门是哪个
组函数不能进行嵌套
我们的查询结果作为另一个查询的数据源 当成另一张表
当成表的过程中必须取别名
 select avg_sal,deptno from(select avg(sal) avg_sal,deptno from emp group by deptno) e where avg_sal =
    ->  (select min(avg_sal) from (select avg(sal) avg_sal,deptno from emp group by deptno) avg_table);
# mysql多表查询
查询员工姓名和员工所在部门的名称
select ename,dname from emp,dept where emp.deptno = dept.deptno;
select ename,dname from emp join dept on emp.deptno = dept.deptno;<!-- join替代逗号on替代where -->
## 表联合
左外联合 左边表中如果存在记录没有匹配到还想显示出来 关键之left
select m.ename,e.ename from emp m left join emp e on e.empno=m.mgr;
右外联合 右边表中如果存在记录没有匹配到还想显示出来 关键字right
select ename,dname from emp right join dept on emp.deptno=dept.deptno;
###3表联合实例
select ename,dname,grade from emp join dept join salgrade on emp.deptno=dept.deptno and emp.sal between
->  losal and hisal;






# mysql函数
## mysql常用函数
### 数学函数
pl() 返回pi的值（圆周率）
floor(x) 返回小于x的最大整数值，（去掉小数取整）
ceiling(x) 返回大于x的最小整数，（进一取整）
round(x,y) 返回参数x的四舍五入的有y位小数的值，（四舍五入）<!-- y里面写数字几就是小数点后几位 -->
truncate(x,y) 返回数字x截取为y位的小数结果 <!-- y里面写数字几就是截断小数点后的几位 -->
### 聚合函数 也称之为分组函数
<!-- 括号里的col是写字段的地方 -->
avg(col) 返回指定列的平均值
couint(col) 返回指定列中非null的值/行的个数（当函数参数为*星号时不会忽略）<!-- 会把你指定的列数值不为null的找出来，并且技数 -->
min(col) 返回指定列的最小值
max(col) 返回指定列的最大值
sum(col) 返回指定列的所有值的总和
### 字符串函数
length(查询字符串的长度)
<!-- 别名 可以给字段、表达式、函数加 -->
<!-- 别名 可以直接写 需要加引号的情况有（中文  有空格 有关键字） -->
concat(s1,s2.....sn) 将s1,s2....sn连接成字符串
<!-- select concat(ename,'的工资是',sal) '工资详细列表' from emp; -->
ltrim(str) 去掉字符串str开头的空格
rtrim(str) 去掉字符串str尾部的空格
trim(str) 去掉字符串首部和尾部的所有空格
substring(str,x,y) 截取字符串x开始y个、
<!-- select substring(ename,1,3) from emp -->
<!-- 原本是123456从1截取保留3位就变成了123 -->
### 日期函数
year(date) 返回日期date的年份
month(date) 返回日期date的月份(1-12)
day(date) 返回日期date的天数
hour(time) 返回time的小时值(0-23)
minute(time) 返回time的分钟值(0-59)
second(time) 返回time的秒值(0-59)
date(datetime) 返回datetime的日期值
time(datetime) 返回datetime的时间值





