## mysql 5.7.2安装

### windows系统
mysql启动后自动停止....报abovting...的错误,可这么解决:ini文件添加行:shared-memory
1. 检查系统残留下的mysql服务,并将其删除掉
2. 切换到指定mysql安装目录的bin目录下
3. 安装Mysql服务: mysqld install
4. 不安全安装方式(空密码): mysqld --initialize-insecure.如果使用安全方式:mysqld --initialize,初始化的随机密码会记录在data/xx.err文件中.
    > 执行成功,生成data文件
5. 启动mysql服务.net start mysql.

6. 修改root密码.

>
    mysql -uroot

    update mysql.user set authentication_string=('root') where user='root';

    flush privileges;

    quit;

    注:5.7.2版本下的password 改成authentication_string

7. 设置远程访问权限:GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;

### init 文件模板
  >
    [mysql]
    # 设置mysql客户端默认字符集
    default-character-set=utf8
    [mysqld]
    #设置3306端口
    port = 3306
    # 设置mysql的安装目录
    basedir = E:\mysql-5.7.12-winx64
    # 设置mysql数据库的数据的存放目录
    datadir = E:\mysql-5.7.12-winx64\data
    # 允许最大连接数
    max_connections=1000
    # 服务端使用的字符集默认为8比特编码的latin1字符集
    character-set-server=utf8
    # 创建新表时将使用的默认存储引擎
    default-storage-engine=INNODB
    sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES

    #bind-address = 127.0.0.1

    skip-host-cache
    skip-name-resolve
    skip-ssl
    skip-grant-tables

### 通过data文件还原mysql数据库

  > 1. 停止mysql服务  net stop mysql
  > 2. 还原data/ibdata1文件
  > 3. 还原相关库文件
  > 4. 重启mysql服务  net start mysql
