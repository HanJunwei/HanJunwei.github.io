> Summarize disk usage of the set of FILEs, recursively for directories.
>
> The Linux “**du**” (**Disk Usage**) is a standard **Unix/Linux** command, used to check the information of disk usage of files and directories on a machine. The **du** command has many parameter options that can be used to get the results in many formats. The **du** command also displays the files and directory sizes in a recursively manner.
>
> du命令用来计算文件或目录占用的磁盘空间。



```shell
du [option]... [file]...

-a：计算所有文件和目录占用磁盘空间，默认只显示目录占用的空间。
-s：显示目录或文件的汇总信息，没有参数时代表当前目录，可接一个或多个文件或目录。
-h：用便于人阅读的大小格式显示。
-d/--max-depth：指定输出目录深度。

-b：输出单位是字节数。
-k：--block-size=1K，输出单位是KB。
-m：--block-size=1M，输出单位是MB。
-c：列出汇总信息。
-S：显示目录的大小，但不包括子目录。
--time：显示目录或文件的最后修改时间。
--inodes：列出inode使用情况，而非硬盘空间使用情况。
--exclude：统计时剔除某些文件，如--exclude="*.txt"，代表剔除txt文件。

```



> **Important:** be careful with default du behavior, because depending on your Unix OS, it may use different block size for reporting the size. <u>Older systems would use 512-byte blocks, while most of the recent releases use 1024-byte ones</u>. To avoid any confusion, get used to specifying the desired block size with -k parameter (see below).
>
> Like it was mentioned before, <u>du calculates all the sizes in blocks of data. All the reports you see are not bytes or kilobytes, but the block sizes</u> – so it’s good to always remember this. In most cases these days, **the default block size is 1024 bytes**, so you are effectively looking at all the sizes reported in kilobytes, but to make sure it’s always the case I advise you to use -k parameter which overrides you Unix flavour default block size and sets it to 1024 bytes.
>
> 通常Linux的“block size”指的是1024 bytes，Linux用1024-byte blocks 作为buffer cache的基本单位。但linux的文件系统的block size确不一样。例如ext3系统，block size是4096。
>
> The “apparent size” of a file is how much data is actually in the file. 指文件实际大小，默认情况下是占用硬盘的空间，硬盘一般按4KB作为一个单位进行分配，所以显示的会大。
>
> The "apparent size" of a file is how much valid data is actually in the file. It is the actual amount of data that can be read from the file. Block-oriented devices can only store in terms of blocks, not bytes. As a result, the disk usage is always rounded up to the next highest block. 
>
> [tips for apparent size option](https://unix.stackexchange.com/questions/173947/du-s-apparent-size-vs-du-s)



查看文件系统block size配置：

```shell
tune2fs -l /dev/sda1 | grep "Block size"

dumpe2fs /dev/sda1 | grep "Block size"
```



遗留问题：

```shell
1. 目录占用多大空间，如何查看目录内容？
[root@dreamworks tmp]# tree test
test

0 directories, 0 files

[root@dreamworks tmp]# du --apparent-size --block-size=1 test
6	test

[root@dreamworks tmp]# du  --block-size=1 test
0	test

2. dereferrence相关的参数用途尚未实验。
```

