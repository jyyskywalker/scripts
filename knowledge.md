## cookie 
+ Cookie，有时也用其复数形式 Cookies。类型为“小型文本文件”，是某些网站为了辨别用户身份，进行Session跟踪而储存在用户本地终端上的数据（通常经过加密），由用户客户端计算机暂时或永久保存的信息

## 反爬虫机制
1. 服务器被视为爬虫而拒绝访问,服务器通过校验请求的 U-A 来识别爬虫
    + 浏览器向服务器发送请求时有请求头 -- User-Agent，用来表示浏览器的类型，用requests 发送请求时，默认的是 python-request/(python 版本号)
    + 查询 chrome User-Agent 的方法：在 console 输入 javascript:alert(navigator.userAgent)
    + 接着将 requests.get 中的 headers 参数改为 {'User-Agent':---}

## 模拟发出请求

## 您的连接不是私密连接
+ 网站的证书不被 CA 机构信任，要爬取这样的站点，要设置忽略证书的选项，否则会提示 SSL 链接错误

## 编码
### Unicode 和其他编码的关系
+ Unicode将所有字符容纳进来，并且给与独一无二的编码，但是Unicode只是符号集，只规定了符号的二进制代码，没规定这个代码如何存储
### decode 和 encode
+ decode 是将其他编码转换为 python 内的 Unicode 
+ encode 是将 Unicode 编码为其他的编码
+ 如果一个字符串已经是unicode了，再进行解码则将出错，因此通常要对其编码方式是否为unicode进行判断：
```python
isinstance(s,unicode)#用来判断是否为unicode
```
+ 用非unicode编码形式的str来encode会报错

## Jupyter notebook 美化
+ 主题命令：jt -t grade3 -f firacode -fs 105 -nf opensans -nfs 95 -tf georgiaserif -tfs 115 -cellw 90% -lineh 120 -T
+ toolbar 覆盖了 table of contents