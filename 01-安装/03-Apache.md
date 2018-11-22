# **安装最新版Apache**
**`Centos7 yum`源中没有最新的`Apache httpd server`, 现在的`yum`源最新的2.4.6,此版本有漏洞.
  `httpd 2.4.15`以上没有漏洞,下面的方法可以安装最新的`httpd`版本**
- 查看现在的Apache的版本
  ```
  yum info httpd
  ```
- 查看更改日志
  ```
  sudo yum install yum-changelog
  
  yum changelog httpd
  ```
- 设置`CodeIT repository仓库, CodeIT提供了最新的WEB服务器
  ```
  sudo yum install -y epel-release
  ```
- 启用CodeIT repository存储仓库
  ```
  cd /etc/yum.repos.d && wget https://repo.codeit.guru/codeit.el`rpm -q --qf "%{VERSION}" $(rpm -q --whatprovides redhat-release)`.repo
  ```
- 重新查看`yum`仓库里的`httpd`版本
  ```
  yum info httpd
  ```
- 安装`Apache httpd server`
  ```
  yum install httpd
  ```
- 启动/重启/停止`httpd`的指令
  ```
  systemctl start httpd
  systemctl restart httpd
  systemctl stop httpd
  ```
# **配置网站信息**
- 编辑`/etc/httpd/conf/httpd.conf`. 加入以下代码
  ```
  <VirtualHost *:80>
      DocumentRoot /var/www/html/wordpress      # 解析的代码位置
      ServerName www.aaa.com                    # 域名
      
  </VirtualHost>
  ```