# 1.下载mysql

https://downloads.mysql.com/archives/community/

# 2.解压

C:\Program Files\mysql-5.7.21-winx64
![image](https://github.com/roototo/roototo.github.io/assets/173517135/d24e7e04-297b-4416-916c-3f885ed9aa6a)

# 3.配置环境变量
![image-20220418203442769](https://github.com/roototo/roototo.github.io/assets/173517135/679b58cb-8113-402f-862e-d895a23e7fac)

# 4.安装mysql

## 4.1配置初始化my.ini文件

放到C:\Program Files\mysql-5.7.21-winx64文件夹下

> [mysqld]
> port=3306
> basedir=C:\Program Files\mysql-5.7.21-winx64\
> datadir=C:\Program Files\mysql-5.7.21-winx64\data
> max_connections=200
> max_connect_errors=10
> character-set-server=utf8
> external-locking = FALSE
> default-storage-engine=INNODB 
> default_authentication_plugin=mysql_native_password
> [mysqld_safe]
> log-error=C:\Program Files\mysql-5.7.21-winx64\
> mysql_oldboy.errpid-file=C:\Program Files\mysql-5.7.21-winx64\mysqld.pid
> sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
> [mysql]
> default-character-set=utf8

## 4.2初始化文件夹

```mysql
mysqld --initialize --console
```

※执行完毕后会生成初始化密码（不含首位空格），在没有更新密码前，需要记住此密码。

同时，在根目录下后生成数据存放目录data文件夹。
![image-20220418204002286](https://github.com/roototo/roototo.github.io/assets/173517135/f46edd17-4adf-403b-86aa-19c07f863623)

如果忘记密码，删除data目录，重新运行初始化命令初始化数据库即可。

## 4.3安装目录

用管理员打开cmd，在bin目录下执行安装服务命令

mysqld --install [服务名]

不写服务名默认为mysql。安装完毕后，在windows服务中可以看到mysql服务。
![image-20220418204259057](https://github.com/roototo/roototo.github.io/assets/173517135/f2a05898-c168-41d6-b423-19c4cfc191bc)


## 4.4更改密码

启动mysql服务

```mysql
net start mysql
```

进入数据库

```mysql
mysql -u root -p
```

修改密码

```mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码'
```

# 5.其他sql命令

连接mysql服务

```mysql
mysql -u root -p
```

CREATE DATABASE 数据库名;

1. 显示当前数据库服务器中的数据库列表
  
  SHOW DATABASES;
  
2. 建立数据库
  
  CREATE DATABASE 库名;
  
  CREATE TABLE 表名 (字段名 VARCHAR(20), 字段名 CHAR(1));
  
3. 使用数据库
  
  USE 库名;
  
4. 删除数据库
  
  DROP DATABASE 库名;
  
5. 删除数据表
  
  DROP TABLE 表名;
  
6. 将表中记录清空
  
  DELETE FROM 表名;
  
7. 往表中插入记录
  
  INSERT INTO 表名 VALUES ("hyq","M");
  
8. 更新表中数据
  
  UPDATE 表名 SET 字段名1='a',字段名2='b' WHERE 字段名3='c';
  
9. 用文本方式将数据装入数据表中
  
  LOAD DATA LOCAL INFILE "D:/mysql.txt" INTO TABLE 表名;
  
10. 导入.sql文件命令
  
  SOURCE d:/mysql.sql;
  
11. 命令行修改root密码
  
  UPDATE mysql.user SET password=PASSWORD('新密码') WHERE User='root';
  
  FLUSH PRIVILEGES;
  
12. 导出数据库
  
  mysqldump -u 用户名 -p 数据库名 > 导出的文件名
  
13. 导出一个表
  
  mysqldump -u 用户名 -p 数据库名 表名> 导出的文件名
  
14. 导出一个数据库结构
  
  mysqldump -u user_name -p -d --add-drop-table database_name > outfile_name.sql
  
15. 带语言参数导出
  

​ mysqldump -uroot -p --default-character-set=latin1 --set-charset=gbk --skip-opt database_name > outfile_name.sql

MySQL 是一个功能强大的关系型数据库管理系统，支持大量的命令和语句来管理数据库和执行操作。以下是一些常用的 MySQL 命令：

1. 连接和退出：
  
  - 连接到 MySQL 服务器：`mysql -u username -p`
  - 退出 MySQL 连接：`quit` 或 `\q`
2. 数据库操作：
  
  - 创建数据库：`CREATE DATABASE database_name;`
  - 删除数据库：`DROP DATABASE database_name;`
  - 使用数据库：`USE database_name;`
  - 显示数据库列表：`SHOW DATABASES;`
3. 表操作：
  
  - 创建表：`CREATE TABLE table_name (column1 datatype, column2 datatype, ...);`
  - 删除表：`DROP TABLE table_name;`
  - 显示表列表：`SHOW TABLES;`
  - 显示表结构：`DESCRIBE table_name;` 或 `SHOW COLUMNS FROM table_name;`
4. 数据操作：
  
  - 插入数据：`INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);`
  - 查询数据：`SELECT column1, column2, ... FROM table_name WHERE condition;`
  - 更新数据：`UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;`
  - 删除数据：`DELETE FROM table_name WHERE condition;`
5. 用户管理：
  
  - 创建用户：`CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';`
  - 授予权限：`GRANT privileges ON database_name.table_name TO 'username'@'localhost';`
  - 修改密码：`ALTER USER 'username'@'localhost' IDENTIFIED BY 'new_password';`
  - 删除用户：`DROP USER 'username'@'localhost';`