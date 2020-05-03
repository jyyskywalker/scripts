## 一、python 数据类型
+ 不可变数据： number string tuple
+ 可变数据： List Dictionary Set
 
1. List
    ```python
    list=['a',1,'b']
    [] 来索引
    是列表连接运算符，* 是重复操作
    ```
   - 内置方法


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

---


## 二、requests 库
### 解析 URL 中的参数
+ 在使用 get 请求时，利用 params 将参数以字典的形式写入，避免查询参数的拼写错误

### 取出其中的内容

### 自定义 Headers
+ 伪装 headers 模拟浏览器
### 重定向与超时
### 代理
+ 为 requests 套上一层代理
### 会话对象

## 三、 urllib 库
三个模块：请求模块 urllib.request, 异常处理模块 urllib.error, url 解析模块 urllib.parse
1. urllib.request
    + urlopen 
        - response = urllib.request.open; request.read().decode('utf-8')
        - read() 获取响应体内容，内容是 bytes 字节，要转化成字符串 
    + data 参数：post请求
    + timeout 参数：设置请求超时时间
    + 响应类型
        - print(type(response)) 
    + 响应的状态码、响应头
        ```python
        response.status
        response.getheaders
        response.getheader('Server')   
    + 使用代理：urllib.request.ProxyHandler()
2. 异常处理模块: urllib.error 
    + error.HTTPError  
    + error.URLError
3. url 解析模块： urllib.parse
    + parse.urlencode 将字典对象转换成 get 请求的参数
    + add_header 方法添加请求头
    + parse.urlparse
    + parse.urlunparse
    + parse.urljoin
4. Cookie
    ```python
    import http.cookiejar
    ```
    + MozillaCookieJar(filename) 形式保存 cookie
    + LWPCookieJar(filename) 形式保存 cookie
    + 读取 cookie 请求，获取登录后的信息