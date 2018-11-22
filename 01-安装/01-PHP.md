# **安装PHP**
- **使用`yum`源在`CentOS 7`中安装`PHP 5.6`**
- 安装`epel`和下载`repository`仓库
  ```
  # yum install epel-release
  
  # rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
  ```
- 使用`yum list`命令查看可安装的包, 此命令只起到查看作用, 可以不运行.
  ```
  # yum list --enablerepo=remi --enablerepo=remi-php56 | grep php
  ```
- 使用`yum`源安装配置`PHP 5.6`环境
  ```
  # yum install --enablerepo=remi --enablerepo=remi-php56 php php-gd php-opcache php-devel php-mbstring php-fpm php-mcrypt php-mysqlnd php-phpunit-PHPUnit php-pecl-xdebug php-pecl-xhprof
  ```
- 使用`PHP`命令查看安装的`PHP`版本信息
  ```
  [root@VM_219_180_centos ~]# php -v
  PHP 5.6.32 (cli) (built: Oct 25 2017 06:49:52) 
  Copyright (c) 1997-2016 The PHP Group
  Zend Engine v2.6.0, Copyright (c) 1998-2016 Zend Technologies
      with Zend OPcache v7.0.6-dev, Copyright (c) 1999-2016, by Zend Technologies
      with Xdebug v2.5.5, Copyright (c) 2002-2017, by Derick Rethans
  ```