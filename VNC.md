# VNC

服务端

```Centos
cat /etc/system-release
yum group list
yum -y group install gnome-desktop
reboot
```

VNC  server

```
yum list |grep vnc

yum -y install tigervnc-server

rpm  -qi  tigervnc-server

rpm  -qc tigervnc-server
```



vncserver --help

vncserver

 vncserver -list

ps aux |grep vnc

ss -anpt |grep vnc

防火墙

```
firewall-cmd --add-service=vnc-server --permanent
firewall-cmd  --reload
```

客户端

Realvnc  viewer