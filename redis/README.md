# ThinkPHP

## 开启debug模式
config.php -> `app_debug => true`


## PHP 自动导入类的插件
PHP Companion
1. 安装
2. 配置快捷键(首选项 -> 快捷键设置)
```
[
  { "keys": ["f10"], "command": "expand_fqcn" },
  { "keys": ["shift+f6"], "command": "expand_fqcn", "args": {"leading_separator": true} },
  { "keys": ["f9"], "command": "find_use" },
  { "keys": ["f4"], "command": "import_namespace" },
  { "keys": ["f3"], "command": "implement" },
  { "keys": ["shift+f12"], "command": "goto_definition_scope" },
  { "keys": ["f7"], "command": "insert_php_constructor_property" }
]
```

##  `Permission denied` 对不起 没有权限

## 格式化插件
HTML/css/js prettify. 安装过程中需要制定 nodejs 命令的路径.

## 伪静态
```
http://192.168.209.128/redis/code/TP/public/index.php/user.html
```

## 关于省略 index.php 的配置
1. 修改apache配置文件(httpd.conf). 将该行配置打开
```
LoadModule rewrite_module modules/mod_rewrite.so
```

2. 修改网站根目录下的配置
```
AllowOverride All
```

3. 重启
```
/usr/local/apache2/bin/apachectl restart
```

## 服务器创建虚拟主机
1. 修改 httpd.conf, 将虚拟主机的子配置文件打开
2. 配置子配置文件
```
<VirtualHost *:80>
    DocumentRoot "/usr/local/apache2/htdocs/redis/code/TP/public"
    ServerName www.lamp207.net
    ErrorLog "logs/dummy-host2.example.com-error_log"
    CustomLog "logs/dummy-host2.example.com-access_log" common
    <Directory "/usr/local/apache2/htdocs/redis/code/TP/public">  
          Options Indexes MultiViews  
          AllowOverride All  
          Order allow,deny  
          Allow from all  
          DirectoryIndex index.php 
    </Directory>
</VirtualHost>
```
3. 重启apache
4. 修改 hosts 文件, 域名解析.
```
127.0.0.1   www.lamp207.net
19.20.90.80  www.baidu.com
```

## sublime 快速打开文件的快捷键
```
ctrl + p
```
