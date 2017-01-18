---
layout: post
title: Mariadb常用命令
category: 技术
tags: Mariadb
keywords: 
description: 
---

# Mariadb基础知识
## Mysql 的安装
```
$ sudo apt-get install mariadb-server mariadb-client
```

## Mysql 常用命令
### Mysql-server 的启动和关闭
```
$ mysqld &                    #mysql-server 启动
$ mysql -uroot -p shutdown    #mysql-server 关闭
```

### Mysql 更改密码
```
$ mysqladmin -uroot [-p] password "new_password"
```

### Mysql 备份
```
$ mysqldump -uroot -p database_name [table_name] > mysql.sql
```

### 登录
```
$ mysql -h 192.168.0.18 -uroot -p
$ mysql -uroot -D database_name -p < create_table.sql
```

### 对库的操作
```
show databases;                                       #显示所有库
use databases_name;                                   #使用库
create database database_name character set utf8;     #建库
drop database database_name;                          #删除库
```

### 对表的结构的操作
```
show tables;                                                                   #显示所有表
create table table_name(id int unsigned not null auto_increment primary key);  #建表
drop table table_name;                                                         #删除表
alter table table_name add cloumn data_type [after 插入位置];                   #插入列
alter table table_name change column new_clumn new_data_type;                  #更改列
alter table table_name drop column;                                            #删除列
alter table table_name rename new_table_name;                                  #重命名表名
desc table_name;                                                               #查看表的详细信息
```

### 对表的内容的操作
```
insert [into] table_name [(column)]values(value);
select column_name from table_name where condition;
update table_name set column_name=value where condition;
delete from table_name where condition;
```

## 常见问题
查找某列是不是NULL，要使用 is NULL, is NOT NULL

### 将mysql的编码格式设置为utf8
1. 将/etc/mysql/my.cnf里[mysqld]组名的末尾添加： `character-set-server=utf8`
2. service mysql restart
3. mysql -uroot -p
4. SHOW VARIABLES LIKE 'char%'

## 参考资源
1. http://www.w3school.com.cn/sql/index.asp
2. http://www.yiibai.com/mysql/mysql_quick_start.html
