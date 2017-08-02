# SquidConf
The configuration of Squid


去除代理登陆密码：
删除或者#注释
auth_param basic program /usr/lib64/squid/ncsa_auth /etc/squid/passwd
auth_param basic children 5
auth_param basic realm Welcome to pac.itzmx.com proxy web server
acl squid_user proxy_auth REQUIRED
http_access allow squid_user

然后把
http_access deny all
修改成http_access allow all

然后重启squid即可
service squid restart

如果修改密码请vi编辑/etc/squid/passwd文件，htpasswd加密方式为crypt
