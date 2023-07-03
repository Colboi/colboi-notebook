来源：[hosts文件在哪？什么修改？另附Windows7/8/10 Mac/iPhone原版hosts文件](https://laod.cn/2411.html)
# hosts概述
hosts是一个没有扩展名的系统文件，可以用记事本等工具打开，其作用就是将一些常用的网址域名与其对应的IP地址建立一个关联“数据库”，当用户在浏览器中输入一个需要登录的网址时，系统会首先自动从Hosts文件中寻找对应的IP地址，一旦找到，系统会立即打开对应网页，如果没有找到，则系统会再将网址提交DNS域名解析服务器进行IP地址的解析

# hosts文件位置
- **Windows**：`C:\Windows\System32\drivers\etc\hosts`
- **Android**（安卓）：`/system/etc/hosts`
- **Mac**（苹果电脑）：`/etc/hosts`
- **iPhone**（iOS）：`/etc/hosts`
- **Linux**：`/etc/hosts`

# 修改
可以用**记事本**打开并修改

**注意：** hosts文件属于系统核心文件之一，所以Windows用户必须用管理员身份打开才能修改保存，如果遇到无法保存，请右键文件hosts并找到 **“属性” -> “安全”** ，然后选择你登陆的用户名，最后点击编辑，勾选 **“写入”** 即可。

Android（安卓）必须Root才能修改，Root Explorer管理器或ES文件浏览器装载`/system`**可写**状态，找到 **/system/etc/hosts** 的文件，使用文本编辑器打开编辑后保存。

Linux系统使用Root权限`vi`编辑

而iPhone、iPad也必须越狱才能修改！Windows系统跟苹果系统的hosts文件文本编码和换行符格式一样，而Android（安卓）则不一样，这点你需要注意。

# 原版hosts文件
Windows：
```
# Copyright (c) 1993-2009 Microsoft Corp.  
#  
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.  
#  
# This file contains the mappings of IP addresses to host names. Each  
# entry should be kept on an individual line. The IP address should  
# be placed in the first column followed by the corresponding host name.  
# The IP address and the host name should be separated by at least one  
# space.  
#  
# Additionally, comments (such as these) may be inserted on individual  
# lines or following the machine name denoted by a ‘#’ symbol.  
#  
# For example:  
#  
# 102.54.94.97 rhino.acme.com # source server  
# 38.25.63.10 x.acme.com # x client host

# localhost name resolution is handled within DNS itself.  
# 127.0.0.1 localhost  
# ::1 localhost  
```

Mac、iPhone、iPad：
```
##  
# Host Database  
#  
# localhost is used to configure the loopback interface  
# when the system is booting. Do not change this entry.  
##  
127.0.0.1 localhost  
255.255.255.255 broadcasthost  
::1 localhost  
fe80::10 localhost  
```
原版的hosts文件前面都带有井号“#”，以#开头的都是注释用的，所以并没什么卵用，如果你想快速恢复原版hosts文件，那么也可以直接清空里边的内容，一般情况没有什么影响。

# 保存修改
- Windows：开始 -> 运行 -> 输入cmd -> 在CMD窗口输入：`ipconfig /flushdns`
- Linux：终端输入`sudo rcnscd restart`。对于systemd发行版，请使用命令  `sudo systemctl restart NetworkManager`
- Mac OS X：终端输入`sudo killall -HUP mDNSResponder`
- Android：开启飞行模式 -> 关闭飞行模式
**通用办法：**
- 拔网线（断网）->插网线（重新连接网络）
- 重启系统
- 清空浏览器缓存

# 拓展
[苹果Mac OS系统修改Hosts文件的方法](https://laod.cn/hosts/mac-os-xiugai-hosts.html)
[iPhone iPad等iOS 设备上配置修改 hosts 方法](https://laod.cn/hosts/iphone-ipad-ios-hosts.html)
[Android修改hosts文件的方法介绍](https://laod.cn/hosts/android-hosts.html)
