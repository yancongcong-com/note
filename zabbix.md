# zabbix

#### server端

```
 rpm -Uvh https://repo.zabbix.com/zabbix/5.0/rhel/7/x86_64/zabbix-release-5.0-1.el7.noarch.rpm
```

```
yum -y install zabbix-server-mysql zabbix-agent zabbix-web-mysql zabbix-get
```

数据库

```
yum   -y install mariadb mariadb-server
```

```
# mysql -uroot -p
password
mysql> create database zabbix character set utf8 collate utf8_bin;
mysql> create user zabbix@localhost identified by 'password';
mysql> flush  privileges;
```

```
zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -uzabbix -p zabbix
```

配置zabbix

```
vim /etc/zabbix/zabbix_server.conf
DBHost-localhost
DBName=zabbix
DBUser=zabbix
DBPassword=password
```

启动

```
systemctl enable  zabbix-server
vim /etc/httpd/conf.d/zabbix.conf
systemctl  enable  httpd
```

