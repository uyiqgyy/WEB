# REST 一些概念和技术
> Representational State Transfer  
> 笔记   

## 相关框架
* Java - JRX-RS
* Python - Django
* Groovy - Grails
* 构建工具
 * Maven
 * Gradle
 
## 一些概念
1. 是一种架构风格。
2. **表述性状态**是对资源数据在某个瞬间状态的快照。
3. **表述（representation）**：资源的某个瞬时状态。
4. **状态**：包括资源数据的内容，表述格式（XML，JSON，Atom等）等信息
5. **转移**：从服务器到客户端，或者相反方向。
6. 请求一个资源的过程：访问一个具有指定性和描述性的URI（Uniform Resource Identifier），将资源的表述从服务器转移到客户端，或者相反的方向。
7. 基本实现形式：HTTP+URI+XML

## REST服务
1. RESTful Web Services：
 1. 一种ROA（Resource-oriented Architecture）
 2. 方法信息在HTTP的方法中（GET或者POST）
 3. 与RPC风格对比。（Remote Procedure Call）远程过程调用  
   RPC关注服务器-客户端的方法的调用，并不关注在那个的网络层的哪个协议。  
   即是一种面向**方法调用过程**的风格。  
   （1）XML-RPC  
   用XML格式封装方法调用，用HTTP来传输，请求方法都是POST。
   相比与使用XML的REST来说，**数据内容**上XML里比REST多了调用和参数的信息，REST只包含了资源的状态。  
   **响应状态**上来讲，REST会包含响应实体信息以及HTTP状态码和可选的异常信息。  
   XML只会有相应信息。  
   **SOAP**： 替代了XML-RPC。 **Thrift** 又可以替代SOAP。
为了包装RPC的请求信息，推出了XML-RPC，但XML-RPC只能使用有限的数据类型种类和一些简单的数据结构。于是就出现了SOAP(Simple Object Access Protocol)。SOAP最主要的工作是使用标准的XML描述了RPC的请求信息(URI/类/方法/参数/返回值)。理论上，SOAP就是一段xml，你可以通过http,smtp等发送它(复制到软盘上，叫快递公司送去也行?)。同样SOAP也是跨语言的。  
为了包装RPC的请求信息，推出了XML-RPC，但XML-RPC只能使用有限的数据类型种类和一些简单的数据结构。于是就出现了SOAP(Simple Object Access Protocol)。SOAP最主要的工作是使用标准的XML描述了RPC的请求信息(URI/类/方法/参数/返回值)。理论上，SOAP就是一段xml，你可以通过http,smtp等发送它(复制到软盘上，叫快递公司送去也行?)。同样SOAP也是跨语言的。  
**WSDL**  
WSDL(Web Services Description Language)是描述web服务的，是描述怎样访问web服务的。WSDL是用来描述SOAP的，换句话说，WSDL 文件告诉你调用 SOAP 所需要知道的一切。WSDL也是一段xml。现在各个语言对wsdl的支持都很成熟，可以根据同一份wsdl文件生成自己语言的客户端。  
（2）Big Web Service： SOAP + WSDL + UDDI + WS-标准栈。  
UDDI是统一描述、发现和集成（Universal Description, Discovery, and Integration）的缩写。它是一个基于XML的跨平台的描述规范，可以使世界范围内的企业在互联网上发布自己所提供的服务。  
相比，REST服务形式更简单、设计更轻量、实现更快捷。不需要引入SOAP消息传输层，无须注册服务，没有客户端stub概念，但是没有提供**安全策略**等全面的标准规范。  
2. Jersey项目是GlassFish项目的一个子项目，专门用来实现JAX-RX标准，并提供扩展性。
3. JBoss - RESTEasy
4. Apache - CXF
5. 其他REST的实现：Java领域支持REST式Web服务开发的未必是遵循了JAX-RS规范。
 1. Restlet
 2. Linkedin - Rest.li
 3. Spring WEB MVC
