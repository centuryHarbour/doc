# REST Client 插件说明

> 类似于 `Postman` ， `REST Client` 支持 [cURL](http://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/CURL) 和 [RFC 2616](http://link.zhihu.com/?target=https%3A//www.w3.org/Protocols/rfc2616/rfc2616-sec5.html) 两种标准来调用 `REST API`

<br>

### **RFC 2616**

下面就是一个符合 `RFC 2616` 标准的 `POST` 请求

```http
POST http://dummy.restapiexample.com/api/v1/create HTTP/1.1
content-type: application/json

{
    "name":"Hendry",
    "salary":"61888",
    "age":"26"
}
```

*<font color=#fa8c16 size=3>Use:&nbsp;&nbsp;</font>* 在 `VS Code` 新建一个以 `.http` 或 `.rest` 结尾的文件，填写 `HTTP` 请求，点击 `Send Request` ， 或者是右键选择 `Send Request`， 或者使用快捷键 `Ctrl + Alt + R`

<br>

### **cURL**

下面就是一个符合 `cURL` 标准的 `POST` 请求

```http
curl -X POST "http://dummy.restapiexample.com/api/v1/create" -d "Hello World"
```

*<font color=#fa8c16 size=3>Use:&nbsp;&nbsp;</font>* 同上


## 主要使用功能点：

* ### **代码生成**

> 可以通过右键的 `Generate Code Snippet`命令把 `HTTP`请求生成不同编程语言的代码：`JavaScript` ， `Python` ， `C` ， `C#` ， `Java` ， `PHP`， `GO` ， `Ruby` ， `Swift` 等主流语言

* ### **高阶功能**

  * `Authentication` ： `REST Client` 支持了 `Basic Auth` ，`SSL Client Certificates` ， `Azure Active Directory` 等多种验证机制

  * `Cookies` 的支持
  
  * 支持 `HTTP 3xx` 的重定向

  * 变量的支持：环境变量，文件变量，预定义的系统变量等等

以下是使用变量的示例：

```http
@hostname = api.example.com
@port = 8080
@host = {{hostname}}:{{port}}
@contentType = application/json
@createdAt = {{$datetime iso8601}}

###

@name = hello
GET https://{{host}}/authors/{{name}} HTTP/1.1

###

PATCH https://{{host}}/authors/{{name}} HTTP/1.1
Content-Type: {{contentType}}

{
    "content": "foo bar",
    "created_at": {{createdAt}}
}
```
