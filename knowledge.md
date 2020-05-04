## cookie 
+ Cookie，有时也用其复数形式 Cookies。类型为“小型文本文件”，是某些网站为了辨别用户身份，进行Session跟踪而储存在用户本地终端上的数据（通常经过加密），由用户客户端计算机暂时或永久保存的信息

## 反爬虫机制
1. 服务器被视为爬虫而拒绝访问,服务器通过校验请求的 U-A 来识别爬虫
    + 浏览器向服务器发送请求时有请求头 -- User-Agent，用来表示浏览器的类型，用requests 发送请求时，默认的是 python-request/(python 版本号)
    + 查询 chrome User-Agent 的方法：在 console 输入 javascript:alert(navigator.userAgent)
    + 接着将 requests.get 中的 headers 参数改为 {'User-Agent':---}