### Linux 入门教程（三）

#### 文件内容	(处理文本流)
	- grep
		- grep something file
		- -i 不区分大小写 
		- -v 结果取反
		- -n 打印出行号
		- -l 只显示匹配到的文件名
		- -e 正则表达式
	- sort
		- cat /etc/passwd | sort -t : -k 7
	- tr
		- cat /etc/passwd | sort -t : -k 7 -u | tr [a-z] [A-Z]
	- diff
	- wc
		- wc -l
	- sed (神器)
	- awk (神器)

#### 管道和重定向
	- stdin 0, stdout 1, stderr 2
	- ls -l > stdout.txt, ls -l >> stdout.txt
	- ls -l 2> stderr.txt 1> stdout.txt
	- ls -l &> out.txt
	- here document

	cat < file << HERE
		This is a test
		This is a test
	HERE

#### 脚本录制
	script 和 scriptreplay

	```shell
	script --timing=file.tm script.out
   	... ...(你的操作)
   	exit   (退出录制)
    scriptreplay --timing file.tm --typescript script.out
	```	
