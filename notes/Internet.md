# Internet & REST & JSON

## 1. How the Internet works:

works by connecting devices and computer systems together using a set of **standardized protocols**.

**protocols** define how information is exchanged between devices and ensure that data is transmitted reliably and securely.

**interconnected** routers are responsible for directing traffic between different devices and systems. When you send data over the internet, it is broken up into small packets that are sent from your device to a router. The router examines the packet and forwards it to the next router in the path towards its destination. This process continues until the packet reaches its final destination.

To ensure that packets are sent and received correctly, the internet uses a variety of **protocols**:

IP, TCP, DNS, HTTP, SSL/TLS

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-12 22.44.22.png" alt="截屏2024-03-12 22.44.22" style="zoom:50%;" />

## 2. Basic concepts

| Term        | Definition                                                   |
| ----------- | ------------------------------------------------------------ |
| Packet      | A small unit of data that is transmitted over the internet.  |
| Router      | A device that directs packets of data between different networks. |
| IP Address  | A **unique identifier** assigned to each device on a network, used to route data to the correct destination. |
| Domain Name | A **human-readable name** that is used to identify a website, such as google.com. |
| DNS         | The Domain Name System is responsible for **translating domain names into IP addresses**. |
| HTTP        | The Hypertext Transfer Protocol is used to **transfer data between a client (such as a web browser) and a server (such as a website)**. |
| HTTPS       | An encrypted version of HTTP that is used to provide secure communication between a client and server. |
| SSL/TLS     | The Secure Sockets Layer and Transport Layer Security protocols are used to provide secure communication over the internet. |

## 3. Protocols

IP is responsible for routing packets of data to their correct destination, while TCP and UDP ensure that packets are transmitted reliably and efficiently. DNS is used to translate domain names into IP addresses, and HTTP is used to transfer data between clients and servers.

## 4. Example/ process:

当您在浏览器中输入网址时（我们的比喻就像步行到商店）：

1. 浏览器转到 DNS 服务器，找到网站所在服务器的真实地址（您找到商店的地址）。
2. 浏览器向服务器发送一条 HTTP 请求消息，要求其将网站的副本发送给客户端（您去商店订购商品）。此消息以及客户端和服务器之间发送的所有其他数据均使用 TCP/IP 通过 Internet 连接发送。
3. 如果服务器批准了客户端的请求，服务器会向客户端发送“200 OK”消息，这意味着“当然你可以查看该网站！就在这里”，然后开始将网站的文件作为一系列文件发送到浏览器称为数据包的小块（商店给你你的商品，你把它们带回你家）。
4. 浏览器将这些小块组装成一个完整的网页并将其显示给您（货物到达您家门口 - 新的闪亮的东西，太棒了！）。

## 5. Domain Name

### Structure

用点分隔并**从右向左读取**：

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-13 08.58.14.png" alt="截屏2024-03-13 08.58.14" style="zoom:50%;" />

[TLD](https://developer.mozilla.org/en-US/docs/Glossary/TLD)（顶级域名）。

TLD 告诉用户域名背后服务的一般用途。最通用的 TLD ( `.com`、`.org`、`.net`) 不要求 Web 服务满足任何特定标准，但某些 TLD 执行更严格的政策，因此其目的更加明确。例如：

- 本地 TLD（例如`.us`、`.fr`、 或 ）`.se`可以要求以给定语言提供服务或在特定国家/地区托管 - 它们应该指示特定语言或国家/地区的资源。
- 包含以下内容的 TLD`.gov`只允许政府部门使用。
- TLD`.edu`仅供教育和学术机构使用。

[标签（或组件）](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_domain_name#label_or_component)

标签是 TLD 后面的内容。标签是不区分大小写的字符序列，长度为 1 到 63 个字符，仅包含字母`A`到`Z`、数字`0`到`9`以及“-”字符（可能不是标签中的第一个或最后一个字符）。

位于 TLD 之前的标签也称为*二级域名*(SLD)。对于您控制的任何域（例如[mozilla.org](https://www.mozilla.org/en-US/)），您可以创建每个域包含不同内容的“子域”,如[developer.mozilla.org](https://developer.mozilla.org/)

# 二）REST 

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-14 08.13.15.png" alt="截屏2024-03-14 08.13.15" style="zoom:50%;" />

**REST, or REpresentational State Transfer is an architecture style to develop web services, which uses the HTTP protocol as a communication interface in order to transfer data through HTTP methods.**

REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server.

Based on the concept of a **resource**: 

Resources are the nouns of the Web - they describe any object, document, or *thing* that you may need to store or send to other services.

Uniform Resource Identifier (URI) uniquely identifies the resource. https://abc.com/customer/7835

REST 代表表述性状态传输。它是一种架构风格，定义了一组用于创建 Web 服务的约束。它不是像HTTP那样的协议，但它使用HTTP进行通信。

**JSON** data format is mostly used for usual data. 

REST APIs are built on **standard HTTP messages** to perform operations on resources.

## 1.  Stateless request model

The Server can't store any data during a Client-Server communication, every request is a standalone request. 

Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.

此约束使 Web 服务具有高度可扩展性，因为无需在客户端和特定服务器之间保留任何关联性。任何服务器都可以处理来自任何客户端的任何请求。也就是说，其他因素可能会限制可扩展性。

## 2. Communication between Client and Server

clients send requests to retrieve or modify resources, and servers send responses to these requests.

### Making Requests

A request generally consists of:

- an HTTP operation to perform
- a *header*, which allows the client to pass along information about the request
- a path to a resource
- an optional message body containing data

### Sending Responses -- same as HTTP response content



# 三）HTTP

**HTTP Protocol** (**H**yperText **T**ransfer **P**rotocol): **the communication standard that rules the Internet world by defining the interaction patterns between Clients and Servers**

## 1. HTTP request & respond content



<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2012.37.21-0675585.png" alt="截屏2024-03-17 12.37.21" style="zoom:50%;" />

## Structure of request and response

| Structure Element | Request                                                      | Response                                                     |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Start-line        | the HTTP method, URL, and HTTP version.                      | the HTTP version, status code, and the status message indicating the result of the request. |
| HTTP Headers      | An optional set of HTTP headers **specifying the request**, authentication information, and any data about the request body being sent. | An optional set of HTTP headers that contain metadata about the response (like content type, set cookies, server information). |
| Blank Line        | A blank line indicating the end of headers and the beginning of the body. | Same                                                         |
| Body              | An optional body that contains data to be sent to the server (like content of an HTML form in POST requests). | An optional body containing the data from the server (like the requested resource, error messages, or other information). |

### 1.1 Specific for request

#### a. HTTP method: 

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-13 08.52.32.png" alt="截屏2024-03-13 08.52.32" style="zoom:50%;" />

#### b. URLs

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2013.17.14.png" style="zoom:50%;" />

#### c. media types/ MIME types (in header)

data formats

Accept header for requests, **Content-Type** header for body

 • JSON media type: **application/json**

 • XML media type: **application/xml** 

 • textual data: **text/plain**

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2013.22.23.png" style="zoom:50%;" />



## d. JSON

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation)  is the most generally popular file format to use

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2015.55.47.png" style="zoom:50%;" />

##### 1. JSON values

| Data Type            | Example                       |
| -------------------- | ----------------------------- |
| String               | "Hello, World!"               |
| Number               | 42                            |
| Object (JSON object) | {"name": "John", "age": 30}   |
| Array                | ["apple", "banana", "cherry"] |
| Boolean              | true                          |
| Null                 | null                          |

cannot be: function/ date/ undefined

##### 2. Related standards

**JSON schema**(https://json-schema.org/):  allows to define valid data structures and values and can be used to validata JSON documents

**JSON Patch**(http://jsonpatch.com/): a format for describing changes to a Json document 

It can be used to avoid sending a whole document when only a part has changed

**Used in combination with the HTTP PATCH method**: http://tools.ietf.org/html/rfc5789

##### 3. Conversion from/ to JSON

`JSON.parse()`：用来解析JSON字符串，将其转换成JavaScript对象或值。常用于处理来自网络服务器或其他来源的JSON格式数据。当接收到JSON格式的字符串，并想将它转换成JavaScript可以操作的对象时，会使用这个方法。

```javascript
var myJSON = '{"name":"John", "age":31, "city":"New York"}';
var myObj = JSON.parse(myJSON);
// 现在 myObj 是一个 JavaScript 对象。
```

`JSON.stringify()`：将JavaScript对象或值转换成JSON字符串。这个方法常用于当需要将JavaScript对象发送到网络服务器或者保存到文件中时，因为这些场景通常要求数据是字符串格式的JSON。

```javascript
var myObj = {name: "John", age: 31, city: "New York"};
var myJSON = JSON.stringify(myObj);
// 现在 myJSON 是一个 JSON 字符串，可以发送到服务器或保存到文件。
```

一些可能出现的问题：

- **日期被解析为字符串**：在JSON中，日期没有专门的数据类型，所以在使用JSON.parse和JSON.stringify时，日期通常会被转换成字符串格式，这意味着它们会失去日期对象的方法和属性。
- **只有树（层级）数据结构被良好处理**：由于JSON是一个基于文本的数据格式，它自然地适用于层级或树形结构的数据。非层级的数据结构，如图（graphs），不适合直接用JSON表示。
- **图形不直接支持，特别是循环图形**：JSON不能直接表达图形数据结构中的循环引用，因为这会导致JSON.stringify方法出现问题。
- **没有直接支持以构造函数实例的形式重新创建对象**：例如，在ECMAScript 6（ES6）中引入的类（classes），使用JSON.stringify方法转换为JSON后，不能直接转换回其原有的类实例。你通常需要一些额外的逻辑来恢复类实例。

### 1.2 How to design RESTTul services?

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2016.37.05.png" style="zoom:40%;" />

More details about Web API design: https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design

#### 1.2.1 Identify resources and URIs

##### Resources

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2016.40.12.png" style="zoom:40%;" />

##### URI templates

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2016.41.40.png" style="zoom:40%;" />

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2016.43.04.png" style="zoom:40%;" />

#### 1.2.2 Define operations in terms of HTTP methods

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2016.44.14.png" style="zoom:40%;" />

Example:

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2017.47.14.png" style="zoom:50%;" />

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2017.47.21.png" style="zoom:50%;" />

## Open API specification

OpenAPI规范，这是一个用于描述RESTful服务的API描述标准。

OpenAPI规范允许你详细描述整个API，包括：

- 可用的端点和每个端点上的操作（例如，`GET /users`, `POST /users`）。

- 每个操作的参数。

- 认证方法。

- 联系信息，许可证，使用条款等其他信息。

  more details: https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md

  

API规范可以用YAML或JSON格式编写，易于学习且对人和机器都易读。

有工具可以自动化Web API设计，例如：

- OpenAPI（Swagger）Editor：这是一个微软Visual Studio Code的扩展程序。
- Postman：一个流行的API开发工具，可用于测试API。

一些工具可以生成用于在浏览器或Node.js环境中调用Web API的客户端API。

#### Consuming (invoking) RESTful services---Asynchronous JavaScript And XML (AJAX) calls

- **内置对象和API**：
  - `XMLHttpRequest`：这是早期的API，基于回调函数，但现在不再推荐使用。
  - `Fetch API`：这是一个基于Promise的现代API，它提供了一个强大且灵活的方式来发出HTTP请求。
- **第三方库**：
  - `Axios`：这是一个非常流行的基于Promise的HTTP客户端，它可以在浏览器和Node.js中使用。

## Fetch API

- 对于Node.js，有一个`node-fetch`包，它是Fetch API的一个实现。

- 例子：如何发出一个GET请求并处理返回的JSON数据。

  <img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2017.54.33.png" style="zoom:50%;" />

- 有关Fetch API的更多信息：https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch

- Grammar:

  - `fetch`函数接收一个指定端点（URL）的资源字符串，以及一个可选的描述HTTP请求的`init`对象。

    <img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2017.56.50.png" style="zoom:40%;" />

  - ```markdown
    init对象的主要属性包括：
    ```

    - `method`：请求方法，如GET或POST。
    - `headers`：要添加到请求中的任何头信息。
    - `body`：要添加到请求中的任何主体内容。对于JSON格式，JavaScript对象必须使用`JSON.stringify()`明确转换。

  - `fetch`函数的返回值is a promise that resolves to a Response object.





### 1.3 HTTP response content

An HTTP response is what web clients (often browsers) receive from an Internet server in answer to an HTTP request.

#### HTTP status code: https://en.wikipedia.org/wiki/List_of_HTTP_status_codes

| Code Block | Type          | Description                                                  |
| ---------- | ------------- | ------------------------------------------------------------ |
| 1xx        | Informational | Request received, continuing process.                        |
| 2xx        | Success       | The action was successfully received, understood, and accepted. |
| 3xx        | Redirection   | Further action needs to be taken to complete the request.    |
| 4xx        | Client Error  | The request contains bad syntax or cannot be fulfilled.      |
| 5xx        | Server Error  | The server failed to fulfill an apparently valid request.    |

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-14 08.20.22.png" alt="截屏2024-03-14 08.20.22" style="zoom:50%;" />



### 整个流程可以这样描述：

- 用户在客户端（如浏览器）进行操作，比如点击一个按钮来获取用户列表。
- 客户端的JavaScript代码使用Fetch API来发送一个HTTP GET请求到服务器的RESTful API端点（如`/api/users`）。
- 服务器处理这个请求，获取用户数据，并将其作为JSON格式的响应数据返回。
- Fetch API接收到服务器的HTTP响应，并利用JavaScript处理返回的JSON数据，可能会更新网页上的信息或界面。

总之，RESTful API定义了客户端和服务器之间通信的规则和结构，HTTP是这种通信的协议，JSON是数据交换的格式，而Fetch API是在客户端执行HTTP请求的一种方法。

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2018.52.02.png" style="zoom:50%;" />



<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2018.52.09.png" style="zoom:50%;" />

<img src="/Users/akira/Library/Application%20Support/typora-user-images/%E6%88%AA%E5%B1%8F2024-03-17%2018.52.15.png" style="zoom:50%;" />

https://www.codecademy.com/article/what-is-rest