#DOL开发环境配置安装报告
14353195_刘畅
***
##一.DOL框架描述  
分布式操作层（DOL）是一个程序的并行应用软件开发框架。DOL允许指定基于计算Kahn进程网络模型的应用范围和特点，基于SystemC仿真引擎。此外，DOL提供了基于XML规范的格式来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。
##二.DOL安装笔记
###1.安装一些必要的环境：
$ sudo apt-get update  
$ sudo apt-get install ant  
$ sudo apt-get install openidk-7-idk  
$ sudo apt-get install ant
![](http://p1.bpimg.com/567571/798ac5db209dceb8.jpg)
###2.下载文件：
$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz  
$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
###3.解压文件：
新建dol的文件夹：  
$ mkdir dol  
将dolethz.zip解压到 dol文件夹中：  
$ unzip dol_ethz.zip -d dol   
解压systemc：  
$ tar -zxvf systemc-2.3.1.tgz   
###4.编译systemc：  
解压后进入systemc-2.3.1的目录下：  
$ cd systemc-2.3.1  
新建一个临时文件夹objdir：  
$ mkdir objdir  
进入该文件夹objdir：  
$ cd objdir  
运行configure：  
$ ../configure CXX=g++ --disable-async-updates  
编译：  
$ sudo make install  
记录当前的工作路径：  
$ pwd  
![](http://p1.bpimg.com/567571/34c4b36b7fc0aa2e.jpg)
###5.编译DOL：  
进入刚刚的dol文件夹，修改build.xml文件，把YYY改成上页pwd的结果：  
![](http://p1.bpimg.com/567571/81d1c57a80930f0b.png)
编译：  
$ ant -f build_zip.xml all  
若成功会显示build sucessful   
###6.运行一个例子：  
进入build/bin/main路径下：  
$ cd build/bin/main  
然后运行第一个例子 ：    
$ ant -f runexample.xml -Dnumber=1  
![](http://p1.bpimg.com/567571/21ad8814ea2ebeed.jpg)
##三.实验感想
在之前Ubuntu配置良好的情况下，跟着教程上的步骤输入命令行，配置DOL比较顺利，基本没有遇到大问题。当然配置环境只是实验的基础，以后的实验中会运用到这个开发环境，到那时才会对DOL有比较深刻的理解。
