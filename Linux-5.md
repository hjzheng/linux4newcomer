### Linux 入门教程（五）

#### Shell 脚本
- 以 Jenkins 中的前端部署脚本或者 .bash_profile  .bashrc 为例。 
- #!/bin/sh
- chmod 755 your_file
- ./your_file
- 添加 your_file 到环境变量 PATH
- 例子
```shell
#!/bin/sh
echo $1
```

#### 变量与环境变量
- name=hjzheng
- export PATH=$PATH:/home/${name}/bin
- 变量访问
- 特殊变量
  - $1-9 脚本执行时的参数1到参数9
  - $? 脚本的返回值
  - $# 脚本执行时，输入的参数的个数
  - $@ 输入的参数的具体内容（将输入的参数作为一个多个对象，即是所有参数的一个列表）
  - $* 输入的参数的具体内容（将输入的参数作为一个单词）

#### 注释
- `#` 以“#”开头的行就是注释，会被解释器忽略

#### 字符串 （可以参见 https://github.com/qinjx/30min_guides/blob/master/shell.md）
- 单引号字符串的限制：
  - 单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的
  - 单引号字串中不能出现单引号（对单引号使用转义符后也不行）
- 双引号
  - 双引号里可以有变量
  - 双引号里可以出现转义字符
- 字符串操作
  - 拼接字符串
  - 获取字符串长度
  - 提取子字符串	

#### 数组
- 声明一个数组 name[index]=value
- 例如
```shell
name[0]=hjzheng
name[1]=fyang
name[2]=lymeng
```
- 数组访问 ${name[index]}
- 访问所有数组项 ${name[*]} 或 ${name[@]}

#### 条件 
- 写法
```shell	
#!/bin/sh
# if 格式
# if list1; then
#    list2
# elif list3; then
#    list4
# else
#    list5
# fi

if ls /root &> /dev/null; then
	echo 'command ls /root run successfully'
fi

if ls + &> /dev/null; then
	echo 'command ls + run successfully'
else
	echo 'command ls + run, error'
fi
```
- 条件判断
  - test 或 []
  - 目录判断
    - 语法: test operation file 或者 [ operation file ]
    - 常用的 operation:
      - -d 目录是否存在
      - -f 文件是否存在
      - -e 文件或目录是否存在
      - -x 文件或目录是否可执行（对于目录是否可以访问）
      - 等等
      - 举例: .bash_profile
  - 字符串比较
    - 语法同上
     - -z str str 长度为 0 时返回真
     - -n str str 长度非 0 时返回真
     - str1 = str2
     - str1! = str2
  - 数字比较
    - int1 -eq int2 等于
    - int1 -ne int2 不等于
    - int1 -lt int2 小于
    - int1 -le int2 小于等于
    - int1 -gt int2 大于
    - int1 -ge int2 大于等于
  - 复杂表达式
    - ! 取反
    - -a 且
    - -o 或
  - 举例: /etc/sysconfig/network-scripts/ifup	
#### 循环
- 写法
  - while
  - util
  - select
  - for
- 例子: grep -n while /etc/sysconfig/network-scripts/*	
- 练习写一个进度条	

#### 如何调试 Shell 脚本
- sh -n your_script #语法检测	
- sh -x	your_script #调试脚本

```shell
set -x　#启动"-x"选项 
要跟踪的程序段 
set +x　#关闭"-x"选项	 	
```
