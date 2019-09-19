1. 创建实例文件夹，赋予权限

2. 初始化实例
mysql_install_db --basedir=/usr --datadir=/home/multiMysql/datadir/3307 --user=mysql

3. 在/home/multiMysql下创建etc/xx.cnf，添加配置
[client]
port = 3307
socket = /home/multiMysql/socket/mysql3307.sock

[mysqld]
datadir=/home/multiMysql/datadir/3307
port = 3307
server_id =1
socket = /home/multiMysql/socket/mysql3307.sock


#bind-address = 127.0.0.1

sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
skip-host-cache
skip-name-resolve
skip-ssl
skip-grant-tables

4. 启动实例
/usr/bin/mysqld_safe --defaults-file=/home/multiMysql/etc/3307.cnf &

5. 登录mysql，安装mysql常规操作，设定密码，赋予远程访问
 mysql -u root -S /home/multiMysql/socket/mysql3307.sock

 修改用户密码
 UPDATE user SET password=password('root') WHERE user='root';  




## =========== 特别说明
在需要指定数据文件位置时如若指定后，服务启动失败，看如下：
1. 首先查看是否有权限

2. 怀疑selinux的问题,需要setenforce 0

3. 修改 /usr/lib/systemd/system/mariadb.service
  ProtectHome=false

4. 
