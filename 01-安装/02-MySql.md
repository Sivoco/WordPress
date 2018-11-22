# **安装mysql**
- 下载`repository`仓库
  ```
  yum install http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
  ```
- 检查下载的`repository`仓库, 查看mysql prm包是否存在, 命令和返回结果如下:
  ```
  [root@VM_230_32_centos ~]# sudo yum repolist enabled | grep "mysql.*-community.*"
  Repository epel is listed more than once in the configuration
  mysql-connectors-community/x86_64 MySQL Connectors Community                  42
  mysql-tools-community/x86_64      MySQL Tools Community                       53
  mysql56-community/x86_64          MySQL 5.6 Community Server                 361
  ```
- 使用`yum`命令安装`mysql`数据库
  ```
  yum install mysql-community-server
  ```
- 输出结果示例:
  ```
  .......
  Replaced:
    mariadb-libs.x86_64 1:5.5.52-1.el7                                                                                                                                                                                           
  Complete!
  [root@VM_230_32_centos ~]#
  ```
- 启动/重启/停止`mysql`数据服务器
  ```
  //centos 7系统命令
  systemctl start mysqld
  systemctl restart mysqld
  systemctl stop mysqld
  
  //centos 6系统命令
  service mysqld start
  service mysqld restart
  service mysqld stop
  ```
- 修改MySql数据库的密码
  ```
  mysql -uroot -p
  //密码确认之后, 重新设置MySql密码
  mysql> set password for root@localhost = password('123456');  # 123456位要替换的密码
  ```
  
# **创建数据库**
- 登入MySQL
  ```
  mysql -u root -p
  //输入自己的登入密码
  ```
- 新建数据库
  ```
  create database xxxxx;   # xxxxx为数据库名称, 注意指令后面的分号
  ```
- 查看数据库
  ```
  show databases;
  ```
- 删除数据库
  ```
  drop database xxxxx;     # xxxxx为数据库名称, 注意指令后面的分号
  ```
# **其他**
- 退出指令
  ```
  exit;
  ```
