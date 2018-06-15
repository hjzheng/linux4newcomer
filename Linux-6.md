### Linux 入门教程（六）

#### 函数
- 定义函数
```shell
function_name () {
   list of commands
}
```
- 函数传参 $1,$2 ... $*
- 函数返回值 return 只能返回数字 0 代表成功 非0 代表失败 与 exit 一致
- 获取函数返回值 $?
- 例子: 获取当前机器 mac 地址

```shell
get_mac_addr() {
    MAC_ADDR=`/sbin/ifconfig $1 | grep ether | awk '{print $2}'`
}

get_mac_addr enp0s3
echo $?
echo $MAC_ADDR
```
