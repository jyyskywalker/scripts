## 一、python 数据类型
+ 不可变数据： number string tuple
+ 可变数据： List Dictionary Set
 
1. List
    ```python
    list=['a',1,'b']
    [] 来索引
    是列表连接运算符，* 是重复操作
    ```
   + 内置方法
        - 查找方法：in, not in, count, index 


2. Tuple
   ```python
   tuple=('abcd', 789, 2.23, 'runoob' )
   [] 来索引
   tup1=() # 空元组
   tup2=(20,) # 一个元素，需要在元素后添加逗号 
   用 + 来进行拼接
  

3. Set
   ```python
   用 {} 或者 set{} 进行创建
   空集合必须用 set{}，因为 {} 用于创建空字典
   ```
4. Dictionary
+ 无序的键 (key) : 值 (value) 的集合
+ key 必须用不可变类型， key 必须是唯一的


## 文件处理
+ open() 方法，第一个参数是文件名称，第二个参数代表以二进制写的格式打开
    ```python
    with open('favicon.ico','wb') as f:
        f.write(r.content)
---

## 常用函数
+ shift() 将 dataframe 数据下移，但同时 index 不变
+ 不用ix, 当使用行索引时，loc()根据 index，iloc() 根据行号
+ hstack(),column_stack()

## 二、 urllib 库
+ 三个模块：请求模块 urllib.request, 异常处理模块 urllib.error, url 解析模块 urllib.parse
+ 还有一个不常用的 robotparser，用于识别网站的 robots.txt文件，判断哪些网站可以爬，用的比较少
1. urllib.request
    + urlopen 
        - response = urllib.request.open; request.read().decode('utf-8')
        - read() 获取响应体内容，内容是 bytes 字节，要转化成字符串 
        - data 参数：post请求
        - timeout 参数：设置请求超时时间
        - 响应类型
        - print(type(response)) 
        - 响应的状态码、响应头
            ```python
            response.status
            response.getheaders
            response.getheader('Server')
            ```
    + Request
        - Request 类可以通过添加参数实现更多的功能    
    + Handler：更高级的操作（如 Cookies 处理、代理设置等），父类 BaseHandler
        - HTTPDefaultErrorHandler
        - HTTPRedirectHandler
        - HTTPCookieProcessor
        - ProxyHandler
        - HTTPPasswordMgr
        - HTTPBasicAuthHandler   
        - 使用代理：urllib.request.ProxyHandler()
2. 异常处理模块: urllib.error 
    + error.HTTPError  
    + error.URLError
3. url 解析模块： urllib.parse
    + （反）解析链接、（拆）连接链接、（反）序列化参数、（反）转URL编码
        - parse.urlencode 将字典对象转换成 get 请求的参数
        - add_header 方法添加请求头
        - parse.urlparse
        - parse.urlunparse
        - parse.urljoin
4. robotsparser 模块，实现网站 Robots 协议的分析
    + RobotFileParser 类，只需要传递给它链接
5. Cookie
    ```python
    import http.cookiejar
    ```
    + MozillaCookieJar(filename) 形式保存 cookie
    + LWPCookieJar(filename) 形式保存 cookie
    + 读取 cookie 请求，获取登录后的信息


## 三、requests 库
+ requests 库可以更加方便地实现 Cookies、登陆验证、代理设置等
### 解析 URL 中的参数
+ 在使用 get 请求时，利用 params 将参数以字典的形式写入，避免查询参数的拼写错误
+ 返回结果如果是 json 格式，调用 json 方法转化为字典
### 取出其中的内容
+ item() 方法可以将类对象转化为元组组成的列表
### 自定义 Headers
+ 伪装 headers 模拟浏览器
### 重定向与超时
### 代理
+ 为 requests 套上一层代理
### 会话对象
#### 会话维持：```Session``` 对象
### 身份认证：auth 参数
+ oAuth 认证

## 四、解析库
1. XPath
    + etree 模块
        - 构造 XPath 对象
    1.2 
2. Beautiful Soup
3. pyquery


## 五、正则表达式

## 六、codecs 库

## 七、json 库 
+ 字符串到对象和对象到字符串
```python
import json

json_obj = json.loads("{'key': 'value'}")  # 字符串到对象
json_str = json.dumps(json_obj)            # 对象到字符串
```