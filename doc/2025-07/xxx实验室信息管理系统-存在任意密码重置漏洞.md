#  xxx实验室信息管理系统-存在任意密码重置漏洞  
原创 z00000  安全光圈   2025-07-20 16:01  
  
# xxx实验室信息管理系统-存在任意密码重置漏洞  
  
同样是比较早的时候接的项目，对目标做渗透测试出报告，时间比较久远了，所以图片比较单调，同期出的几个报告里掏出来点相对能看的，家人们将就看看~  
  
![](https://mmbiz.qpic.cn/mmbiz_jpg/g1X9cMsc6D3jFHAAaJwrESXYCgMpicDm6abvgyeSq3l9IsBabu7YbNRfibEI9uPYrqNqJ0uuh1ngPwiblic6JBHnrQ/640?wx_fmt=jpeg "")  
  
安全起见，文章  
厚厚厚厚厚厚厚厚厚  
厚厚厚厚厚厚厚厚厚  
厚厚厚厚厚厚厚厚厚  
厚厚厚厚厚厚厚厚厚  
厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚厚  
码，仅分享挖掘经历和思路，观看不便之处敬请见谅~  
  
![](https://mmbiz.qpic.cn/mmbiz_jpg/g1X9cMsc6D0y6TcnAdIjsw79IXh18wBJlvC5q0MjR1lL8QoS3JLOuyUvh0sxTjSf4fwdIgCHWYD7CQcg7wU3hw/640?wx_fmt=jpeg "")  
## 找到接口  
  
信息收集过程省略(也就是老几样的搜索方式，查资产，查子资产，找存活ip、端口，判断服务打web~)。  
  
访问目标url，Ctrl+U  
 查看网页源码，翻找网页源码得到重置密码接口的链接。  
  
哟~ 很经典的可测点嘛 那不得狠狠地尝试一下！  
  
https:/xxxx:7111/xxxx/ref/toModifyPwdNew.action  
  
![](https://mmbiz.qpic.cn/mmbiz_png/g1X9cMsc6D3jFHAAaJwrESXYCgMpicDm6H15kY6G3LBHXKHbiaGNvHaMfK11bQ9M3d8BBUKzjib2V1QDt1YysDfPg/640?wx_fmt=png&from=appmsg "null")  
(ps:看到.action已经盲测过了，没有测出来s2的洞)  
## 密码重置  
  
考虑到业务正常运行问题，当时重置的是test用户  
  
直接修改返回包为 success，然后前端响应成功。不清楚后端的鉴权逻辑具体是怎么写的，没有任何条件就可以重置密码了……还蛮抽象的  
  
![](https://mmbiz.qpic.cn/mmbiz_png/g1X9cMsc6D3jFHAAaJwrESXYCgMpicDm6ovBqjV7Ku9yvI81ZfaOvDrsg3zvxlyhfQ8eicibqwK6Oew5wGOIqZicuA/640?wx_fmt=png&from=appmsg "null")  
  
## 登录后台  
  
重置的账号密码为test/1234a@A666  
  
直接回到前台进行登录，登录成功！到这就可以确定漏洞点存在了，截图写报告~  
  
功能点比较少，也没能泄露更多的接口来测试，估计是test用户的角色问题，只好作罢去找下一个点~  
  
![](https://mmbiz.qpic.cn/mmbiz_png/g1X9cMsc6D3jFHAAaJwrESXYCgMpicDm60PTYBG8cACLIK32eZ4uMYkL7ClicicmsXXRmS2m2iadj8qFJnUw5KvbTw/640?wx_fmt=png&from=appmsg "null")  
  
![](https://mmbiz.qpic.cn/mmbiz_gif/g1X9cMsc6D1TAfwxLibAwZwoPcYAtBr6W7b17RibrfFDE6B70OOLYDaJgHsYmNgxx9k6dnJHIvzzz4Zb2hFibEKGg/640?wx_fmt=gif "")  
  
  
