# 1.官方资源介绍
资料分为两个部分：应用开发、设备开发。应用开发主要是上层，本文的重心主要在设备开发上。
## 华为官网
主页：
https://www.harmonyos.com/cn/home/
设备开发：
https://device.harmonyos.com/cn/docs/develop/demo/oem_wifi_sdk_dev-0000001050982229
CMSIS-RTOSV2:
https://arm-software.github.io/CMSIS_5/RTOS2/html/rtos_api2.html#rtos_api2_functions



## 发烧友论坛
https://bbs.elecfans.com/jishu_1989262_1_1.html
资料汇总：
https://bbs.elecfans.com/jishu_1991869_1_1.html
Hi3861V100软件开发资料(32份):
https://bbs.elecfans.com/jishu_1994271_1_1.html
旗点科技连志安老师国庆假期Hi3861_WiFi_IoT精彩文章集锦:
https://bbs.elecfans.com/jishu_1995610_1_1.html


## 51cot
https://harmonyos.51cto.com/user/posts/14630655

# 2. hpm && npm安装：
https://www.imooc.com/article/310925?block_id=tuijian_wz
## 安装操作：
https://www.cnblogs.com/liuqiyun/p/8133904.html
## 替换软件源：
https://www.colabug.com/2020/0407/7216390/

# 3. JDK安装教程
https://jingyan.baidu.com/article/ce09321b85e8d62bff858f93.html

老子跑起来了：

![image-20201021194746246](C:\Users\songz\Pictures\博客截图\image-20201021194746246.png)

------

# 以下为不完全沙雕随笔

## HI3861的环境搭建

在windows系统的 HarmonyOS IDE下的编译功能暂时是无法使用的（感觉华为在赶工期所以windows下的东西都没给全，目前官网的教程上也是采用了windosw下写代码，Linux去编译的方式），因此暂时只能按官网文档的教程去搭建。

在搭建的过程中可以将apt以及python的pip更换成国内源来提高下载速度。或者采用群友们的docker一键搭建环境工具（未验证）。

## 润和的开发视频：

http://t.elecfans.com/live/1325.html?room=1

https://bbs.elecfans.com/jishu_1998840_1_1.html



## AT指令测试

1. 在IPOP串口终端中，依次执行如下AT命令，启动STA模式，连接指定AP热点，并开启DHCP功能。

   ```
   1. AT+STARTSTA                             - 启动STA模式
   2. AT+SCAN                                 - 扫描周边AP
   3. AT+SCANRESULT                           - 显示扫描结果
   4. AT+CONN="SSID",,2,"PASSWORD"            - 连接指定AP，其中SSID/PASSWORD为待连接的热点名称和密码
   5. AT+STASTAT                              - 查看连接结果
   6. AT+DHCP=wlan0,1                         - 通过DHCP向AP请求wlan0的IP地址
   ```

   

2. 查看WLAN模组与网关联通是否正常，如下图所示。

```
1. AT+IFCFG                                - 查看模组接口IP
2. AT+PING=X.X.X.X                         - 检查模组与网关的联通性，其中X.X.X.X需替换为实际的网关地址
```



# VScode串口使用中提示wsl无法使用的问题：

解决方法

https://blog.csdn.net/jesse_pan/article/details/88200477?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param