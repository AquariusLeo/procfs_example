# procfs_example

## 前言
本程序是为了《操作系统课程设计》（浙江大学出版社09年版 李善平著）第六章/proc实验而写，因书上及网络上的现有教程基本上都是10年以前内核2点几的，不再适用，故在3.10.0下写了此内核模块，发布出来。更高版本内核可能会有一些小问题，但大体相似，可自行百度解决。

## 功能描述
编写一个内核模块，该模块在/proc目录下创建我们自己的目录proc_example 然后在这个目录下创建三个普通文件（foo、bar、jiffies）和一个文件链接（jiffies_too）。foo和bar是两个可读写文件，各自实现读取操作函数与写入操作函数。jiffies是一个只读文件，取得当前系统时间jiffies。jiffies_too为文件jiffies的一个符号链接。

## 读写示例
write操作必须在root用户下进行  
![](https://ws1.sinaimg.cn/mw690/8d421749ly1g2qe3q0p9hj20iz07haam.jpg)

## 备注
测试使用的内核版本为3.10.0，其他版本内核可能会在读写操作函数的参数、copy_to_user、copy_from_user处报错，这是内核版本定义不同导致的，请自行百度函数原型

## 参考网址
https://blog.csdn.net/larry233/article/details/88093780?tdsourcetag=s_pctim_aiomsg
https://blog.csdn.net/caotuo_csdn/article/details/79172663

## 作者
zhangle
