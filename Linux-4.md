### Linux 入门教程（四）

#### 了解自己的系统
	- OS 
		- uname -a
		- cat /etc/redhat-release (for centos or redhat)
	- CPU cat /proc/cpuinfo | grep processor | wc -l
	- 内存 
		- cat /proc/meminfo
		- free
	- 磁盘信息
		- df -h
		- fdisk -l
	- 网络
		- nmcli dev status 查看网卡设备连接情况
		- ss -tubna 等价 netstat -tulpna
	- 进程
		- top
		- ps -ef	