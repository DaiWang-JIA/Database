#                                   Mysql数据库



# ==基础：==

# Mysql概述



## 数据库相关概念

![image-20250731170443410](Mysql数据库.assets/image-20250731170443410.png)

- 数据库：数据存储的仓库
- 数据库管理系统：操纵和管理数据库的大型软件
- SQL：操作关系型数据库的编程语言，是一套标准

![image-20250731181344221](Mysql数据库.assets/image-20250731181344221.png)



## 数据模型

- 关系型数据库（RDBMS）

![image-20250731181616170](Mysql数据库.assets/image-20250731181616170.png)

![image-20250731181754658](Mysql数据库.assets/image-20250731181754658.png)



# SQL

## 通用语法及分类

- SQL通用语法

![image-20250731182248985](Mysql数据库.assets/image-20250731182248985.png)



- SQL分类

![image-20250731182402388](Mysql数据库.assets/image-20250731182402388.png)



## DDL

### 数据库操作

![image-20250731182949961](Mysql数据库.assets/image-20250731182949961.png)



### 表操作

- 查询

![image-20250731184438283](Mysql数据库.assets/image-20250731184438283.png)



- 创建

![image-20250731184946613](Mysql数据库.assets/image-20250731184946613.png)

示例：

![image-20250731185126437](Mysql数据库.assets/image-20250731185126437.png)

```sql
mysql> create table tb_user(
    -> id int comment '编号',
    -> name varchar(50) comment '姓名',
    -> age int comment '年龄',
    -> gender varchar(1) comment '性别'
    -> ) comment '用户表' ;
```



- 数据类型及案例

![image-20250731190710687](Mysql数据库.assets/image-20250731190710687.png)

![image-20250731191441133](Mysql数据库.assets/image-20250731191441133.png)

![image-20250731192202273](Mysql数据库.assets/image-20250731192202273.png)



![image-20250731192304881](Mysql数据库.assets/image-20250731192304881.png)

![image-20250731192911772](Mysql数据库.assets/image-20250731192911772.png)



- 修改

1. 添加

![image-20250731193151433](Mysql数据库.assets/image-20250731193151433.png)

![image-20250731193248391](Mysql数据库.assets/image-20250731193248391.png)



2. 修改

![image-20250731193342491](Mysql数据库.assets/image-20250731193342491.png)

![image-20250731193512461](Mysql数据库.assets/image-20250731193512461.png)

![image-20250731193621435](Mysql数据库.assets/image-20250731193621435.png)



3. 删除

![image-20250731193716157](Mysql数据库.assets/image-20250731193716157.png)

![image-20250731193845104](Mysql数据库.assets/image-20250731193845104.png)



4. 修改表名

![image-20250731193813061](Mysql数据库.assets/image-20250731193813061.png)

![image-20250731193939322](Mysql数据库.assets/image-20250731193939322.png)





5. 删除表

![image-20250731194036148](Mysql数据库.assets/image-20250731194036148.png)

### DDL小结

![image-20250731194401700](Mysql数据库.assets/image-20250731194401700.png)





## DML

- 介绍

![image-20250801090250227](Mysql数据库.assets/image-20250801090250227.png)

### 添加数据

![image-20250801091139033](Mysql数据库.assets/image-20250801091139033.png)

```sql
insert into tb_user(id, name, age, gender) values (1,'itcast',10,'男');

select * from tb_user;

insert into tb_user values (2,'itcast2',20,'女');

insert into tb_user values (3,'itcast3',9,'男'),(4,'itcast4',6,'女');
```



### 更新和删除数据

- 更新

![image-20250801092921723](Mysql数据库.assets/image-20250801092921723.png)

```sql
update  tb_user set name='itheima' where id=1;

update tb_user set name='小昭',gender='女' where id=1;

update  tb_user set gender='女';
```



- 删除

![image-20250801093756137](Mysql数据库.assets/image-20250801093756137.png)

```sql
delete from tb_user where id=1;

delete from tb_user;
```



### 总结

![image-20250801094758174](Mysql数据库.assets/image-20250801094758174.png)



## DQL

- 介绍

![image-20250801095155898](Mysql数据库.assets/image-20250801095155898.png)



### 基础查询

- 语法

![image-20250801095323693](Mysql数据库.assets/image-20250801095323693.png)



- 基本查询

![image-20250801095545063](Mysql数据库.assets/image-20250801095545063.png)

```sql
create table emp(
    id int comment '编号',
    workno varchar(10) comment '工号',
    name varchar(10) comment  '姓名',
    gender char(1) comment  '性别',
    age tinyint comment '年龄',
    idcard char(18) comment '身份证号',
    workaddress varchar(50) comment '工作地址',
    entrydate date comment '入职时间'
) comment '员工表';

insert into emp(id, workno, name, gender, age, idcard, workaddress, entrydate)
values (1,'1','柳岩','女',20,'123456789789456123','北京','2000-01-01'),
       (2,'2','张无忌','男',21,'123456789789456523','上海','2000-02-01'),
       (3,'3','韦一笑','男',22,'123456789789756123','江苏','2000-03-01'),
       (4,'4','赵敏','女',23,'123456789789456126','成都','2000-04-01'),
       (5,'5','小昭','女',24,'123456789789456121','天津','2000-05-01'),
       (6,'6','张三丰','男',25,NULL,'广州','2000-06-01');

-- 查询指定字段 name,workno,age返回
select name,workno,age from emp;

-- 查询所有字段返回
select id, workno, name, gender, age, idcard, workaddress, entrydate from emp;

select * from emp;

-- 查询所有员工地址

select emp.workaddress as '工作地址' from emp ;

-- 查询员工的工作地址（不要重复）
select distinct  emp.workaddress '工作地址' from emp;

```



### 条件查询

- 语法

![image-20250801110001818](Mysql数据库.assets/image-20250801110001818.png)

```sql

-- 条件查询
-- 1.查询年龄=23的员工
select * from emp where age=23;

-- 2.查询年龄小于23的员工信息
select * from emp where age<23;

-- 3.查询年龄小于等于23的员工
select * from emp where age<=23;

-- 4.查询没有身份证号的成员信息
select * from emp where idcard is null;

-- 5.查询有身份证号的员工信息
select * from emp where idcard is not null;

-- 6.查询年龄不等于23的成员信息
select * from emp where age!=23;

-- 7.查询年龄在21到24之间的员工信息
select * from emp where 21<=age && age<=24;

-- 8.查询性别为女且年龄小于23的员工信息
select * from emp where gender='女' and age<23;

-- 9.查询年龄等于21，22，24的员工信息
select * from emp where  age=21 or age=22 or age=24;

-- 10.查询性别为2个字的员工
select * from emp where name like '__';

-- 11.查询身份证最后一位是X的员工信息
select * from emp where idcard like '%X';
```











# 函数





# 约束





# 多表查询





# 事务

