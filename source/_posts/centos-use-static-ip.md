---
title: Centos 7 use static ip
date: 2020-02-28 11:43:51
tags: Linux,Centos
---

# Centos7 Use Static Ip

I use hyperv to create to new centos7 virtual machine, I want to use the old ip that I have.

* first to get the origin gateway,dns,netmask.

```
 #get gateway
 route -n | grep "^0.0.0.0" | tr -s " " | cut -f2 -d" "

 #get dns
 cat /etc/resolv.conf

 #get netmask

 ifconfig

```

* then change the config

```

sudo vi /etc/sysconfig/network-scripts/ifcfg-eth0

change BOOTPROTO and add

IPADDR=xxxx
GATEWAY=xxxx
DNS1=xxxx
DNS2=xxxx
NETMASK=xxxx

```
* restart the network, or you can just restart your virtual machine.

```
sudo systemctl restart network
```

