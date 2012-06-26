---
layout: post
title: "windows XP常见问题"
date: 2012-06-26 16:36
comments: true
categories: WinXP
---
问题一：如何清除「我的计算机」中那些碍眼的分享数据夹？
方法：请从registry删掉以下code
HKEY_LOCAL_MACHINE \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Explorer \\ My Computer \\ NameSpace \\ DelegateFolders \\ {59031a47-3f72-44a7-89c5-5595fe6b30ee}
问题二：如何加快XP的开关机？
方法：
1.开启注册表编辑器，找到 HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Control，
将 WaitToKillServiceTimeout 设为：1000或更小。
找到 HKEY_CURRENT_USER\\Control Panel\\Desktop 键，将右边窗口的 WaitToKillAppTimeout 改为 1000，
即关闭程序时仅等待1秒。将 HungAppTimeout 值改为：200，表示程序出错时等待0.5秒。
让系统自动关闭停止响应的程序。打开注册表 HKEY_CURRENT_USER\\Control Panel\\Desktop 键，
将 AutoEndTasks 值设为 1。
2.控制台-->系统设定公用程序-->服务-->NVIDIA DRIVER Helper Service取消掉

问题三：如何加快选单显示速度 ？
开启注册表编辑器，找到 HKEY_CURRENT_USER\\Control Panel\\Desktop，
将其下的 MenuShowDelay 项改为：0，你的选单将会出乎意料地快。

二、『XP系统减肥法』
问题一：如何节省XP所占空间？
方法：
1. 删除系统文件备份
sfc.exe /purgecache
2 删除驱动备份
windows\driver cache\i386目录下的Driver.cab文件 （73mb)
3. 取消系统还原
4、删除Help档（减掉40多mb)
5、删掉C:\WINDOWS\system32\dllcache下档（减去200——300mb),这是备用的dll檔，
只要你已拷贝了安装文件，完全可以这样做。
6、把我的文件、IE的临时文件夹都转到其它硬盘（分区）。
7、把虚拟内存也转到其它硬盘。
8、将应用软件装在其它硬盘（这对重装系统也有好处）。
9、删除C:\windows\ime下不用的输入法！ （日文，韩文，简体中文输入法，84.5MB）
10、若使用NTFS格式安装xp，NTFS有内建压缩功\能，可省30%。

三、『XP系统版本』
问题一：如何知道XP已启动？
方法：
1.执行 oobe/msoobe /a
如果出现「Windows 产品启用 ，Windows 已经启用。请按[确定]结束 」
则已启动。
2.
开始-->执行-->regedit
HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion]
将 \"RegDone\" = 的数值，由 \"0\" 改成 \"1\"

问题二：如何知道XP的版本？
方法：
1.找寻计算机中windows/system32/NTOSKRNL.EXE 的这个档-->按右键-->选内容
2.辨认真假中文版XP的方法
(1)执行超级终端机.是否为中文接口及中文名称抬头
(2).寻找dxdiag.exe并执行.看看directx诊断程序中的系统信息
-->看看系统信息中的操作系统版本是否为5.1build2600
-->看看系统信息中的语言及区域设定是否都为中文

四、『XP疑难杂症』
问题一：如何制作开机磁盘？
方法：
在A槽-->按右键-->选格式化-->选建立一个MS-DOS开机磁盘
问题二：如何设定ADSL？
方法：
控制台-->网络联机-->建立一个新联机-->联机到因特网
-->手动设定我的联机-->使用需要使用者名称和密码的宽带联机来联机
-->ISP名称(随便填你想要的,如Hinet...)-->使用者名称.密码就填拨接账号与密码
-->下面3选项看需要可选可不选(其实XP内建的防火墙功\能不错)-->完成
P.S 如要开机就自动拨接上网的话,把联机ICON抓到启动中即可。
问题三：如何设定网络芳邻？
方法：
控制台-->使用者账户-->建立新的账户
-->输入那台计算机的开机账号(计算机名称)及密码
-->选择\"受限制的账户\"-->完成

问题四：如何开启DMA？
方法：
到装置管理员里选择IDE ATA/ATAPI controllers
到Primary/Secondary IDE Channel里面的进阶设定
将所有的转送模式都设定为使用DMA(如果可用的话)
系统就会自动打开DMA支持(在BIOS里也应该要先设为支持DMA)
问题五：如何关闭Autorun？
方法：
1.打开光驱的内容,将自动拨放里所有的光盘格式都设为不要有任何动作
2.利用Group Policy (执行gpedit.msc)
到计算机设定-->系统管理模板-->系统
找到-->关闭自动拨放
按右键选-->内容,选择已-->启用,
在下面那里选-->所有的磁盘驱动器,
然后套用,重新开机,应该也可以,但是这个方法不能关闭音乐CD的自动拨放
3.regedit
HKEY_LOCAL_MACHINE\\SYSTEM\\ControlSet001\\Services\\Cdrom
将Autorun原本的0x00000001(1)的执中的1改为0
改完后会变成0x00000000(0)这样就可以了.

问题六：XP如何才能关机？
方法：
控制台-->电源-->显示-->屏幕保护程序-->电源管理-->APM打勾
如果还不行,应该是BIOS的问题
问题七：如何关闭系统休眠功\能？
方法：
因为休眠功\能占的硬盘空间蛮大的，所以关闭比较好。
控制台-->电源选项-->休眠(不要打勾)

问题八：如何关闭错误回报？
方法：
控制台---->系统---->进阶---->右下角--->错误报告---->关闭
问题九：无法安装驱动程序？
方法：
XP安装驱动程序往往因为数字签署的关系挂不上去，把数字签署忽略：
控制台-->系统-->硬件-->装置管理员-->驱动程序签署-->略过

问题十：WinXP执行时候为什么都会停顿一下呢？
方法：
开始-->联机-->显示所有联机-->局域网络-->右键选内容
一般-->选Internet Protocol(TCP/IP)-->按内容
使用下列的ip地址第一个192.168.0.1，第二个打255.255.255.0即可。

问题十一：为什么XP会不定时自动重开机？
方法：
我的计算机-->按右键-->内容-->进阶-->启动修复的设定
在系统错误下方有三个勾：将自动重新启动取消即可

问题十二：我找不到新的指令？
方法：
执行列上输入：
msconfig=>设定开始功\能表
ipconfig=>设定网络卡与寻找IP

问题十三：如何让XP自动联机 ？
方法：
1.IE-->工具-->因特网选项-->联机
勾选 \"网络不存在时拨号\" ，把 IE 拉到 \"启动\"
每次开机完成后 , 你已经上线了 !
2. 进入联机内容，把「提示名称、密码、凭证」等的勾勾取消掉，
然后把该联机拉到「启动」。

问题十四：如何关闭winXP的自动更新？
方法：
控制台-->系统-->自动更新，进到里面勾选关闭即可。
问题十五：如何全新安装XP？
方法：
a. 若是FAT partition请直接利用Windows 98或Windows Millennium开机片来 执行FDISK或
formAT
b. 若是NTFS partition请直接透过Windows XP光盘片，使用CD-ROM开机，来
将NTFS的partition删除并重建。

a. 请至Windows XP所在的partition，删除下列目录及档案：Pagefile.sys, NTDETECT.COM及 NTLDR文件( 位于开机磁盘如C: )及一些Windows XP相关的目录及档案
b. 用Windows 98或Windows Millennium开机磁盘来开机，并在A：＞ 模式下，执行sys c: 指令
将系统回复至Windows 98或Windows Millennium。
< Windows XP与Windows NT 4.0或Windows 2000并存>
a.请至Windows XP所在的partition，删除下列目录及档案WINNT(请确定这是Windows XP的主目录而非Windows NT 4.0或Windows 2000)Pagefile.sys, NTDETECT.COM及NTLDR文件( 位于开机磁盘如C: )及一些Windows XP相关的目录及档案。
b. 修改启动扇区根目录下Boot.ini之内容：
[boot loader]设定值下的ARC设定，变更预设的开机操作系统。例如，您
原来Windows NT 4.0/2000是装在第一颗实体硬盘的第一个partition，您可参
考以下ARC设定：
default=multi(0)disk(0)rdisk(0)partition(1)
[operating systems]设定值下的ARC设定，删除Windows XP的开机选项
c. 重灌最新的service pack版本；例如：SP6a for WinNT或SP2 for WIN2000

问题十六：如何看ip？
方法：
控制台-->网络联机-->开启联机内容-->勾选图标显现再通知区域内
要看ip就点两下图示-->选支持就看的到了，很方便。
问题十七：如何使用pppoe自动联机？
方法：
1.首先需要确定你的RasPPPoE联机已经正确拨上过
并且储存密码(SavePassword)选项已勾选
2.于『网络上的芳邻』上按鼠标右键并点选『内容』选项
3.在出现的窗口中RasPPPoE建立的联机(以下称预设联机)上按鼠标右键点选『内容』选项
4.将『设定』页中所有的选取方块勾勾取消
5.将重拨设定中的『闲置过久时自动中断』的功\能选择『永不中断』
6.将重拨设定中的『断线后自动联机』功\能打勾
7.按下方的确定键储存设定
8.点选『开始』功\能表…选择『设定』下的『控制台』
9.于『排定的工作』上点鼠标两下
10.点选『新增排定的工作』两下
11.点选『下一步』
12.点选『浏灠』
13.选择『C:\\WinNT\\System32\\RasPhone.exe』并按开启
14.选择『在您的计算机启动时自动执行』
15.点选「下一步』
16.输入系统管理员(Administrator)之登入账号以及登入密码
17.点选『下一步』
18.点选『完成』
19.于上面步骤新增的工作图标上按鼠标右键并点选内容
20.将执行的文字框中的『C:\\WinNt\\System32\\RasPhone.exe』改为
『C:\\WinNt\\System32\\RasPhone.exe -d 预设联机』
21.将『设定』页中所有的勾勾取消
22.按『确定』键套用新的设定(会要求输入Administrator的密码确认)
23.点选『开始』功\能表…选择『执行』
24.于开启文字框中填入『Regedit』并按确定
25.寻找下列地址
『HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon』
26.在上面之地址按鼠标右键…选择『新增\\字符串』
27.将新的字符串名称『新数值 #1』改为『KeepRasConnections』
28.在字符串上按鼠标右键…选择『修改』
29.将值的数据填入『1』(数字的1)
30.重新开机即可完成设定，使Windows2000不需登入系统即自动连上网络

问题十七：如何作XP免序号光盘？
方法：
将下列文字复制存成Winnt.sif
再置入i386数据夹中即可。
-----
[UserData]
ProductKey=FCKGW-RHQQ2-YXRKT-8TG6W-2B7Q8
[Data]
AutoPartition=0
MSDosInitiated=0
UnattendedInstall=Yes
[Unattended]
UnattendMode=GuiAttended
TargetPath=WINNT
Hibernation=1
OemPreinstall=No
OemSkipEula=Yes
CrashDumpSetting=0
DisableDynamicUpdates=Yes
UnattendSwitch=Yes
------ 
