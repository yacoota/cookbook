#### 操作说明

##### window安装篇
+ 1、apache文件<br>
[下载](https://mirrors.tuna.tsinghua.edu.cn/apache//httpd/binaries/netware/httpd_2.4.10-netware-bin.zip)
+ 2、php文件<br>
[下载](https://windows.php.net/downloads/releases/php-7.4.5-Win32-vc15-x64.zip)

> 注意下载对应的版本

版本|说明|环境 
-|-|-
non-thread-safe|非线程安全|与IIS搭配环境
thread-safe|线程安全|与apache搭配的环境


+ 3、apache基础配置
```
命令：vi conf/httpd.conf
## 配置PHP解析 ##
PHPIniDir "D:/Program Files/Apache Software Foundation/php64"
LoadModule php7_module "D:/Program Files/Apache Software Foundation/php64/php7apache2_4.dll"
AddHandler application/x-httpd-php .php .html .htm
AddType application/x-httpd-php .php .html .htm

## 开启虚拟主机 ##
Include conf/extra/httpd-vhosts.conf

命令：vi conf/extra/httpd-vhosts.conf
<VirtualHost *:80>
    ServerAdmin gao_20022002@126.com
    DocumentRoot "T:/workapce/intellij/phpstorm"
    ServerName kaka.com
    ServerAlias www.kaka.com
    ErrorLog "logs/kaka_error.log"
    CustomLog "logs/kaka_access.log" common
    <Directory "T:/workapce/intellij/phpstorm">
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
+ 4、php基础配置
```
命令：cp php.ini-development php.ini
命令：vi php.ini

;开启sqllite
extension=pdo_sqlite
extension=sqlite3
;开启mysql;
extension=pdo_mysql
extension=mysql
extension=mysqli
;修改对应的服务参数
[MySQL]
[MySQLi]
```
+ 5、加入服务，测试运行
```
cd D:\Program Files\Apache Software Foundation\Apache64\bin
httpd -k install -n "Apache64"
net start Apache64
net stop Apache64
```