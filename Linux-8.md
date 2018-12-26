### Linux 补充知识 (一)

#### CPU 性能相关知识

- CPU 使用率
    - 用户 CPU 使用率 (包括用户态 CPU 使用率和低优先级用户态 CPU 使用率) 表示 CPU 在用户态运行时间百分比. 用户态 CPU 使用率高,通常说明有应用程序比较繁忙.
    - 系统 CPU 使用率 表示 CPU 内核态运行的时间百分比(不包括中断). 系统CPU使用率比较高, 说明内核比较繁忙.
    - 等待 IO 使用率 iowait 高, 说明系统与硬件设备的I/O交互时间比较长
    - 软中断 CPU 使用率 表示软中断程序的时间百分比, 如果比较高, 说明系统中有大量中断程序在运行
    - 硬中断 CPU 使用率 表示硬中断程序的时间百分比, 如果比较高, 说明系统中有大量中断程序在运行
    - 窃取 CPU 使用率 和 客户 CPU 使用率, 表示其他虚拟机占用 CPU 时间,和运行客户虚拟机的 CPU 使用率
- 平均负载
    - 表示过去 1 分钟, 5分钟, 15分钟的平均负载
    - 平均负载等于CPU的逻辑个数,说明 CPU 恰好被充分利用
- 进程上下文切换
    - 无法获取资源而导致的自愿上下文切换
    - 被系统强制调度导致的非自愿上下文切换
- CPU 缓存命中率

#### 性能相关工具

- 平均负载
    - uptime
    - top

- 系统整体 CPU 使用率
    - vmstat
    - mpstat
    - top
    - sar
    - /proc/stat

- 进程 CPU 使用率
    - top
    - pidstat
    - ps
    - htop
    - atop

- 系统上下文切换
    - vmstat

- 进程上下文切换
    - pidstat

- 软中断
    - top
    - /proc/softirqs
    - mpstat

- 硬中断
    - vmstat
    - /proc/interrupts

- 网络
    - dstat
    - sar
    - tcpdump

- IO
    - dstat
    - sar

- CPU个数
    - lscpu
    - /proc/cpuinfo

- 事件剖析
    - perf
    - execsnoop 用来监控短时进程