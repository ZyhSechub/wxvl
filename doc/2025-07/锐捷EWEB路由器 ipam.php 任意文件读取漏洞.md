#  锐捷EWEB路由器 ipam.php 任意文件读取漏洞  
Superhero  Nday Poc   2025-07-12 01:45  
  
![图片](https://mmbiz.qpic.cn/mmbiz_png/Melo944GVOJECe5vg2C5YWgpyo1D5bCkYN4sZibCVo6EFo0N9b7Kib4I4N6j6Y10tynLOdgov9ibUmaNwW5yeoCbQ/640?wx_fmt=other&from=appmsg&wxfrom=5&wx_lazy=1&wx_co=1&tp=webp "")  
  
![图片](https://mmbiz.qpic.cn/mmbiz_png/Melo944GVOJECe5vg2C5YWgpyo1D5bCkhic5lbbPcpxTLtLccZ04WhwDotW7g2b3zBgZeS5uvFH4dxf0tj0Rutw/640?wx_fmt=other&from=appmsg&wxfrom=5&wx_lazy=1&wx_co=1&tp=webp "")  
  
![图片](https://mmbiz.qpic.cn/mmbiz_png/Melo944GVOJECe5vg2C5YWgpyo1D5bCk524CiapZejYicic1Hf8LPt8qR893A3IP38J3NMmskDZjyqNkShewpibEfA/640?wx_fmt=other&from=appmsg&wxfrom=5&wx_lazy=1&wx_co=1&tp=webp "")  
  
内容仅用于学习交流自查使用，由于传播、利用本公众号所提供的  
POC  
信息及  
POC对应脚本  
而造成的任何直接或者间接的后果及损失，均由使用者本人负责，公众号Nday Poc及作者不为此承担任何责任，一旦造成后果请自行承担！  
  
  
**01**  
  
**漏洞概述**  
  
  
锐捷EWEB路由器 ipam.php 接口存在任意文件读取漏洞，未经身份验证攻击者可通过该漏洞读取系统重要文件（如数据库配置文件、系统配置文件）、数据库配置文件等等，导致网站处于极度不安全状态。  
  
**02******  
  
**搜索引擎**  
  
  
FOFA:  
```
title="锐捷网络-EWEB网管系统
```  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtvNbIJReh0QxfG9YufibgI2tXWKdPfP2aNcPvwNHiaT5MlK3mvQ2U7lvlw/640?wx_fmt=png&from=appmsg "")  
  
  
**03******  
  
**漏洞复现**  
  
1、获取可用cookie  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtvcJcBw7hBSrfwCbAuM1EI69KJiaokayXETibNcmWOUNwMxSfbNb21QUHg/640?wx_fmt=png&from=appmsg "")  
  
2、利用可用cookie读取文件  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtvREYXfZiaJZYnpwSibBEJmY0TOB91by1fGHt8Xxc1U9UW5KjjREcbYhNA/640?wx_fmt=png&from=appmsg "")  
  
  
**04**  
  
**自查工具**  
  
  
nuclei  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtvF4VlFAvLjpicw4ZD1Rqv8ExsTk72wyakFuopR7rbxYHGxFPAGq9nXOg/640?wx_fmt=png&from=appmsg "")  
  
afrog  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtvD5ibNYEqiaAlosxsNKCD3Q8GbSNjrOuia4ytbgta2QuDC4TY8nDqiapdzw/640?wx_fmt=png&from=appmsg "")  
  
xray  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwKlKagmGiagojVJXLX5xumtv3d2fNUicCXpRpEicE9MWuduQzdujicTIZ3XiabZjAVy1lNUiaWIm54vaOag/640?wx_fmt=png&from=appmsg "")  
  
  
**05******  
  
**修复建议**  
  
  
1、关闭互联网暴露面或接口设置访问权限  
  
2、升级至安全版本  
  
  
**06******  
  
**内部圈子介绍**  
  
  
【Nday漏洞实战圈】🛠️   
  
专注公开1day/Nday漏洞复现  
 · 工具链适配支持  
  
 ✧━━━━━━━━━━━━━━━━✧   
  
🔍 资源内容  
  
 ▫️ 整合全网公开  
1day/Nday  
漏洞POC详情  
  
 ▫️ 适配Xray/Afrog/Nuclei检测脚本  
  
 ▫️ 支持内置与自定义POC目录混合扫描   
  
🔄 更新计划   
  
▫️ 每周新增7-10个实用POC（来源公开平台）   
  
▫️ 所有脚本经过基础测试，降低调试成本   
  
🎯 适用场景   
  
▫️ 企业漏洞自查 ▫️ 渗透测试 ▫️ 红蓝对抗   
▫️ 安全运维  
  
✧━━━━━━━━━━━━━━━━✧   
  
⚠️ 声明：仅限合法授权测试，严禁违规使用！  
  
![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/wnJTy44dqwL3ibS1g2m2lT43sfSu19lEhicMFmdMDQN5oc6MW7xnkAT0cYo3PoZdf8CicjIFw2eSwN20ogfBN8vog/640?wx_fmt=png&from=appmsg&watermark=1&wxfrom=5&wx_lazy=1&tp=webp "")  
  
  
