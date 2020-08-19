## 软硬件准备

软件：VMware-workstation-full-15.5.6-16341506

镜像：CentOS7。

VMware安装好之后，下载需要安装的centOS_7_X64操作系统的[镜像文件](http://isoredirect.centos.org/centos/7/isos/x86_64/)。

## 虚拟机准备

1、进入主页选择[创建新的虚拟机](https://blog.csdn.net/java_xinshou1/article/details/100010099)

2、典型安装和自定义安装

典型安装会将主流的配置应用在虚拟机的操作系统上

自定义安装可以针对性的把一些资源加强，把不需要的资源移除。

此处选择自定义安装。

3、选择安装光盘映像文件(iso)：选择下载好的CentOS的iso文件所在位置

4、操作系统的选择：选择Linux下的CentOS

5、虚拟机位置和命名：默认在C盘，可以修改盘符

6、处理器和内存分配：选择的2个处理器，每个处理器的核心数量为2。

​                                        虚拟机的内存分配1024MB

7、网络连接类型的选择：有桥接、NAT、仅主机和不联网四种，选择NAT模式（虚拟机联网先通过宿主机才能和外面进行通信）

8、磁盘容量：设置的20GB，选择`将虚拟磁盘拆分为多个文件`项

9、可以自定义取消不需要的硬件：声卡、打印机等

### 安装CentOS

1、连接光盘，开启此虚拟机

2、安装操作系统：开机虚拟机后会出现一下界面，选择第一项，回车直接安装

​								Install CentOS 7 安装CentOS 7

​								Test this media & install CentOS 7 测试安装文件并安装CentOS 7

​								Troubleshooting 修复故障



3、选择英文，美式键盘

4、设置时间，需要安装的软件（建议选择Server with GUI）

5、磁盘划分：选择自动划分

6、设置root密码，点击USER CREATION创建管理员账户

7、等待安装完毕reboot系统，到登录界面输入密码登录。

## 存在问题

### 主板没有支持虚拟化

进入bios界面，enable CPU虚拟化，联想主板F2进入

### 安装VMware tool

虚拟机和主机之间要实现复制粘贴文档文件或文字，需要安装vmware tool工具。

1、打开VMware窗口`虚拟机`，显示`安装VMware Tools`，会在桌面出现一个光盘图标，双击进入

2、进入光盘找到VMwareTools-10.0.5-3228253.tar.gz压缩文件（可能版本不对应）。打开终端，执行命令安装。

```
tar -zxf VMwareTools-10.0.5-3228253.tar.gz -C ~  #解压到当前用户的根目录
cd ~/vmware-tools-distrib  
su  #切换到管理员
sudo ./vmware-install.pl  #开始安装

#安装过程除了第一步yes外，其余都直接回车默认选项
```

3、检查【虚拟机设置】→【选项】中客户机隔离中`启用拖放、启用复制粘贴`是否勾选上，默认已勾选上

4、安装完成之后，进入`/usr/bin`目录，然后执行`./vmware-user`命令，就可实现复制拖放。

### 安装VMware tools选项显示重装灰色解决办法

1、关闭虚拟机

2、在虚拟机设置中设置CD/DVD为自动检测，如果有CD/DVD和软盘也设置为此

3、再重启虚拟机即可



## 安装epics

操作系统：CentOS-7-x86_64-DVD-2003

EPICS Base：baseR3.14.12.8

### Base安装

1、打开终端，以root账户登录

2、进入`\usr\local`目录下，新建文件夹`epics`，并进入该文件夹

3、下载[EPICS Base](https://epics.anl.gov/base/R3-14/12.php)，拷贝到虚拟机的`epics`文件夹下

4、在`\usr\local\epics`目录下，解压该文件`tar -zxvf baseR3.14.12.8.tar.gz `

5、重命名`mv baseR3.14.12.8 base`

6、安装相关依赖：

​              `yum install gcc`

​              `yum install gcc-c++`

​              `yum install readline-devel`

7、进入`base`文件夹下编译：

​              `cd /usr/local/epics/base/startup`

​              `./EpicsHostArch`

![startup](\vmware虚拟机安装epics过程\startup.PNG)

8、切回到根目录修改`.bashrc`文件内容，添加环境变量

​              `vi /root/.bashrc` 输入：

              ```
EPICS_HOST_ARCH=linux-x86_64
export EPICS_HOST_ARCH
PATH=$PATH:/usr/local/epics/base/bin/linux-x86_64/
export PATH
EPICS_BASE=/usr/local/epics/base/
export EPICS_BASE
              ```

![bashrc](\vmware虚拟机安装epics过程\bashrc.PNG)

9、修改完保存，更新环境变量

​               `source /root/.bashrc`

10、在`base`目录下编译

​               `cd /usr/local/epics/base`

​               `make clean && make`

11、在`\usr\local\epics\base\bin\linux-x86_64`目录下可看到一系列文件，Base安装成功。

![base安装成功结果](\vmware虚拟机安装epics过程\base安装成功结果.PNG)

### 安装IOC实例

1、创建放置IOC实例的目录`top`

​               `mkdir -p /usr/local/epics/base/top`

2、查看路径，复制路径，将路径添加到`\root\.bash_profile`的PATH后面

![查看路径](\vmware虚拟机安装epics过程\查看路径.PNG)

![bash_profile](\vmware虚拟机安装epics过程\bash_profile.PNG)

3、修改完，更新环境变量

​               `source /root/.bash_profile`

4、在`top`目录下利用`makeBaseApp.pl`建立一个IOC实例

```
cd /usr/local/epics/base/top

/usr/local/epics/base/bin/linux-x86_64/makeBaseApp.pl -t example firstIoc

/usr/local/epics/base/bin/linux-x86_64/makeBaseApp.pl -i -t example firstIocBoot
```

输入启动名字`firstIoc`

![IOC实例](\vmware虚拟机安装epics过程\IOC实例.PNG)

5、在`top`目录下进行编译

​                `make clean && make`

6、给`iocfirstIocBoot`目录下的`st.cmd`增加权限

```
cd /usr/local/epics/base/top/iocBoot/iocfirstIocBoot
chmod +x st.cmd
./st.cmd   #运行st.cmd
```

7、输入指令`dbl`，可查看安装结果

![Ioc安装结果](\vmware虚拟机安装epics过程\Ioc安装结果.PNG)



## 参考资料

[VMware虚拟机安装详细教程](https://blog.csdn.net/java_xinshou1/article/details/100010099)

[VMware安装Centos7超详细过程](https://blog.csdn.net/babyxue/article/details/80970526)

[VMware 实现主机与虚拟机间文件的复制与拖放](https://blog.csdn.net/y_k_y/article/details/82857745)

[安装VMware Tools选项显示灰色的正确解决办法](https://blog.csdn.net/qq_40259641/article/details/79022844)

[基于CentOS系统部署EPICS环境](https://www.bbsmax.com/A/kPzO41E3Jx/)

[CentOS7安装EPICS Base与建立IOC实例](https://blog.csdn.net/qq_34885184/article/details/88088502)