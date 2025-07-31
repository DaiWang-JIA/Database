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



# 函数





# 约束





# 多表查询





# 事务

