

# top命令详解

>The  top  program provides a dynamic real-time view of a running system.  It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.   The  types  of  system summary information shown and the types, order and size of information displayed for processes are all user configurable and that  configuration  can  be  made  persistent across restarts.
>
>1. top程序提供了一个观察系统运行时动态的、实时的视图。
>2. top展示两方面的信息：系统运行统计信息和进程信息。
>3. 显示内容可定制。



## 交互式运行top

`[andy@dreamworks ~]$ top`

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
  - M：按内存占用进行排序。
  - P：按CPU占用进行排序。
  - N：按PID进行排序。
  - T：按运行时间进行排序。
  - R：切换排序方式，生序或降序。
  - V：进程以树形结构显示。
  - z：切换显示方式，显示彩色或黑白。
  - Z：设置彩色模式。
  - x：高亮显示排序列。
  - y：高亮显示运行中程序。
  - X：设置字段显示宽度。
  - c：切换COMMAND列显示模式。
  - d：设置刷新时间间隔。
  - u/U：按用户进行过滤。
  - o/O：增加过滤条件。
  - n/#：设置显示进程列表数目。
  - j：控制字符左右对齐方式。
  - J：控制数字左右对齐方式。
  - H：切换第二行显示任务信息还是线程信息。
  - i：是否显示idle进程。
  - =：清空筛选条件。
  - L：按字符串查询。
  - &：查询下一个。
  - g：切换显示窗口，top默认有4个窗口，分别有不同的排序方式和显示字段列表。
  - A：切换显示单个窗口/多个窗口。
  - -/_：切换是否显示某个窗口或所有窗口。
  - E：切换summary area的内存显示单位。
  - e：切换列表区域的内存显示单位。
  - 



top命令行参数：

- -b：批处理模式，配合-n执行指定刷新次数，适用于生成系统探测文件。
- -c：同命令c。
- -E：设置内存显示单位。k，m，g。
- -H：显示thread，而非process。
- -i：是否显示idle进程。
- -n：刷新次数。
- -o：指定刷新字段，字段前可使用+或-指定排序方式。
- -O：输出所有可用字段名。
- -p：指定PID，进入交互界面后可通过=/u/U命令删除筛选条件。
- -S：显示累计占用CPU时间。
- -u/-U：指定显示指定用户的进程。-u筛选effective user。-U筛选任何用户（effective user, real user, saved user, filesystem）
- -w：输出宽度
- -1：多个CPU汇总输出还是单独输出。



> 技巧：
>
> 1. 手动刷新：将刷新间隔调到很大，然后需要刷新时按Space或Enter即可手动刷新。



