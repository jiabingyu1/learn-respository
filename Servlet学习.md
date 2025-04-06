# HTTP/HTTPS教程

## 一、简介

### 1.HTTP

HTTP 协议是 Hyper Text Transfer Protocol（超文本传输协议）的缩写，是用于从万维网（ WWW:World Wide Web ）服务器传输超文本到本地浏览器的传送协议。

​	HTTP 是一个基于 TCP/IP 通信协议来传递数据（HTML 文件、图片文件、查询结果等）。

​	HTTP 的 URL 是由 **http://** 起始与默认使用端口 **80**

### 2.HTTPS

HTTPS 协议是 HyperText Transfer Protocol Secure（超文本传输安全协议）的缩写，是一种通过计算机网络进行安全通信的传输协议。

​	**与HTTP协议的区别**：HTTP 本身是不安全的，因为传输的数据未经加密，可能会被窃听或篡改，为了解决这个问题，引入了 HTTPS，即在 HTTP 上加入 SSL/TLS 协议，为数据传输提供了加密和身份验证。

​	HTTPS 经由 HTTP 进行通信，但利用 SSL/TLS 来加密数据包，HTTPS 开发的主要目的，是提供对网站服务器的身份认证，**保护交换资料的隐私与完整性**。

​	HTTPS 的 URL 则是由 **https://** 起始与默认使用端口**443**

## 二、工作原理

### 1.HTTP

![image-20250208211219351](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208211219351.png)

![image-20250208211254884](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208211254884.png)

### 2.HTTPS

![image-20250208211437590](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208211437590.png)

## 三、两种协议的区别

![image-20250209013541358](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209013541358.png)

- **加密**：
  - **HTTP**：数据传输过程中不加密，容易被截获和篡改。
  - **HTTPS**：使用SSL/TLS协议对传输的数据进行加密，保护数据传输过程中的安全性。
- **端口**：
  - **HTTP**：默认使用端口80。
  - **HTTPS**：默认使用端口443。
- **安全性**：
  - **HTTP**：不提供数据加密，安全性较低。
  - **HTTPS**：提供数据加密和完整性校验，安全性较高。
- **证书**：
  - **HTTP**：不需要证书。
  - **HTTPS**：需要SSL证书来启用加密，并验证服务器的身份。
- **性能**：
  - **HTTP**：由于不加密数据，性能略高于HTTPS。
  - **HTTPS**：由于需要进行加密和解密，可能会有一定的性能开销。
- **搜索引擎优化(SEO)**：
  - **HTTP**：搜索引擎可能会对没有使用HTTPS的网站进行降权。
  - **HTTPS**：搜索引擎倾向于优先索引和展示使用HTTPS的网站。
- **浏览器显示**：
  - **HTTP**：在大多数现代浏览器中，HTTP网站通常显示为"不安全"。
  - **HTTPS**：浏览器会显示一个锁形图标，表示网站是安全的。
- **成本**：
  - **HTTP**：通常免费。
  - **HTTPS**：需要购买SSL证书，可能会有一定的成本。
- **应用场景**：
  - **HTTP**：适用于不需要传输敏感信息的网站，如新闻网站、博客等。
  - **HTTPS**：适用于需要传输敏感信息的网站，如网上银行、在线购物、电子邮件等。

## 四、HTTP消息结构

HTTP消息分为两种类型：请求消息和响应消息。

​	一个 HTTP 客户端是一个应用程序（Web 浏览器或其他任何客户端），通过连接到服务器达到向服务器发送一个或多个 HTTP 的请求的目的。

​	一个 HTTP 服务器 同样也是一个应用程序（通常是一个 Web 服务，如 Nginx、Apache 服务器或 IIS 服务器等），通过接收客户端的请求并向客户端发送 HTTP 响应数据。

![image-20250209013815320](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209013815320.png)

### 1.客户端请求消息

​	客户端发送一个HTTP请求到服务器的请求消息包括以下格式：请求行（request line）、请求头部（header）、空行和请求数据四个部分组成，下图给出了请求报文的一般格式。

![image-20250209013853807](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209013853807.png)

- **请求行**（Request Line）：

  - **方法**：如 GET、POST、PUT、DELETE等，指定要执行的操作。
  - **请求 URI**（统一资源标识符）：请求的资源路径，通常包括主机名、端口号（如果非默认）、路径和查询字符串。
  - **HTTP 版本**：如 HTTP/1.1 或 HTTP/2。

  请求行的格式示例：`GET /index.html HTTP/1.1`

- **请求头**（Request Headers）：

  - 包含了客户端环境信息、请求体的大小（如果有）、客户端支持的压缩类型等。
  - 常见的请求头包括`Host`、`User-Agent`、`Accept`、`Accept-Encoding`、`Content-Length`等。

- **空行**：

  - 请求头和请求体之间的分隔符，表示请求头的结束。

- **请求体**（可选）：

  - 在某些类型的HTTP请求（如 POST 和 PUT）中，请求体包含要发送给服务器的数据。

### 2.服务器响应消息

HTTP 响应也由四个部分组成，分别是：状态行、消息报头、空行和响应正文。

![image-20250209014012059](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209014012059.png)

- **状态行**（Status Line）：

  - **HTTP 版本**：与请求消息中的版本相匹配。
  - **状态码**：三位数，表示请求的处理结果，如 200 表示成功，404 表示未找到资源。
  - **状态信息**：状态码的简短描述。

  状态行的格式示例：`HTTP/1.1 200 OK`

- **响应头**（Response Headers）：

  - 包含了服务器环境信息、响应体的大小、服务器支持的压缩类型等。
  - 常见的响应头包括`Content-Type`、`Content-Length`、`Server`、`Set-Cookie`等。

- **空行**：

  - 响应头和响应体之间的分隔符，表示响应头的结束。

- **响应体**（可选）：

  - 包含服务器返回的数据，如请求的网页内容、图片、JSON数据等。

### 3.实例

客户端请求：

```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:91.0) Gecko/20100101 Firefox/91.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Connection: keep-alive
```

服务端响应:

```
HTTP/1.1 200 OK
Date: Wed, 18 Apr 2024 12:00:00 GMT
Server: Apache/2.4.1 (Unix)
Last-Modified: Wed, 18 Apr 2024 11:00:00 GMT
Content-Length: 12345
Content-Type: text/html; charset=UTF-8

<!DOCTYPE html>
<html>
<head>
    <title>Example Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <!-- The rest of the HTML content -->
</body>
</html>
```

## 五、HTTP请求方法

| 序号 | 方法    | 描述                                                         |
| :--: | :------ | :----------------------------------------------------------- |
|  1   | GET     | 从服务器获取资源。用于请求数据而不对数据进行更改。例如，从服务器获取网页、图片等。 |
|  2   | POST    | 向服务器发送数据以创建新资源。常用于提交表单数据或上传文件。发送的数据包含在请求体中。 |
|  3   | PUT     | 向服务器发送数据以更新现有资源。如果资源不存在，则创建新的资源。与 POST 不同，PUT 通常是幂等的，即多次执行相同的 PUT 请求不会产生不同的结果。 |
|  4   | DELETE  | 从服务器删除指定的资源。请求中包含要删除的资源标识符。       |
|  5   | PATCH   | 对资源进行部分修改。与 PUT 类似，但 PATCH 只更改部分数据而不是替换整个资源。 |
|  6   | HEAD    | 类似于 GET，但服务器只返回响应的头部，不返回实际数据。用于检查资源的元数据（例如，检查资源是否存在，查看响应的头部信息）。 |
|  7   | OPTIONS | 返回服务器支持的 HTTP 方法。用于检查服务器支持哪些请求方法，通常用于跨域资源共享（CORS）的预检请求。 |
|  8   | TRACE   | 回显服务器收到的请求，主要用于诊断。客户端可以查看请求在服务器中的处理路径。 |
|  9   | CONNECT | 建立一个到服务器的隧道，通常用于 HTTPS 连接。客户端可以通过该隧道发送加密的数据。 |

## 六、HTTP状态码

下面是常见的 HTTP 状态码：

- **1xx（信息性状态码）**：表示接收的请求正在处理。
- **2xx（成功状态码）**：表示请求正常处理完毕。
- **3xx（重定向状态码）**：需要后续操作才能完成这一请求。
- **4xx（客户端错误状态码）**：表示请求包含语法错误或无法完成。
- **5xx（服务器错误状态码）**：服务器在处理请求的过程中发生了错误。

​	HTTP 状态码由三个十进制数字组成，第一个十进制数字定义了状态码的类型。响应分为五类：信息响应(100–199)，成功响应(200–299)，重定向(300–399)，客户端错误(400–499)和服务器错误 (500–599)：

| 分类 | 分类描述                                       |
| :--- | :--------------------------------------------- |
| 1**  | 信息，服务器收到请求，需要请求者继续执行操作   |
| 2**  | 成功，操作被成功接收并处理                     |
| 3**  | 重定向，需要进一步的操作以完成请求             |
| 4**  | 客户端错误，请求包含语法错误或无法完成请求     |
| 5**  | 服务器错误，服务器在处理请求的过程中发生了错误 |

## 七、MIME

​	MIME (Multipurpose Internet Mail Extensions) 是描述消息内容类型的标准，用来表示文档、文件或字节流的性质和格式。

​	MIME 消息能包含文本、图像、音频、视频以及其他应用程序专用的数据。

​	浏览器通常使用 MIME 类型（而不是文件扩展名）来确定如何处理URL，因此 Web服务器在响应头中添加正确的 MIME 类型非常重要。如果配置不正确，浏览器可能会无法解析文件内容，网站将无法正常工作，并且下载的文件也会被错误处理。

​	MIME 的组成结构非常简单，由类型与子类型两个字符串中间用 **/** 分隔而组成，不允许有空格。type 表示可以被分多个子类的独立类别，subtype 表示细分后的每个类型。

​	MIME类型对大小写不敏感，但是传统写法都是小写。

两种主要的 MIME 类型在默认类型中扮演了重要的角色：

- **text/plain** 表示文本文件的默认值。
- **application/octet-stream** 表示所有其他情况的默认值。



# Servlet教程

## 一、Servlet简介

1.Servlet是什么？

​	Java Servlet 是运行在 Web 服务器或应用服务器上的程序，它是作为来自 Web 浏览器或其他 HTTP 客户端的请求和 HTTP 服务器上的数据库或应用程序之间的中间层。**简单来说，Servlet就是客户端和服务端传递数据的中间层。**

2.Servlet架构

​	Servlet 在 Web 应用程序中的位置：

![image-20250209023443151](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209023443151.png)

3.Servlet作用

​	Servlet 执行以下主要任务：

- 读取客户端（浏览器）发送的显式的数据。这包括网页上的 HTML 表单，或者也可以是来自 applet 或自定义的 HTTP 客户端程序的表单。
- 读取客户端（浏览器）发送的隐式的 HTTP 请求数据。这包括 cookies、媒体类型和浏览器能理解的压缩格式等等。
- 处理数据并生成结果。这个过程可能需要访问数据库，执行 RMI 或 CORBA 调用，调用 Web 服务，或者直接计算得出对应的响应。
- 发送显式的数据（即文档）到客户端（浏览器）。该文档的格式可以是多种多样的，包括文本文件（HTML 或 XML）、二进制文件（GIF 图像）、Excel 等。
- 发送隐式的 HTTP 响应到客户端（浏览器）。这包括告诉浏览器或其他客户端被返回的文档类型（例如 HTML），设置 cookies 和缓存参数，以及其他类似的任务。

4.运行流程

![image-20250209031543219](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209031543219.png)

## 二、Servlet生命周期

Servlet 生命周期可被定义为从创建直到毁灭的整个过程。以下是 Servlet 遵循的过程：

- Servlet 初始化后调用 **init ()** 方法。
- Servlet 调用 **service()** 方法来处理客户端的请求。
- Servlet 销毁前调用 **destroy()** 方法。
- 最后，Servlet 是由 JVM 的垃圾回收器进行垃圾回收的。

### 1.init方法

init 方法的定义如下：

```
public void init() throws ServletException {
  // 初始化代码...
}
```

注意：

​	1.init 方法被设计成只调用一次。它在第一次创建 Servlet 时被调用，在后续每次用户请求时不再调用。因此常用于初始化。

​	2.Servlet 通常创建于用户第一次调用对应于该 Servlet 的 URL 时，但是也可以指定 Servlet 在服务器第一次启动时被加载。

​	3.当用户调用一个 Servlet 时，就会创建一个 Servlet 实例，每一个用户请求都会产生一个新的线程，适当的时候移交给 doGet 或 doPost 方法。init() 方法简单地创建或加载一些数据，这些数据将被用于 Servlet 的整个生命周期。

### 2.service方法

下面是该方法的特征：

```
public void service(ServletRequest request, 
                    ServletResponse response) 
      throws ServletException, IOException{
}
```

注意：

​	1.service() 方法是执行实际任务的主要方法。Servlet 容器（即 Web 服务器）调用 service() 方法来处理来自客户端（浏览器）的请求，并把格式化的响应写回给客户端。

​	2.每次服务器接收到一个 Servlet 请求时，服务器会产生一个新的线程并调用服务。service() 方法检查 HTTP 请求类型（GET、POST、PUT、DELETE 等），并在适当的时候调用 doGet、doPost、doPut，doDelete 等方法。**所以，不需要对 service() 方法做任何动作，只需要根据来自客户端的请求类型来重写 doGet() 或 doPost() 即可。**

​	3.可以近似看作Controller控制层

​	4.Servlet在Tomcat中是单例模式，成员变量在多个线程栈之中共享，因此不建议在service方法中修改成员变量，会引发线程安全问题。即：可以用但不能修改，要想修改需要加锁，但是锁会降低性能。

### 3.doGet方法

GET 请求来自于一个 URL 的正常请求，或者来自于一个未指定 METHOD 的 HTML 表单，它由 doGet() 方法处理。

```
public void doGet(HttpServletRequest request,
                  HttpServletResponse response)
    throws ServletException, IOException {
    // Servlet 代码
}
```

### 4.doPost方法

POST 请求来自于一个特别指定了 METHOD 为 POST 的 HTML 表单，它由 doPost() 方法处理。

```
public void doPost(HttpServletRequest request,
                   HttpServletResponse response)
    throws ServletException, IOException {
    // Servlet 代码
}
```

### 5.destroy方法

destroy 方法定义如下所示：

```
  public void destroy() {
    // 终止化代码...
  }
```

注意：

​	1.destroy() 方法只会被调用一次，在 Servlet 生命周期结束时被调用。

​	2.destroy() 方法可以让您的 Servlet 关闭数据库连接、停止后台线程、把 Cookie 列表或点击计数器写入到磁盘，并执行其他类似的清理活动。

​	3.在调用 destroy() 方法之后，servlet 对象被标记为垃圾回收。

### 6.总结

1.实例化	构造器	第一次请求

2.初始化	init方法	构造完毕

3.接收请求、处理请求	service方法	每次请求

4.销毁	destroy方法	关闭服务

## 三、Servlet开发流程

### 1.目标

校验注册时用户名是否被占用。通过客户端向一个 Servlet 发送请求，携带 username，如果用户名是 atguigu，则向客户端响应 NO，如果是其他，则响应 YES

### 2.开发过程

步骤1：开发一个web类型的module

![image-20250209041540703](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209041540703.png)

步骤2：开发一个UserServlet

![image-20250209041612808](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209041612808.png)

步骤3：在xml文件中配置客户端和服务端的servlet类的映射

![image-20250209041707153](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209041707153.png)

步骤4：部署Tomcat

​	先在当前项目中，导入Tomcat相关依赖包

![image-20250209041732084](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209041732084.png)

​	再配置Tomcat，在Application context中设置访问页面demo

![image-20250209041903797](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209041903797.png)

​	最后设置访问页面demo的快捷方式

![image-20250209042010355](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209042010355.png)

​	实现页面：

![image-20250209042029453](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209042029453.png)![image-20250209042040367](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209042040367.png)

​	改进：动态响应资源的时候HTTP返回报文的响应头中没有content-type，因此我们需要自己定义一个content-type进行响应，目的是让浏览器清楚的知道响应体的格式。

![image-20250209171911851](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209171911851.png)

### 3.XML标签

#### 3.1 url-pattern

1.工作流程

![image-20250209172736870](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209172736870.png)

​	注意：一个servlet-name可以对应多个servlet-pattern；一个servlet标签可以同时对应多个servlet-mapping标签。

2.写法格式

​	a.精确匹配：/servlet1

​	b.模糊匹配

​		使用 * 作为通配符，符号在哪里，哪里就是模糊的

​		/：匹配全部，但是不包含jsp文件

​		/*：匹配全部，包含jsp文件

​		/a/*：匹配前缀，后缀模糊

​		*.action：匹配后缀，前缀模糊

#### 3.2 load-on-startup

`<load-on-startup> -1 </load-on-startup>`

默认值是-1，表示tomcat启动时不会实例化该servlet（在真正请求时才会实例化，见 二、6 总结）

其他正整数的含义是：tomcat在启动时就实例化该servlet，正整数代表执行顺序，越小的数优先级越高。如果正整数冲突了，tomcat会自动协调启动顺序。

### 4.Servlet注解

@WebServlet

例：

​	配置xml文件

![image-20250209201437213](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201437213.png)

​	编写Servlet1.java

![image-20250209201507907](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201507907.png)

​	输出：

![image-20250209201521769](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201521769.png)

改进：

​	删除配置代码

![image-20250209201544892](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201544892.png)

​	使用注解

![image-20250209201634502](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201634502.png)

​	输出：

![image-20250209201648714](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250209201648714.png)

## 四、Servlet创建方式

### 1.实现Servlet接口

```
//Servlet的生命周期:从Servlet被创建到Servlet被销毁的过程
//一次创建，到处服务
//一个Servlet只会有一个对象，服务所有的请求
/*
 * 1.实例化（使用构造方法创建对象）
 * 2.初始化  执行init方法
 * 3.服务     执行service方法
 * 4.销毁    执行destroy方法
 */
public class ServletDemo1 implements Servlet {

    //public ServletDemo1(){}

     //生命周期方法:当Servlet第一次被创建对象时执行该方法,该方法在整个生命周期中只执行一次
    public void init(ServletConfig arg0) throws ServletException {
                System.out.println("=======init=========");
        }

    //生命周期方法:对客户端响应的方法,该方法会被执行多次，每次请求该servlet都会执行该方法
    public void service(ServletRequest arg0, ServletResponse arg1)
            throws ServletException, IOException {
        System.out.println("hehe");

    }

    //生命周期方法:当Servlet被销毁时执行该方法
    public void destroy() {
        System.out.println("******destroy**********");
    }
//当停止tomcat时也就销毁的servlet。
    public ServletConfig getServletConfig() {

        return null;
    }

    public String getServletInfo() {

        return null;
    }
}
```

### 2.继承 GenericServlet 类

它实现了 Servlet 接口除了 service 的方法，不过这种方法极少使用。

```
public class ServletDemo2 extends GenericServlet {

    @Override
    public void service(ServletRequest arg0, ServletResponse arg1)
            throws ServletException, IOException {
        System.out.println("heihei");

    }
}
```

### 3.继承 HttpServlet 方法

```
public class ServletDemo3 extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp)
            throws ServletException, IOException {
        System.out.println("haha");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp)
            throws ServletException, IOException {
        System.out.println("ee");
        doGet(req,resp);
    }

}
```

注意：推荐重写doGet和doPost方法处理前端的业务请求，重写service方法可能会使父类HttpServlet中的service方法失效。

## 五、ServletConfig和ServletContext

### 1.ServletConfig

​	在xml中可以编写一些初始化数据，这些数据随着servlet的创建会放入ServletConfig对象中，使用getServletConfig方法、getInitParameter方法即可拿到这些数据。

方法：

​	1.getServletConfig()：获取xml文件的初始配置信息 config

​	2.getInitParameter()：config对象所包含的方法，作用是根据key获取value

​	3.getInitParameterNames()：config对象所包含的方法，返回一个迭代器对象，作用是获取所有的key

​	4.hasMoreElements()：该迭代器对象所包含的方法，检查是否有下一个

​	5.nextElement()：该迭代器对象所包含的方法，获取下一个并修改迭代器指针为当前的下一个

![image-20250210022134458](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210022134458.png)

例：

​	xml文件：init-param标签中即为初始化时要携带的数据，用键值对的形式表示。

![image-20250210023117107](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210023117107.png)

​	servlet文件：

![image-20250210024302913](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210024302913.png)

```
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取初始配置信息
        ServletConfig config = this.getServletConfig();
        //根据key获取value
        String valueA = config.getInitParameter("keyA");
        System.out.println(valueA);

        //获取所有的初始参数的名字,返回类型实际上是一个迭代器
        Enumeration<String> names = config.getInitParameterNames();
        while (names.hasMoreElements()) {
            String element = names.nextElement();
            System.out.println(element);
        }
    }
}
```

​	输出：

![image-20250210024325337](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210024325337.png)

改进：通过@WebServlet注解中的InitParams属性即可赋值，不再需要编写xml文件

![image-20250210024805923](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210024805923.png)

### 2.ServletContext

​	ServletContext也是为提供初始化的参数而存在的，但与ServletConfig不同的是，二者的作用域不同。ServletConfig只能一个类使用（参数在servlet标签中），而ServletContext可以所有类都能使用。

方法：

​	1.getServletContext()：获取xml文件的初始全局配置信息context

​	2.getRealPath()：获得一个指向项目部署位置下的某个文件/目录的磁盘真实路径的API，即打包后的module路径，参数表示该模块下的某个文件

​	3.getContextPath()：获取项目的上下文路径，即网址中除去localhost:8080的其余路径

​	其余方法与1中config方法相同

![image-20250210173352103](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210173352103.png)

例：

​	xml文件：context-param标签中即为初始化时要携带的数据，用键值对的形式表示。

![image-20250210173526323](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210173526323.png)

​	servlet文件：

![image-20250210194027927](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210194027927.png)

```
public class Servlet2 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext context = this.getServletContext();
        System.out.println("===== getInitParameter =====");
        String encoding = context.getInitParameter("encoding");
        String username = context.getInitParameter("username");
        System.out.println(encoding+"  "+username);
        System.out.println("===== getInitParameterNames =====");
        Enumeration<String> names = context.getInitParameterNames();
        while (names.hasMoreElements()) {
            String s = names.nextElement();
            System.out.println(s);
        }
    }
```

​	输出：

![image-20250210194059341](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210194059341.png)

### 3.域对象

1.定义：一些用于存储数据和传递数据的对象，传递数据不同的范围，我们称之为不同的域，不同的域对象代表不同的域，共享数据的范围也不同。

2.分类：webapp中的三大域对象，分别是应用域、会话域、请求域

3.三大域对象共同API：

![image-20250210203737806](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210203737806.png)

#### 3.1 应用域

​	ServletContext代表应用，所以ServletContext域也叫做应用域，是webapp中最大的域，可以在本应用内实现数据的共享和传递。

例：

​	在servlet1中使用servletContext1.setAttribute()方法向域对象中传递一个key和value

```
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取ServletContext对象
        ServletContext servletContext1 = this.getServletContext();
        //向应用域中设置数据
        servletContext1.setAttribute("Servlet1-key","servlet1-value");
    }
```

​	在servlet2中使用servletContext2.getAttribute()方法从域对象中根据key读取value

```
protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext servletContext2 = this.getServletContext();
        Object attribute = context.getAttribute("Servlet1-key");
        System.out.println(attribute);
    }
```

## 六、HttpServletRequest

1.简介

​	a.HttpServletRequest是一个接口，其父接口是ServletRequest

​	b.HttpServletRequest是Tomcat将请求报文转换封装而来的对象，在Tomcat调用service方法时传入

​	c.HttpServletRequest代表客户端发送过来的请求，所有请求中的信息都可以通过该对象获得

2.URI和URL区别与联系

![image-20250210222850337](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210222850337.png)

3.常见API

请求行相关：

​	String getMethod()：获取请求方式

​	String getScheme()：获取请求协议

​	String getProtocol()：获取请求协议及版本号

​	String getRequestURI()：获取客户端请求项目中的具体资源

​	StringBuffer getRequestURL()：获取客户端请求的url

​	int getServerPort()：获取客户端发送请求时使用的端口号

​	int getLocalPort()：获取本应用在所在容器的端口号

​	int getRemotePort()：获取客户端程序的端口号

​	![image-20250210222653027](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210222653027.png)

​	![image-20250210222706116](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250210222706116.png)

请求头相关：

​	String getHeader(String key)：获取请求头中的key对应的value

​	Enumeration**<**String**>** getHeader()：获取请求头中所有的key，返回一个迭代器

​	String getContentType()：获取请求头中ContentType的数据

请求参数相关：

​	String getParameter(String parameterName)：根据请求参数名获取请求单个参数值

​	String[] getParameterValues(String parameterName)：根据请求参数名获取请求多个参数值数组

​	Enumeration**<**String**>** getParameterNames()：获取所有请求参数名

​	Map<String,String[]> getParameterMap()：获取所有请求参数的键值对集合

​	BufferedReader getReader() throws IOException：获取读取请求体的字符输入流

​	ServletInputStream getInputStream() throws IOException：获取读取请求体的字节输入流

​	int getContentLength()：获取请求体长度的字节数

例：

get方式（键值对形式数据）：

​	html文件：

![image-20250212035715622](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212035715622.png)

![image-20250212042113994](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212042113994.png)

​		输出：

![image-20250212042130116](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212042130116.png)

​	servlet文件：

![image-20250212042018767](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212042018767.png)

```java
@Override
protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
    //获取 key-value形式的参数
    //根据参数名获取单个参数值
    System.out.println("===============");
    String username = req.getParameter("username");
    System.out.println("username:"+username);
    String userPwd = req.getParameter("userPwd");
    System.out.println("userPwd:"+userPwd);
    //根据参数名获取多个参数值
    System.out.println("===============");
    String[] hobbies = req.getParameterValues("hobby");
    System.out.println(Arrays.toString(hobbies));

    //获取所有的参数名
    System.out.println("===============");
    Enumeration<String> names = req.getParameterNames();
    while (names.hasMoreElements()) {
        String keyName = names.nextElement();
        //由于不知道key对应的value的个数，因此用数组接收
        String[] values = req.getParameterValues(keyName);
        if (values.length > 1) {
            System.out.println("values:"+Arrays.toString(values));
        }
        else System.out.println("value:"+values[0]);
    }

    //返回所有参数的map集合 key = 参数名；value = 参数值
    System.out.println("===============");
    Map<String, String[]> map = req.getParameterMap();
    Set<Map.Entry<String, String[]>> entries = map.entrySet();
    for (Map.Entry<String, String[]> entry : entries) {
        System.out.println("key:"+entry.getKey());
        String[] values = entry.getValue();
        if (values.length > 1) {
            System.out.println("values:"+Arrays.toString(values));
        }
        else System.out.println("value:"+values[0]);
    }
}
```

​		输出：

![image-20250212042055317](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212042055317.png)

post方式（键值对形式数据）：

​	将html的form表单method方法改为post，其余HTML代码和servlet代码保持不变

![image-20250212192056212](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212192056212.png)

获得请求体中的非键值对数据（JSON串、文件等）

```java
@Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取非键值对形式参数
        BufferedReader reader = req.getReader();
        //获取一个从请求中读取二进制数据的字节输入流
        ServletInputStream is = req.getInputStream();
}
```

其他API：

​	String getServletPath()：获取请求的servlet的映射路径

​	ServletContext getServletContext()：获取ServletContext对象

​	Cookie[] getCookies()：获取请求的所有cookie

​	HttpSession getSession()：获取session对象

​	void setCharacterEncoding(String encoding)：设置请求体字符集

## 七、HttpServletResponse

1.简介

​	a.HttpServletResponse是一个接口，其父接口是ServletResponse

​	b.HttpServletResponse是Tomcat预先创建的，在Tomcat调用service方法传入

​	c.HttpServletResponse代表对客户端的响应，该对象会被转换成响应的报文发送给客户端，通过该对象我们可以设置相应信息

2.常见API

响应行相关：

​	void setStatus(int code)：设置响应状态码

响应头相关：

​	void setHeader(String headerName, String headerValue)：设置/修改响应头键值对

​	void setContentType(String contentType)：设置content-type及响应字符集（设置MIME类型）

响应体相关：

​	PrintWriter getWriter() throws IOException：获得向响应体放入信息的字符输出流

​	ServletOutputStream getOutputStream() throws IOException：获得向响应体放入信息的字节输出流

​	void setContentLength(int length)：设置响应体的字节长度，其实就是在设置content-length响应头

​	例：

```java
@Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        String info = "<h1>Hello</h1>";
        // 设置状态码
        resp.setStatus(200);
        // 在响应头中加入key-value
        resp.setHeader("keya", "valuea");
        // 设置content-type
        resp.setContentType("text/html");
        // 设置content-length（响应体的数据长度）
        resp.setContentLength(info.getBytes().length);

        //设置响应体内容
        //获得一个字符输出流
        PrintWriter writer = resp.getWriter();
        writer.write(info);
        //获得一个字节输出流
        ServletOutputStream os = resp.getOutputStream();
    }
```

​	展示：

![image-20250212232945545](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212232945545.png)

![image-20250212233021118](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212233021118.png)

其他API：

​	void sendError(int code, String message) throws IOException：向客户端响应错误信息的方法，需要指定响应码和响应信息

​	void addCookie(Cookie cookie)：向响应体中增加cookie

​	void setCharacterEncoding(String encoding)：设置响应体字符集

3.MIME类型

​	a.可以理解为文档类型，用户表示传递的数据是属于什么类型的文档

​	b.浏览器可以根据MIME类型决定用什么样的方式解析接收到的响应体消息

​	c.可以理解为：前后端数据交互时，告诉对方发给对方的是html/css/js/图片/视频/声音。。。

​	tomcat/conf/web.xml中配置了常见文件的拓展名和MIME类型的对应关系

## 八、请求转发和响应重定向

### 1.概述

1.请求转发和响应重定向是web应用中间接访问项目资源的两种手段，也是servlet控制页面跳转的两种手段

2.请求转发通过HttpServletRequest实现，响应重定向通过HttpServletResponse

3.请求转发生活举例：张三找李四借钱，李四没有，李四找王五借给张三

4.响应重定向生活举例：张三找李四借钱，李四没有，李四让张三自己再去找王五借钱

### 2.请求转发

![image-20250212234204673](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250212234204673.png)

注意：request和response对象全程只有一对

例：调用servletA，servletA可以转发到servletB，并输出B语句，通过debug方式检查是否跳转

servletA：

![image-20250213013344855](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250213013344855.png)

```java
@WebServlet("/servletA")
public class ServletA extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servletA run");
        //请求转发给ServletB
        //获得请求转发器
        RequestDispatcher requestDispatcher = req.getRequestDispatcher("servletB");//相对路径
        //让请求转发器做出转发动作
        requestDispatcher.forward(req,resp);
    }
}
```

servletB：

![image-20250213013435895](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250213013435895.png)

```java
@WebServlet("/servletB")
public class ServletB extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servletB run");
    }
}
```

输出：

![image-20250213013547666](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250213013547666.png)

请求转发特点：

​	a.请求转发是通过HttpServletRequest对象实现的

​	b.请求转发是服务器内部行为，对客户端是屏蔽的

​	c.客户端只产生了一次请求，服务端只产生了一对request和response对象

​	d.客户端的地址栏是不变的（仍指向servletA）

​	e.请求的参数是可以继续传递的

​	f.目标资源可以是servlet动态资源，也可以是html静态资源

​	g.目标资源可以是WEB-INF下的受保护的资源，该方式也是WEB-INF下资源的唯一访问方式

​	h.目标资源不能是web上的资源网址，即目标资源不可以是外部资源

### 3.响应重定向

![image-20250213015503901](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250213015503901.png)

响应重定向特点：

​	a.响应重定向通过HttpServletResponse对象的sendRedirect方法实现

​	b.响应重定向是服务端通过302响应码和路径，告诉客户端自己去找其他资源

​	c.客户端至少发送了两次请求，客户端地址栏是要变化的

​	d.服务端产生了多对请求和响应对象，且请求和响应对象不会传递给下一个资源

​	e.因为全程产生了多个HttpServletRequest对象，所以请求参数不可以传递，请求域中的数据也不可以传递

​	f.重定向可以是其他servlet动态资源，也可以是一些静态资源以实现页面跳转

​	g.重定向不可以定向到WEB-INF下受保护的资源

​	h.重定向可以定向到本项目以外的外部资源（区别请求转发）

例：

​	servlet1：请求servlet1后，响应头中状态码为302，且location指向servlet2

![image-20250214201520448](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214201520448.png)

![image-20250214201946077](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214201946077.png)

```java
@WebServlet("/servlet1")
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //接收用户请求
        System.out.println("servlet1执行了");
        //响应重定向     1.设置响应状态码为302  2.设置location响应头
        //使用sendRedirect方法即可完成以上两个步骤，不需要自己再设置
        resp.sendRedirect("servlet2");
    }
}
```

​	servlet2：servlet1放行后，浏览器会自动再发送一个指向servlet2的请求

![image-20250214201617910](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214201617910.png)

![image-20250214202106791](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214202106791.png)

```java
@WebServlet("/servlet2")
public class Servlet2 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servlet2执行了");
    }
}
```

​	输出：

![image-20250214201703364](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214201703364.png)

## 九、乱码问题

1.乱码问题的根本原因：数据的编码和解码使用的不是同一个字符集，或者使用了不支持某个语言文字的字符集

2.各个字符集的兼容性：

![image-20250214203130550](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250214203130550.png)

现在基本不存在乱码问题

## 十、路径问题

![image-20250215025841230](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250215025841230.png)

解决方式：不再设置上下文路径，只用一个 / 

![image-20250215030339474](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250215030339474.png)“

## 十一、会话管理

### 1.概述

1.为什么需要会话管理？

​	HTTP是无状态协议，无状态就是不保存状态，即无状态协议。HTTP协议自身不对请求和响应之间的通信状态进行保存，也就是说，在HTTP协议这个级别，协议对于发送过的请求或者响应都不做持久化处理。

​	简单理解：浏览器发送请求，服务器接收并响应，但是服务器不记录请求是否来自哪个浏览器，服务器没记录浏览器的特征，就是客户端的状态。

​	举例：张三去一家饭馆点了几道菜，觉得味道不错，第二天又去了，对老板说还点上次的几道菜

​		无状态：老板没有记录张三是否来过，更没有记录上次他点的什么菜，张三只能重新再点一遍

​		有状态：老板把每次来吃饭的用户都做好记录，查阅一下之前的记录，查到了张三之前的菜单，直接下单

2.会话管理实现的手段

​	Cookie和Session配合解决

​	cookie是在客户端保留少量数据的技术，主要通过响应头向客户端响应一些客户端要保留的信息

​	session是在服务端保留更多数据的技术，主要通过HttpSession对象保存一些和客户端相关的信息

​	cookie和session配合记录请求状态

​	举例：张三去银行办理业务

​		张三第一次去某个银行办业务，银行会为张三开户(Session)，并向张三发放一张银行卡(Cookie)

​		张三后面每次去银行，就可以携带之前的银行卡(Cookie)，银行根据银行卡找到之前张三开通的账户(Session)

![image-20250218175637372](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218175637372.png)

### 2.Cookie

#### 2.1 Cookie概述

cookie是一种客户端会话技术，cookie由服务端产生，他是服务器存放在浏览器的一小份数据，浏览器以后每次访问该服务器的时候都会将这一小份数据携带到服务器去。

a.服务端创建cookie，将cookie放入响应对象中，Tomcat容器将cookie转化为set-cookie响应头，相应给客户端

b.客户端在收到cookie的响应头时，在下次请求该服务的资源时，会以cookie请求头的形式携带之前收到的cookie

c.cookie是一种键值对格式的数据，从tomcat8.5开始可以保存中文，但是不推荐

d.由于cookie是存储于客户端的数据，比较容易暴露，一般不存储一些敏感或者影响安全的数据

例：

​	创建cookie传回浏览器，servletA：

![image-20250218185134073](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218185134073.png)

```java
@WebServlet("/servletA")
public class ServletA extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //创建cookie
        Cookie cookie1 = new Cookie("keyA","valueA");
        Cookie cookie2 = new Cookie("keyB","valueB");
        //将cookie放入response对象
        resp.addCookie(cookie1);
        resp.addCookie(cookie2);
    }
}
```

![image-20250218185113216](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218185113216.png)

​	接收浏览器发送的cookie，servletB：

![image-20250218190003632](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218190003632.png)

```
@WebServlet("/servletB")
public class ServletB extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取请求中携带的cookie
        Cookie[] cookies = req.getCookies();
        //请求中的多个cookie会进入该数组
        //如果没有cookie，数组为null,for循环时会爆出空指针异常
        //因此需要先判断
        if (cookies != null) {
            for (Cookie cookie : cookies) {
                System.out.println(cookie.getName() + " " + cookie.getValue());
            }
        }
    }
}
```

​	输出：

![image-20250218190024517](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218190024517.png)

​	另，当cookie数组为空时，如果没有if判断语句，则输出：

![image-20250218190723970](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218190723970.png)

#### 2.2 Cookie的时效性

默认情况下Cookie的有效期是一次会话范围内，我们可以通过cookie的setMaxAge()方法让Cookie持久化保存到浏览器上。

a.会话级cookie(默认)：

​	服务器端并没有明确指定Cookie的存在时间

​	在浏览器端，Cookie数据存在于内存中

​	只要浏览器还开着，Cookie数据就一直都在

​	浏览器关闭，内存中的Cookie数据就会被释放

b.持久化Cookie

​	服务器端明确设置了Cookie的存在时间

​	在浏览器端，Cookie数据会被保存到硬盘上

​	Cookie在硬盘上存在的世界根据服务器端限定的时间来管控，不受浏览器关闭的影响

​	持久化Cookie到达了预设的时间会被释放

​	方法：void setMaxAge(int expiry)：参数单位是秒，表示cookie的持久化时间，如果设置参数为0，表示将浏览器中保存的该cookie删除。

```java
@WebServlet("/servletA")
public class ServletA extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //创建cookie
        Cookie cookie1 = new Cookie("keyA","valueA");
        cookie1.setMaxAge(60*5);
        Cookie cookie2 = new Cookie("keyB","valueB");
        //将cookie放入response对象
        resp.addCookie(cookie1);
        resp.addCookie(cookie2);
    }
}
```

#### 2.3 Cookie的提交路径

访问互联网资源时不能每次都需要把所有Cookie带上。访问不同的资源时，可以携带不同的Cookie，我们可以通过cookie的setPath(String path)方法对cookie的路径进行设置。

```java
@WebServlet("/servletA")
public class ServletA extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //创建cookie
        Cookie cookie1 = new Cookie("keyA","valueA");
        //设置持久化时间
        cookie1.setMaxAge(60*5);
        //设置cookie的提交路径
        cookie1.setPath("/web03_war_exploded/servletB");
        Cookie cookie2 = new Cookie("keyB","valueB");
        //将cookie放入response对象
        resp.addCookie(cookie1);
        resp.addCookie(cookie2);
    }
}
```

### 3.Session

#### 3.1 HttpSession概述

HttpSession是一种保留更多信息在服务端的一种技术，服务器会为每一个客户开辟一块内存空间，即session对象，客户端在发送请求时，都可以使用自己的session，这样服务端就可以通过session来记录某个客户端的状态了。

​	a.服务端在位客户端创建session时，会同时将session对象的id，也就是JSESSIONID以cookie的形式放入响应对象

​	b.后端创建完session后，客户端会收到一个特殊的cookie，叫做JSESSIONID

​	c.客户端下一次请求时携带JSESSIONID，后端收到后，根据JSESSIONID找到对应的session对象

​	d.通过该机制，服务端通过session就可以存储一些专门针对某个客户端的信息了

​	e.session也是域对象

![image-20250218220800518](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250218220800518.png)

应用场景：

​	1.记录用户的登录状态

​		用户登录后，将用户的账号等敏感信息存入session

​	2.记录用户操作的历史

​		例如记录用户的访问痕迹，用户的购物车信息等临时性的信息

#### 3.2 HttpSession的使用

用户提交form表单到ServletA，携带用户名，ServletA获取session将用户名存到session；之后用户再请求其他任意Servlet时，就会获取之前存储的账户。

1.getSession()方法的内部处理逻辑：

![image-20250219154728386](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219154728386.png)

![image-20250219154802052](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219154802052.png)

例：验证servlet2能否获取到servlet1创建的session

创建HTML提交表单

```html
<body>
    <form action="servlet1" method="post">
        用户名：
        <input type="text" name="username">
        <input type="submit" value="提交">
    </form>
</body>
```

创建servlet1：

```java
@WebServlet("/servlet1")
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //接收前端传递的参数
        String username = req.getParameter("username");
        //获得session对象
        HttpSession session = req.getSession();
        //getSession()方法的步骤是：
        //  1.先判断请求中有没有一个特殊的cookie JESSIONID  值为***
        //  2.如果不存在，则会创建一个新的session返回，并且向response对象中存放一个 JESSIONID 的cookie
        //  3.如果存在，则：根据JESSIONID找对应的session对象
        //          若找到JESSIONID则返回之前的session
        //          没找到JESSIONID则创建一个新的session并且返回
        System.out.println(session.getId());
        System.out.println(session.isNew());
        //将 username 存入 session，其中，key为"username"，value为username，也就是前端传递的参数
        session.setAttribute("username",username);
        //客户端响应信息
        resp.setContentType("text/html;charset=UTF-8");
        resp.getWriter().write("success!");
    }
}	
```

创建servlet2：

```java
@WebServlet("/servlet2")
public class Servlet2 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获得session对象
        HttpSession session = req.getSession();
        System.out.println(session.getId());
        System.out.println(session.isNew());
        //读取session中存储的用户名
        String username = (String) session.getAttribute("username");
        System.out.println("servlet2 get username:"+username);
    }
}
```

​	请求servlet1时，输出：

![image-20250219160520761](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219160520761.png)

​	证明已创建一个新的session

​	请求servlet2时，输出：

![image-20250219192331684](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219192331684.png)

#### 3.3 HttpSession时效性

为什么要设置session的时效？

​	用户量很大的时候，session对象相应的也要创建很多。如果一味的创建而不释放，那么服务器端的内存迟早要被耗尽。

​	客户端关闭行为无法被服务端直接侦测到，或者客户端较长时间不操作的应用场景也会经常出现，因此需要对session进行时限设置。

​	默认的session的最大限制时间(两次使用同一个session中的间隔时间)，在tomcat/conf/web.xml中配置为30分钟。

![image-20250219211750863](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219211750863.png)

也可以自己设置时间：

![image-20250219211842169](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250219211842169.png)

还可以通过setMaxInactiveInterval()方法设置

​	例：session.setMaxInactiveInterval(60);

也可以直接让session失效：session.invalidate()

### 4.域对象的使用

#### 4.1 概述

![image-20250220212822289](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220212822289.png)

图解：

![image-20250220212947751](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220212947751.png)

![image-20250220213412476](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220213412476.png)

![image-20250220213602384](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220213602384.png)

![image-20250220213704978](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220213704978.png)

#### 4.2 域对象的使用

域对象的API：

![image-20250220213840209](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220213840209.png)

例：

​	ServletA向三大域中存放数据、获得请求域数据、对ServletB进行转发：

```java
@WebServlet("/servletA")
public class ServletA extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //向请求域中存放数据
        req.setAttribute("request","requestMessage");
        //向会话域中存放数据
        HttpSession session = req.getSession();
        session.setAttribute("session","sessionMessage");
        //向应用域中存放数据
        ServletContext application = req.getServletContext();
        application.setAttribute("application","applicationMessage");

        //获取请求域数据
        String reqMessage = (String)req.getAttribute("request");
        System.out.println("请求域："+reqMessage);
        //请求转发给servletB
        req.getRequestDispatcher("servletB").forward(req,resp);
    }
}
```

​	ServletB获取三大域的数据：

​	

```java
@WebServlet("/servletB")
public class ServletB extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取三大域中的数据
        //获取请求域的数据
        String reqMessage = (String)req.getAttribute("request");
        System.out.println("请求域："+reqMessage);
        //获取会话域的数据
        HttpSession session = req.getSession();
        String sessionMessage = (String)session.getAttribute("session");
        System.out.println("会话域："+sessionMessage);
        //获取应用域的数据
        ServletContext application = req.getServletContext();
        String applicationMessage = (String)application.getAttribute("application");
        System.out.println("应用域："+applicationMessage);

    }
}
```

​	输出：

![image-20250220215829190](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250220215829190.png)

​	注意：由于请求域的范围是一次请求，因此如果没有转发，则请求不到该域中的数据，输出null，并且用重定向也仍然输出null，因为重定向时使用的请求和原来的请求不是同一个。由于会话域的范围是一次会话，因此换一个浏览器请求时就拿不到会话域中的数据了，因为两种浏览器不属于同一个会话。应用域则可以跨多个不同的客户端，但是如果手动清除网页应用域或者重启服务器，则会输出null，因为不属于同一个应用域。

#### 4.3 总结

请求转发时，请求域可以传递数据：请求域内一般放本次业务有关的数据，如：查询到的部门信息

同一个会话内，不用请求转发，会话域可以传递数据：会话内一般放本次会话的客户端有关的数据，如：当前客户端登录的用户

同一个App内，不同的客户端，应用域可以传递数据：应用域内一般放本程序应用有关的数据，如：Spring框架的IOC容器。

## 十二、Filter过滤器

### 1.过滤器概述

1.Filter，即过滤器，是javaee技术规范之一，作用目标资源的请求进行过滤的一套技术规范，是Java Web项目中最为使用的技术之一。

​	a.Filter接口定义了过滤器的开发规范，所有的过滤器都要实现该接口。

​	b.Filter的工作位置是项目中所有目标资源之前，容器在创建HttpServletRequest和HttpServletResponse对象后，会先调用Filter的doFilter方法。

​	c.Filter的doFilter方法可以控制请求是否继续，如果放行，则请求继续；如果拒绝，则请求到此为止，由过滤器本身做出响应。

​	d.Filter不仅可以对请求做出过滤，也可以在目标资源做出响应前，对响应再次进行处理。

​	e.Filter是GOF中责任链模式的典型案例。

​	f.Filter的常用应用包括但不限于：登录权限检查、解决网站乱码、过滤敏感字符、日志记录、性能分析...

2.举例：公司前台、停车场安保、地铁验票闸机

​	a.公司前台对来访人员进行审核，如果是游客则拒绝进入公司，如果是客户则放行，客户离开时提醒客户不要遗忘物品。

​	b.停车场保安对来访车辆进行控制，如果没有车位则拒绝进入，如果有车位则发放停车卡并放行，车辆离开时收取停车费。

​	c.地铁验票闸机在人员进入之前检查票，没票拒绝进入，有票验票后放行，人员离开时同样验票。

3.日常开发场景：日志的记录，性能的分析，乱码的处理，事务的控制

### 2.过滤器使用

目标：开发一个日志记录过滤器

​	a.用户请求到达目标资源之前，记录用户的请求资源路径

​	b.响应之前记录本次请求目标资源运算的耗时

​	c.可以选择将日志记录进入文件，为了方便测试，这里将日志直接在控制台打印

例：定义一个过滤器，编写功能代码

​	Servlet1:

```java
@WebServlet(value = "/servlet1",name = "servlet1")
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("servlet1 service invoked");
        resp.getWriter().write("servlet1Message");
    }
}
```

​	LoggingFilter:

```java
public class LoggingFilter implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    //过滤请求和响应的方法
    /*
    1 请求到达目标资源之前，先经过该方法
    2 该方法有能力控制请求是否继续向后到达目标资源 可以在该方法内直接向客户端做响应处理
    3 请求到达目标资源后，响应之前还会经过该方法
     */
    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        /*
        1 请求到达目标资源之前的功能代码
                判断是否登录
                校验权限是否满足
        2 放行代码

        3 响应之前 HttpServletResponse 转换为响应报文之前的功能代码
         */
        //请求到达目标资源之前的功能代码
        System.out.println("loggingFilter before doFilter invoked");
        //放行代码
        filterChain.doFilter(servletRequest,servletResponse);
        //响应报文之前的功能代码
        System.out.println("loggingFilter after doFilter invoked");
    }

    @Override
    public void destroy() {

    }
}
```

​	web.xml

```xml
<!--    配置过滤器-->   
	<filter>
        <filter-name>loggingFilter</filter-name>
        <filter-class>com.atguigu.filter.LoggingFilter</filter-class>
    </filter>
<!--    配置过滤器的过滤资源规则，两种方式：-->
<!--    url-pattern：根据请求的资源路径 对指定的请求进行过滤-->
    <!--        /*：过滤全部资源   /a/*：过滤以a开头的资源  *。html：过滤以html为后缀的资源
<!-    servlet-name：根据请求的servlet别名，对指定的servlet资源进行过滤-->
    <filter-mapping>
        <filter-name>loggingFilter</filter-name>
<!--        <servlet-name>servlet1</servlet-name>-->
        <url-pattern>/*</url-pattern>
    </filter-mapping>
```

接收request后，进入servlet前，先进入filter中，执行第一个语句输出后，被doFilter放行，然后才进入到servlet中；从servlet返回response时，先进入filter中，执行第三个语句输出后，才返回给前端。

### 3.过滤器的生命周期

1.构造：构造器	public LifeCycleFilter()	项目启动时执行

2.初始化：init	public void init(FilterConfig filterConfig)	构造完成时执行

​	filterConfig：即初始化信息，在xml文件的**<**filter**>** ---> **<**init-param**>**标签中配置，格式为键值对格式

3.过滤：doFilter	public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain)	每次请求时执行

4.销毁：destroy	public void destroy()	服务关闭时执行

### 4.过滤器链的使用

![image-20250222030144318](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222030144318.png)

![image-20250222030245129](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222030245129.png)

例：

​	xml文件：

```xml
<filter>
    <filter-name>filter1</filter-name>
    <filter-class>com.atguigu.filter.Filter1</filter-class>
</filter>
<filter-mapping>
    <filter-name>filter1</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>

<filter>
    <filter-name>filter2</filter-name>
    <filter-class>com.atguigu.filter.Filter2</filter-class>
</filter>
<filter-mapping>
    <filter-name>filter2</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>

<filter>
    <filter-name>filter3</filter-name>
    <filter-class>com.atguigu.filter.Filter3</filter-class>
</filter>
<filter-mapping>
    <filter-name>filter3</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
```

​	则：访问顺序为：前端 ---> filter1 before --->  filter2 before --->  filter3 before --->  servlet --->  filter3 after --->  filter2 after --->  filter1 after

​	因此，访问顺序随mapping标签的顺序而确定。

优化：也可以使用注解的方式定义过滤器：

​	filter1：

```java
@WebFilter("/*")
public class Filter1 implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("filter1 before doFilter invoked");
        filterChain.doFilter(servletRequest,servletResponse);
        System.out.println("filter1 after doFilter invoked");
    }

    @Override
    public void destroy() {

    }
}
```

​	filter2：

```java
@WebFilter("/*")
public class Filter2 implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("filter2 before doFilter invoked");
        filterChain.doFilter(servletRequest,servletResponse);
        System.out.println("filter2 after doFilter invoked");
    }

    @Override
    public void destroy() {

    }
}
```

​	filter3：

```java
@WebFilter("/*")
public class Filter3 implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("filter3 before doFilter invoked");
        filterChain.doFilter(servletRequest,servletResponse);
        System.out.println("filter3 after doFilter invoked");
    }

    @Override
    public void destroy() {

    }
}
```

​	因此，如果使用注解定义过滤器，过滤顺序按照类名的字典顺序确定。

## 十三、Listener监听器

### 1.概述

![image-20250222151218309](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222151218309.png)

### 2.主要接口

#### 2.1 application域监听器

1.ServletContextListener 监听 ServletContext 对象的创建与销毁

方法：

​	contextInitialized(ServletContextEvent sce)：ServletContext创建时调用

​	contextDestroyed(ServletContextEvent sce)：ServletContext销毁时调用

​	注意：ServletContextEvent对象代表从ServletContext对象身上捕获到的事件，通过这个事件对象我们可以获取到ServletContext对象。

2.ServletContextAttributeListener 监听 ServletContext 中属性的添加、移除和修改

方法：

​	attributeAdded(ServletContextAttributeEvent scab)：向ServletContext中添加属性时调用

​	attributeRemoved(ServletContextAttributeEvent scab)：从ServletContext中移除属性时调用

​	attributeReplaced(ServletContextAttributeEvent scab)：当ServletContext中的属性被修改时调用

​	ServletContextAttributeEvent对象代表属性变化事件，它包含的方法如下：

​		getName()：获取修改或添加的属性名

​		getValue()：获取被修改或添加的属性值

​		getServletContext()：获取ServletContext对象

例：

​	listener：

```java
@WebListener
public class MyApplicationListener implements ServletContextListener, ServletContextAttributeListener {
    @Override
    public void contextInitialized(ServletContextEvent servletContextEvent) {
        ServletContext application = servletContextEvent.getServletContext();
        System.out.println(application.hashCode()+"应用域被初始化");
    }

    @Override
    public void contextDestroyed(ServletContextEvent servletContextEvent) {
        ServletContext application = servletContextEvent.getServletContext();
        System.out.println(application.hashCode()+"应用域被销毁");
    }

    @Override
    public void attributeAdded(ServletContextAttributeEvent servletContextAttributeEvent) {
        //监听数据增加
        ServletContext application = servletContextAttributeEvent.getServletContext();
        String key = servletContextAttributeEvent.getName();
        String value = (String)servletContextAttributeEvent.getValue();
        System.out.println(application.hashCode()+"应用域增加了："+key+":"+value);
    }

    @Override
    public void attributeRemoved(ServletContextAttributeEvent servletContextAttributeEvent) {
        //监听数据移除
        ServletContext application = servletContextAttributeEvent.getServletContext();
        String key = servletContextAttributeEvent.getName();
        String value = (String)servletContextAttributeEvent.getValue();
        System.out.println(application.hashCode()+"应用域移除了："+key+":"+value);
    }

    @Override
    public void attributeReplaced(ServletContextAttributeEvent servletContextAttributeEvent) {
        //监听数据修改
        ServletContext application = servletContextAttributeEvent.getServletContext();
        String key = servletContextAttributeEvent.getName();
        String value = (String)servletContextAttributeEvent.getValue();//获取的是修改前的值
        Object newValue = application.getAttribute(key);//获取的是修改后的新值
        System.out.println(application.hashCode()+"应用域修改了："+key+":旧为"+value+"新为"+newValue);
    }
}
```

​	servlet1：

```java
@WebServlet("/servlet1")
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //向应用域中放入数据
        ServletContext application = this.getServletContext();
        application.setAttribute("keyA","valueA");
    }
}
```

​	servlet2：

```java
@WebServlet("/servlet2")
public class Servlet2 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //修改应用域中的数据
        ServletContext application = this.getServletContext();
        application.setAttribute("keyUpdate","valueUpdate");
    }
}
```

​	servlet3：

```java
@WebServlet("/servlet3")
public class Servlet3 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //删除应用域中的数据
        ServletContext application = this.getServletContext();
        application.removeAttribute("keyA");
    }
}
```

​	输出：

![image-20250222213158200](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222213158200.png)

![image-20250222213228610](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222213228610.png)

![image-20250222213351682](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250222213351682.png)

#### 2.2 Session域监听器

同application域监听器，只需要更改方法名。

#### 2.3 Request域监听器

同application域监听器，只需要更改方法名。
