# **WordPress**
## **安装WordPress**
- 下载`WordPress`
  ```
  wget https://cn.wordpress.org/wordpress-4.9.4-zh_CN.tar.gz      # WordPress的下载地址可以去中文官网寻找
  ```
- 解压`WordPress`
  ```
  tar -xzf wordpress-4.9.4-zh_CN.tar.gz -C /var/www/html
  ```
- 初始设置`WordPress`
  - 在浏览器输入`http;//ip/wordpress`或`http://localhost/wordpress`访问,自动开始安装`WordPress`
  - 中文版`WordPress`点击`现在安装`进入下一步
  - 输入数据库信息
    - 数据库名称
    - 数据库用户名
    - 数据库密码
    - 数据库`Host`
    - 标签
- 在`/var/www/html/wordpress`目录下创建一个`wp-config.php`文件,将页面中高亮的部分复制入内并保存, 点击`现在安装`
- 设置网站和用户信息
  - 网站名称
  - 后台用户名
  - 后台密码
  - 联系邮箱
  - 是否允许搜索引擎搜索到
- 设置FTP
  - 添加下列内容到`/var/www/html/wordpress/wp-config.php`
    ```
    define("FS_METHOD","direct");
    define("FS_CHMOD_DIR", 0777);
    define("FS_CHMOD_FILE", 0777);
    ```
  - 给`wordpress`添加权限
    ```
    chmod -R 777 wordpress
    ```