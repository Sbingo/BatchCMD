wifi下调试app：

AS中也有相应的插件

前提：

1.手机和电脑在同一个局域网

2.断开其他adb连接

命令：

//adb从usb模式转化成adb网络模式

adb tcpip 5555

//输入手机的ip

adb connect 192.168.1.129

//切换回usb模式

adb usb

