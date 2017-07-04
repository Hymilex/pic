## 第一章

- WebGIS：WebGIS是一种在Internet或Intranet环境下基于HTTP协议的用来存储、管理、分析、发布和共享地理信息的B/S模式的分布式计算机应用系统。
- WebGIS、网络GIS、InternetGIS的比较:
    - 网络GIS所包含的内容最广泛，网络GIS使用的协议可以是TCP/IP，也可以是其他网络协议，甚至是无线通信协议如WAP，GPRS或蓝牙协议等;
    - Internet GIS（互联网GISInternet ）是网络GIS的一个子集，是基于TCP/IP协议的网络GIS，因此可以分布在互联网上运行。这些GIS可以是C/S模式也可以是B/S模式，Google公司的Google Earth，就是一种典型的网络地图的客户端工具；
    - WebGIS，一种B/S模式的Internet GIS，从技术角度看，WebGIS应具有以下特征：
        - 是通过Web服务器（如IIS，Apache等）发布的动态的Web应用；
        - 客户端是通用的Web浏览器，如IE，Firefox等。用户通过Web浏览器与地图进行交互。
        - 基于HTTP协议的B/S模式的分布式GIS。
- 大众化的新一代WebGIS应用的共同特点是：
    - 提供大众化和个性化的地图查询服务；
    - 采用基于Ajax（Web2.0）的新一代Web开发技术；
    - 服务器端以地图切片的形式提供预先渲染好的地图图片服务；
    - 地图浏览采用分级缩放方式；
    - 地图服务的功能丰富：主要包括基本的地图浏览，查询定位，   路径规划，用户标注、LBS和导航服务等。
- WebGIS的主要优点和缺点:
    - 优点:
        - 是一种大众化的GIS。
        - 管理成本低。
        - 与其他Web应用的无缝集成。
        - 客户端平台独立性。
        - 数据维护方便，现势性强。
    - 缺点:
        - 有限的交互性
        - 响应速度受到带宽的限制
        - 超时限制
-  WebGIS的基本思想就是在互联网上提供地理信息服务，让用户通过浏览器从WebGIS服务器上获取地理数据和地理处理服务。
- WebGIS的基本架构:![Markdown](http://i2.kiimg.com/1949/17b583c2610f1614.png)

- 新一代WebGIS产品:GoogleMap、51ditu、Yahoo地图、Sogou 地图。

## 第二章 WebGIS的网络基础 

- 什么叫HTTP协议;特点;
    - HTTP协议:一种详细规定了Web服务器和浏览器之间互相通信的规则，在Internet上传送Web文档的数据传送协议;
    - 特点:
        - 简单快速
        - 灵活
        - 无连接
        - 无状态:HTTP是无状态协议。
- HTTP协议请求响应的过程:
    - 四个阶段:连接、请求、响应、断开。
    - HTTP请求：也就是Web客户端向Web服务器发送信息。
    - HTTP请求构成:
        - 请求行：请求方法+请求网址+HTTP版本；
        - HTTP头
        - 内容
    - HTTP响应构成：
        - 状态行：HTTP版本+响应状态码+状态码的描述；
        - HTTP头
        - 返回内容：HTTP请求所请求的信息。这个信息可以是一个HTML，也可以是一个图片。
- TCP/IP 分层
    - 应用层、传输层、网络层、链路层
    - OSI/ISO 模型:开放系统互连参考模型（OSI，Open System Interconnect Reference Model），把整个网络的通信功能划分了7个层次，每一层是相对独立的，完成数据传输过程中的部分功能。
    - TCP/IP的核心是传输层和网际层。
    - HTTP工作在客户端的应用层上/
- DNS :(DOMAIN NAME SYSTEM)域名系统,计算机可以被赋予IP地址，也可以被赋予主机名或域名。比如：www.cumt.edu.cn；DNS服务是和HTTP协议一样位于应用层的协议。它提供域名到IP地址之间的解析服务。
- Cookie：通过在请求和响应报文中写入Cookie信息来控制客户端的状态。


## 第三章 WebGIS技术基础

- HTML文件的构成:由 HTML标记、元素及其属性构成。
- HTML元素：元素一般由一个起始标记和对应的结束标记、标记之间的内容构成，浏览器依据标记对元素中的文字或图片等内容进行控制和显示。
- HTML属性：属性是元素具有的，用来告诉浏览器如何控制或显示元素内容的。
- DTD （DocumentTypeDefinition）即文档类型定义，它指定了文档中的有效元素、属性及元素之间的关系。
- DTD作用?
- URL URI 之间的关系是什么
    - URI（统一资源标识符）：当用户从HTML网页链接到另外一个HTML网页时，依靠的 是URI，URI会把网页定位到世界上某台服务器上正确的位置。URI是 HTML网页的基本要素之一。
    - URL（统一资源定位符）：要链接Web中不同计算机上的文档，需要定义一个统一的格式来描述互联网上的文件、文档片断或服务资源的地址，即URL。URL是因特网上标准的资源地址。
    - URL与URI区别：
        - URI用字符串标识某一互联网资源，而URL表示资源的地点； 
        - URL是URI的子集；

- 表单
    - 表单是前台页面和后台处理程序（ASP、JSP、CGI等）的接口。 
    - name属性：给整个表单起的名字，以便后台程序获取表单中的信息；Request其值。
    - method属性：定义后台程序获取表单中信息的方法，取值有二：get和post；
        - Get方法：表示该表单主要是从服务器中获取信息，因此它传送给服务器的反馈信息长度有限制；
        - Post方法：表示该表单主要是向服务器发送信息，它传送给服务器的反馈信息长度没有限制；POST机制本身 就比GET机制的安全性能好一点。
    - action属性：来设置处理表单的后台程序，比如本例的action="accept.asp"，表明表单中的内容提交给后台处理程序accept.asp来处理。
    - enctype属性：用于设置表单中信息的编码方式。
        - 取值有：unknown和enctype，默认为unknown，当多数情况下不需要设置该项，不过当我们需要上传文件时就c需要设为multipart/form-data编码方式。 
- Get与Post方法的异同：
- 在HTML上：GET示该表单主要是从服务器中获取信息，因此它传送给服务器的反馈信息长度有限制；Post方法：表示该表单主要是向服务器发送信息，它传送给服务器的反馈信息长度没有限制；
- 在服务器上:
    - Get方式提交的表单在地址栏会显示参数名和参数值，而post方式不会；
    - 由于浏览器地址栏能输入的最大字符数有限制，所以用get方式提交不能处理参数值更大的表单，而post方式则没有这个限 制；

- 标记和元素的区别:元素是由一个起始标记和对应的结束标记、标记之间的内容构成。元素不包括其内容。
- 样式表概念：样式表是规范浏览器如何显示HTML特定标记的一组规则。
- 样式表构成：标记名称，标记属性
- 样式表作用：设计者可以更加灵活地控制页面显示效果：
    - 可以将格式和结构分离，既使HTML简单明了。又让样式表能够独立出来控制页面外观；
    - 可以制作体积更小下载更快的网页，因为对同一类别标记的控制只需要一段共同代码；
    - 可以同时更新大量网页。比以前更快更容易，最后，可以使浏览器成为更友好的界面。
- 样式表的种类，前两种可以称为内部样式表，后两种称为外部样式表。
    - 内联式样式表
    - 嵌入式样式表
    - 输入外部样式表：
    ```
    <style>
         <!--@import url("...");-->
    </style>
    ```
    - 链接外部样式表。

- ID CLASS规则 （代码）
- DIV SPAN 区域标签的区别:<div>标记是一个块级标记，可以包含段落、标题、表格、章节等对象。而<span>标记却是个行内标记，即它只能用于标记同行对象。换句话说，<span>标记不能自动换行，而<div>标记能够产生换行。
- POSITION有哪些取值：
    - absolute表示使用绝对坐标来进行区域定位;
    - relative是指相对于前一个区域的原始位置，新的区域使用相对坐标来定位;
    - static则是使top和left属性失效，按照HTML的默认位置顺序进行定位。

- HTML中包含JS代码有哪两种方式：
    - 直接在HTML中添加JavaScript代码
    - 导入JavaScript文件
- DOM定义。JS 中数组、JSON格式、FOR IN循环 代码
    - DOM（文档对象模型）：通过 HTML DOM，可访问HTML文档的所有元素；当网页被加载时，浏览器会创建页面的文档对象模型；HTMLDOM模型被构造为对象的树。 
    - Json格式(语法规则的核心,简答)：Json是一种轻量级的数据交换格式。
        - 数据在名称/值对中
        - 数据由逗号分隔
        - 花括号保存对象
        - 方括号保存数组
    - FOR IN  在ES6中变为了FOR OF 循环。
- JS中的数组、对象、RegExp对象。
    -  数组表示的两种方式:
        - var cars=[]
        - var cars=new Array("a","b");
    - 对象 {}
    - RegExp对象是由字符串组成的字符组合。eg:var searchperson=new Regexp("");
- JS库文件：Javascript库就是可重用Javascript代码的集合，让我们在程序只需添加几行代码就能完成复杂的操作。
- 使用库的原因:
    - 比我们自己编写的代码会更完善
    - 吸取其他程序员的思路
    - 利用细致编写的库可以避免跨浏览器时JavaScript可能产生的问题
- 常见的库文件:
    - Prototype框架：优势在于DOM扩展和Ajax处理，在JSON支持与创建和继承类方面也做的不错
    - Dojo：是个开源工具集，能够简化创建程序和用户界面的工作；最新版本不仅支持全部主流浏览器，还支持手机环境；
    - jQuery：是个小型高效的Javascript库，简化了多种开发工作，比如HTML文档转换、事件处理、动画和Ajax调用
    - MooTools

## 第三章
- ASP.NET的扩展名、JS、ASP.NET如何工作？
- 从根本上说,ASP.NET与HTML完全相同。
- HTML的扩展名是.html或者.htm。浏览器请求服务器的HTML页面，服务器不会进行任何的修改，就会把该页面发到浏览器。
- ASP.NET页面的扩展名是.ASPX。如果浏览器请求某张ASP.NET页面，那么服务器在结果发回之前，服务器首先会处理该页面的可执行的代码。
    - 当浏览器请求ASP.NET文件时 ，IIS会把该请求传递到服务器上的ASP.NET引擎。
    - ASP.NET逐行读取文件并且执行。
    - ASP.NET最终以纯HTML文件格式返回浏览器。

- ASP.NET内置对象
    - Request：Request封装了客户端请求信息。可以使用Request对象访问任何基于HTTP请求的所有信息，包括从HTML表单（Form）用POST方法或GET方法传递的参数、cookie和用户认证信息。
    - Response：Response代表了服务器响应对象。每次客户端发出一个请求的时候，服务器就会用一个响应对象来处理这个请求，处理完这个请求之后，服务器就会销毁这个响应对象，以便继续接收其它客户端请求。 
    - Server对象：Server对象是用于获取服务器的相关信息的对象。
    - Session对象：Session对象**用来保存与特定用户相关的信息**，Session中的数据保存在服务器端，在客户端需要的时候创建Session，在客户端不需要的时候 销毁Session，使它不再占用服务器内存 。
    - Application对象：Application和Session存储的数据类型和存储位置一样，都是存放Object类型的数据（也就是任意类型），并且存放在服务器上，不同的Application中的数据可以由网站中所有的用户来设置或者获取。并且Application中存放的数据没有时间限制，除非我们手动删除或者服务器重新启动，否则存放的数据不会丢失。 
    - Cookie对象：Cookie对象和Session对象一样也是用来保存特定的用户相关的数据，不过Session不同的是Cookie保存在客户端而不是服务器上，每次客户端发出请求的时候都会把Cookie一起发送到服务器，服务器每次响应客户端请求的时候会重新把Cookie发送到客户端保存。
- 区别:
![Markdown](http://i1.buimg.com/1949/2f2ab8f9fa9bc191.png)

- 如何将普通的HTML控件转换为服务器控件  ASP.NET的隐藏域的作用是什么[掌握]
    - ASP.NET 中的 HTML 元素是作为文本来进行处理的。要想使这些元素可编程，就需要向这些 HTML 元素添加runat="server" 属性。该属性指示，此元素是一个服务器控件。同时要添加 id 属性来标识该服务器控件。该 id 引用于操作运行时的服务器控件。
    - 在普通HTML控件中加上了一个id属性和一个runat=”server”标记。
- 隐藏域的作用:因为服务器会保存服务器控件的状态和属性，所以它会利用一些隐藏域来保存这方面的信息，这部分的内容是经过Base64编码的。 
- 单页面、代码页面分离的优势创建一个页面分类
    - 单页模型的特点是HTML标记、控件代码及服务器端运行的C#代码全部包含在一个.aspx页面中。 
    - 缺点:页面和代码混在一起，维护起来较为麻烦。
    - 代码页面模式就是将页面标记（HTML 代码）和服务器端元素放在.aspx页面中，而C#代码位于一个.aspx.cs文件中。采用默认方式创建的aspx网页就是这种方式。
- ADO.NET的组件结构图:它提供了平台互用性和可伸缩的数据访问。ADO.NET增强了对非连接编程模式的支持。ADO.NET是一组用于和数据源进行交互的面向对象类库。通常情况下，数据源是数据库，但它同样也能够是文本文件、Excel表格或者XML文件。
![Markdown](http://i2.kiimg.com/1949/e33ba1529ed57bff.png)

- DataSet对象：DataSet中经常使用的类包括DataTable、DataRow、DataColumn：
    - Data Table称为数据表，用来存储数据；一个DataTable可以包含多个Data Table，每个Data Table又可包含多行（ DataRow）和（ DataColumn）；
    - DataRow表示数据表里的行，提供了对表中数据的插入、删除、更新和查询等功能；
    - DataColumn表示数据表中的数据列（字段），定义了表的数据结构；


## 第四章
- 什么叫web服务器。服务器的发布的方式。代表性的产品
    - Web服务器：WEB服务器也称为WWW服务器，主要功能是提供网上信息浏览服务。
    - 产品：最常用的Web服务器是Apache和Microsoft的Internet信息服务器（Internet Information Server，IIS）、Apache、Tomcat、ngix 等。
    - 服务器的发布的方式：
        - 第一种方法是通过IIS管理器来发布。打开IIS管理器，在默认站点下点击鼠标右键，通过向导来创建和发布虚拟目录。(改虚拟路径)
        - 将要发布的项目直接复制到wwwroot路径下。
        - 共享文件夹。

## 第五章
- 地图API：地图 API 是一种通过 JavaScript （或其他语言）将地图嵌入到网页的 API。该 API 提供了大量实用工具用以处理地图，并通过各种服务向地图添加内容，从而能够在你的网站上创建功能全面的地图应用程序。
- 产品：百度地图API、天地图API、高德地图API、Google 地图API

## 第六章

- 地理信息web服务概念，webservice的体系结构和技术组成
    - 地理信息Web服务：是Web Service技术在GIS领域中的应用，是指使用数据和相关功能以完成基本地学处理任务的Internet应用程序；主要是指处理地理空间信息的服务，主要包括数据服务和处理服务。
    - Web Service体系结构：
    ![Markdown](http://i4.piimg.com/1949/b93bf9039f497168.png)
- OGC 和OPENGIS的名称。全称
    - OGC（The Open Geospatial Consortium，开放地理信息联盟 ）
    - OpenGIS(Open Geodata lnteroperation Specification开放的地理数据互操作规范) ；
- 熟悉OWS服务模型框架。**OWS（OGC Web Services）**服务模型框架：
![Markdown](http://i2.kiimg.com/1949/9aed8a1e30a598ad.png)
- OGC常用的服务类别。WMS  wfs wcs、熟悉WMS、对WMS的描述。
    - 在OGCWeb服务框架中常用的服务：注册服务（CSW）；数据服务（WFS、WCS）；描绘服务（WMS）；处理服务（WPS） 
    - 地理数据服务：提供对空间数据的服务，主要有WFS和WCS，地理数据服务返回的结果通常是带有空间参照体系的数据。
    - 地图描绘服务：提供对空间数据的描绘。主要有WMS，其中地图由多个图层组合起来，每个地图可以用SLD（Styled Layer Descriptor）来对地图进行描述。
    - （WMS）Web地图服务（Web Map Service）：传递以图形方式表示的地图作为对客户查询的响应。地图是地理数据的可视化表现，而不是数据本身。通常情况下，渲染的图片格式有JPEG、PNG、SVG等。客户从WMS请求地图时需要指定图层名称、图形大小、以及使用的空间参考系等参数。客户还可以向不同的WMS示例发出请求，将结果叠加以形成更丰富的地图层叠。
    - 有一个大题。SOA SOAP的名称:
        - SOA（Service-Oriented Architecture）面向服务架构。SOA是一种以服务为基本组件的架构模型，它通过规范化的接口契约将系统中不同功能的单元(服务)联系起来。这些接口的定义是独立的，与实现服务的具体逻辑无关。
        - SOA的体系结构:
            - 服务提供者：发布自己的服务，并对接收到的服务请求进行响应。
            - 服务代理：又叫服务注册中心，相当于一个服务信息的数据库，对服务进行分类并提供搜索服务。
            - 服务使用者：也叫服务消费者，利用服务代理查找所需的服务，进而根据需求使用服务。
        - SOAP协议（Simple Object Access Protocol）简单对象访问协议：
            - web服务流程:客户应用程序通过基于HTTP之上的SOAP协议(简单 对象访问协议)向位于特定URL的服务发出请求；该服务收到请求，进行处理，发回应答。
            - webgis系统  给出开发的方案和开发的技术以及相关作用。


## 第七章

- 开源WEBGIS 的工作原理和技术。
    - 工作原理:
        - 用户通过浏览器访问WebGIS站点发布的地图页面，Web服务器将根据用户的请求，使用OpenGIS定义的标准协议来访问地图服务器的WMS/WFS服务；
        - 地图服务器根据Web服务器发送的请求，根据一定规则访问空间数据库，获取空间数据，生成地图图像或GML格式的文件，并将数据返回给Web服务器；
        - Web服务器对地图服务器发送过来的数据进行渲染，并操作属性数据，将最终结果返回给浏览器。
    - 开源WebGIS技术
        - maptalks、openlayers、Geoserver。

## 第八章

- (感觉不会考)ArcGIS Server  ESRI官网。体系和系统结构、各个部分的作用。
    - 客户端—客户端可以使用ArcGIS for Server Internet 服务或ArcGIS for Server本地服务创建Web应用程序、移动应用程序和桌面应用程序。ArcGIS for Server包括四种指定的客户端应用程序开发框架：1)Web APIs，2）ArcGIS Explorer，3）ArcGIS 移动解决方案，4）ArcGIS Runtime。  
    - Web Adaptor—用于整合GIS服务器与企业级web服务器。Web Adaptor接收web服务请求，并向站点中的GIS服务器发送请求。也可以通过HTTP负载均衡、路由器、或第三方负载均衡软件来暴露站点，在一些情况下，Web Adaptor与负载均衡方案联合使用比较适 用。
    - Web 服务器—Web服务器用于托管Web应用程序和服务，并为ArcGIS for Server站点提供可选的安全和负载均衡能力。
    - 数据服务器—数据服务器包含在GIS服务器上作为服务进行发布的GIS资源。
    - GIS 服务器—GIS服务器用于托管GIS资源（例如地图、地理处理工具和地址定位器等）并将它们作为服务呈现给客户端应用程序。当客户端应用请求某种特定服务时，GIS Server产生响应并且将其返回到客户端应用。GIS服务器可以是一台计算机，也可以是多台计算机。GIS服务器可以配置集群，每个集群专注于运行某项工作，以高效稳定处理多并发请求。

- SOAP REST  表述性状态转移、核心思想、原则。
    - SOAP接口：基于此协议的服务输入、输出都是XML文件；
    - REST接口：定义了一个Web服务的应用程序结构；REST：即表述性状态传递（Representational State Transfer）
    
- 怎么使用ArcGIS for Server：
    - 制作GIS资源（使用 ArcGIS Desktop制作）； 
    - 将资源发布为服务（使用 ArcGIS Server发布）； 
    - 将资源发布为服务（使用 ArcGIS Server发布）； 
    
## XML 

- XML是eXtensible Markup Language的缩写，称为可扩展标记语言
- XML 文档的构成：XML 声明、处理指令、文档类型定义 DTD、元素、属性、注释、CDATA 节
- 格式良好的 XML：
    - 有且只有一个根元素
    - 区分大小写
    - 元素必须要结束标签
    - 元素间不可交叉，要遵循严谨的树型结构
    - 属性值必须用引号括住
    - XML 名字必须以字母或下划线开头，可包含的字符有字母、数字、下划线、连字符和句点.
- 有效的 XML
    - 格式良好的文档指的是 XML 文档按照 XML 规范所要求的格式编写，是对编写格式的要求。
    - 有效的 XML 文档指的是 XML 文档的内容满足 DTD 或 Schema 的约束，是对文档内容的要求。
    - 有效的 XML 文档必须是格式良好的。
- Schema的作用：使用 Schema 定义和验证 XML 文档；与DTD作用相同，用于规范和约束XML文档，用于验证XML文档的有效性；Schema逐渐成为XML应用的统一规范。
- XML解析器：XML解析器是XML和应用程序之间的一个软件组织，其目的是为应用程序从XML文件中解析出所需要的数据。


## 题型概述
填空  简答、 论述 阅读程序(HTML CSS JS)
