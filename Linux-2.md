### Linux 入门教程（二）

#### 文件类型
	- - 常规文件
	- l 符号链接 指向系统中另一个文件的文件
	- c 字符设备文件 提供一种机制，使得和设备通信时，传输单个字符
	- b 块设备文件 提供一种机制，使得和设备通信时，传输大块数据
	- p 命名管道 自己有兴趣，可以查查
	- d 目录文件

#### 文件权限
    - r（4） w（2） x（1）
    - 修改文件权限 chmod

#### 用户和组
    - 创建用户
    	- 例如 useradd -m lymeng
    	- 修改密码 passwd lymeng
    	- 查看所有用户 /etc/passwd
    - 创建组
    	- 例如 addgroup xafe
    	- 查看所有用户 /etc/group
    - 给目录添加组的权限
    	- chown -R :xafe /xafe 	
    - 改变用户所属组	
		- usermod -a -G xafe lymeng

	https://www.linux.com/learn/intro-to-linux/2017/12/how-manage-users-groups-linux
	备注: 本节不要求重点掌握	

#### 文件操作
	- 创建文件 touch 
	- 编辑文件 vim
	- 查看文件 cat tail head less more
		- tail -f tail -12 | wc -l head -12 | wc -l
	- 复制或移动文件 cp mv
	- 删除文件 rm

#### 目录操作
    - 查看目录 ls
    - 创建目录 mkdir
    	- mkdir -p /home/lymeng/code/ccms
    - 拷贝或移动目录 mv -r 
    - 删除目录 rm -r

#### 创建链接（重点）
	- 符号链接（symbolic link） ln -s
	- hard link
	- 作业: 上面两种链接的区别

#### 查找文件（重点）
	- find  例如 find /root/ccms_node -name login* -type f | xargs ls -al 
	- locate

