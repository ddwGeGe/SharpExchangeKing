# SharpExchangeKing
Exchange 服务器安全的辅助测试工具


## 0x00 前言
这是自编写了 SharpvCenterKing 之后的第三个 King 系列工具，命名为 SharpExchangeKing。

关于 Exchange 的利用手段技术也是非常多的，因此该工具搬挪了 SharpvCenterKing 的大部分布局。总的来说， King 系列工具都长得差不多。当前公开的版本仅仅是包含了两个功能

1. Exchange 服务器的基本信息收集，不包括端口。
2. 通过 EWS 接口进行密码爆破。

建议使用 Windows 10 系统运行 SharpExchangeKing。
## 0x01 功能介绍
### 1.1 基本信息收集
该模块共计收集了以下数据：

1. 通过 EWS 收集服务器机器名，所在 AD 域
2. 获取详细版本号
3. 尝试获取服务器内网 IP
4. 获取 SSL 证书信息
5. 根据版本号来判断是否存在漏洞

效果如下：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/22287830/1676642007959-898b8638-3d29-44aa-afd2-b27bfa3c5d47.png#averageHue=%23444341&clientId=uc2c0e25b-b1ba-4&from=paste&height=610&id=u3fab67f0&name=image.png&originHeight=610&originWidth=866&originalType=binary&ratio=1&rotation=0&showTitle=false&size=64384&status=done&style=none&taskId=ud4fbb82b-625c-49e0-9b9c-5818fcb94f3&title=&width=866)

### 1.2 密码爆破

使用线程池，最大默认 10。目前仅支持 EWS 接口的验证，且该接口支持 NLTM 验证。账号密码混杂组合支持 5 种模式：

- 单个账号单个密码：UserName 和 PassWord 分别填写账号密码即可。
- 单个账号多个密码：UserName 填写账号，PassWord 填写包含密码的本地文本路径。
- 多个账号单个密码：UserName 填写包含账号的本地文本路径，PassWord 填写密码。
- 多个账号多个密码：UserName 填写包含账号的本地文本路径，PassWord 填写包含密码的本地文本路径。
- 批量验证账号密码：UserName 填写包含账号密码的本地文本路径，格式必须为“账号:密码”。

PS：如果以上的**多个密码**是 NTLM 格式，则勾选 NTLM，不支持明文和 NTLM 同时使用。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/22287830/1675492521551-b5bfcf3b-a719-4223-be9a-53b6e953fdf9.png#averageHue=%23716f6e&clientId=u39e2b50c-3852-4&from=paste&height=592&id=u093dcc36&name=image.png&originHeight=592&originWidth=857&originalType=binary&ratio=1&rotation=0&showTitle=false&size=60909&status=done&style=none&taskId=u893ef663-fb08-44ef-b772-1c4e23b56e5&title=&width=857)


## 0x02 未公开的版本

- 邮箱用户名验证：采用 SMTP 和 HTTP 响应最开始时间两种方法。
- 邮件搜索：EWS 的 SOAP 操作。
- 邮件收取：EWS 的 SOAP 操作。
- 获取全局邮箱列表：EWS 的 SOAP 操作。
- 设置当前邮箱收信箱转发：EWS 的 SOAP 操作。
- 设置当前邮箱收信箱设置：EWS 的 SOAP 操作。


## 0x03 加入加入
加入加入！加入加入！解压密码：RowTeam
### 3.1 加入知识星球

![RowTeam.png](https://cdn.nlark.com/yuque/0/2023/png/22287830/1676642752168-40e91f41-9bdb-462f-bfa1-a774663179b3.png#averageHue=%23eeeed0&clientId=ue0a4f1d3-95f3-4&from=paste&height=412&id=Ej6eo&name=RowTeam.png&originHeight=412&originWidth=750&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27878&status=done&style=none&taskId=u328a741f-81ea-41bc-99ca-f8a8c8d7db8&title=&width=750) 
### 3.1 关注公众号
![qrcode.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/22287830/1676642752166-eae094e9-1c26-4800-94e1-f2969312d9ed.jpeg#averageHue=%239c9c9c&clientId=ue0a4f1d3-95f3-4&from=paste&height=258&id=AaPhh&name=qrcode.jpg&originHeight=258&originWidth=258&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26910&status=done&style=none&taskId=ub11cc5ca-9f6c-47de-bee4-41de7ae933f&title=&width=258)


## 0x04 免责声明
本工具仅面向合法授权的企业安全建设行为，例如企业内部攻防演练、漏洞验证和复测，如您需要测试本工具的可用性，请自行搭建靶机环境。

在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。请勿对非授权目标使用。

如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。
