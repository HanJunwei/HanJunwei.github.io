# top命令详解

>The  top  program provides a dynamic real-time view of a running system.  It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.   The  types  of  system summary information shown and the types, order and size of information displayed for processes are all user configurable and that  configuration  can  be  made  persistent across restarts.
>
>1. top程序提供了一个观察系统运行时动态的、实时的视图。
>2. top展示两方面的信息：系统运行统计信息和进程信息。
>3. 显示内容可定制。



## 交互式运行top

`[andy@dreamworks ~]$ top`

top程序的交互界面如下：

![top-1](https://github.com/HanJunwei/HanJunwei.github.io/blob/main/system-admin-cmd/images/top-1.jpg)



top交互界面分为上下两个部分：

- 上半部分显示系统资源统计信息
  - 第一行显示`系统当前时间 系统运行时间 系统最近1分钟、5分钟、15分钟负载`
  - 第二行显示`系统总任务数 运行中任务数 睡眠中任务数 已停止任务数 僵尸任务数 `
  - 第三行显示`用户态非nice进程占用CPU百分比 系统态占用CPU百分比 用户态nice进程占用CPU百分比 CPU闲置百分比 等待IO占用百分比 硬中断占用百分比 软中断占用百分比 虚拟机占用百分比`
  - 第四行显示`总物理内存 可用内存 已使用内存 用作缓冲区的内存`
  - 第五行显示`总虚拟内存  可用虚拟内存 已用虚拟内存 物理内存再用多少会开始占用虚拟内存`
  - 第六行显示`此处是输入和运行命令第地方`
- 下半部分显示进程列表
  - F：选择显示哪些字段和设置字段前后顺序，并可设置按哪个字段进行排序。
    - s：设置按当前选择字段进行排序。
    - d：选中或反选当前字段。
    - q：退出。





