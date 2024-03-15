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

JSON data format

## 1. Communication between Client and Server

clients send requests to retrieve or modify resources, and servers send responses to these requests.

### Making Requests

A request generally consists of:

- an HTTP operation to perform
- a *header*, which allows the client to pass along information about the request
- a path to a resource
- an optional message body containing data

### Sending Responses -- same as HTTP response content

## 2.  Stateless

The Server can't store any data during a Client-Server communication, every request is a standalone request. 

Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.

此约束使 Web 服务具有高度可扩展性，因为无需在客户端和特定服务器之间保留任何关联性。任何服务器都可以处理来自任何客户端的任何请求。也就是说，其他因素可能会限制可扩展性。

# 三）HTTP

**HTTP Protocol** (**H**yperText **T**ransfer **P**rotocol): **the communication standard that rules the Internet world by defining the interaction patterns between Clients and Servers**

<img src="/Users/akira/Desktop/截屏2024-03-14 09.14.14.png" alt="截屏2024-03-14 09.14.14" style="zoom:50%;" />

## 1. HTTP request content

<img src="/Users/akira/Desktop/截屏2024-03-14 09.17.25.png" alt="截屏2024-03-14 09.17.25" style="zoom:50%;" />

1. HTTP version type

2. a URL

3. an HTTP method: 

   <img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-13 08.52.32.png" alt="截屏2024-03-13 08.52.32" style="zoom:50%;" />

4. HTTP request headers

5. Optional HTTP body.

### HTTP response content

An HTTP response is what web clients (often browsers) receive from an Internet server in answer to an HTTP request.

1. an HTTP status code: https://en.wikipedia.org/wiki/List_of_HTTP_status_codes

   | Code Block | Type          | Description                                                  |
   | ---------- | ------------- | ------------------------------------------------------------ |
   | 1xx        | Informational | Request received, continuing process.                        |
   | 2xx        | Success       | The action was successfully received, understood, and accepted. |
   | 3xx        | Redirection   | Further action needs to be taken to complete the request.    |
   | 4xx        | Client Error  | The request contains bad syntax or cannot be fulfilled.      |
   | 5xx        | Server Error  | The server failed to fulfill an apparently valid request.    |

   <img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-03-14 08.20.22.png" alt="截屏2024-03-14 08.20.22" style="zoom:50%;" />

2. HTTP response headers

3. optional HTTP body



HTTP Request Target

![截屏2024-03-14 09.40.44](/Users/akira/Desktop/截屏2024-03-14 09.40.44.png)

Media types













## JSON

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation)  is the most generally popular file format to use







https://www.codecademy.com/article/what-is-rest