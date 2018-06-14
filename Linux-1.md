### Linux 入门教程（一）

#### 虚拟机
什么是虚拟机？

虚拟机（Virtual Machine）指通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。

以 virtualbox 为例


##### 虚拟机四种网络模式

	- Network Address Translation (NAT)
	- Bridged networking
	- Internal networking
	- Host-only networking

https://www.virtualbox.org/manual/ch06.html

练习：使用 virtualbox 安装 centos，并成功配置网络， 可以正常访问网络（尝试使用 NAT 或 桥接模式）


#### 配置 Linux 网络

两套命令集 net-tools 和 iproute2， 问题这两套命令的区别？

常用命令：
- 查看网络
```shell
 ifconfig
 ip show addr
```
- 配置网络
```shell
 ifconfig eth0 192.168.0.77
 ip address add 192.168.0.77 dev eth0
``` 
- 启用网络:
```shell
 ifconfig eth0 up
 ip link set eth0 up
``` 

另一种配置方式，直接修改文本: 
/etc/sysconfig/network-scripts

补充资料：https://p5r.uk/blog/2010/ifconfig-ip-comparison.html

#### 安装软件

rpm 
- 将光盘挂载到本地 mount -o loop /dev/cdrom /root/iso/
- 找到对对应的软件包，并安装命令 例如 rpm install ruby-2.0.0.648-30.el7.x86_64.rpm
- 卸载 umount /root/iso

yum（类似于这些 apt-get / gem / pipo / maven）
- yum install
- 什么是 yum 源
- 配置 yum 源 手动配置 /etc/yum.repos.d 使用命令配置 yum-config-manager

自己在网络上下载
- wget 

练习，在系统上使用 yum 的方式安装 node

####  Shell
 - 什么是 Shell ？
 - 你都知道那些常用的 Shell 命令？
 - 如何使用帮助文档 man  
 - 如何配置环境变量
 - bash 文件初始化顺序 https://www.jianshu.com/p/6a0047ad2d9e

