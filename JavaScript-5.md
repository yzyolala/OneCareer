## AWS:

| 层级（Service Layer） | 服务类型（Type of Service） | 示例（Examples）               |
|---------------------|----------------------------|-----------------------------|
| 基础设施（IaaS）      | 虚拟服务器                  | Amazon EC2, Google Compute Engine (GCE), Microsoft Azure, Rackspace, Digital Ocean, Linode |
|                     | 块级存储                    | Amazon EBS (part of EC2 service) |
|                     | 网络设施                    | Amazon VPC, Azure Virtual Network |
|---------------------|----------------------------|-----------------------------|
| 平台（PaaS）         | 应用部署和管理平台            | AWS Elastic Beanstalk, Heroku, Google App Engine, Microsoft Azure |
|                     | 认证服务和访问管理            | AWS IAM, Azure Active Directory |
|                     | 无服务器计算                | AWS Lambda, Google Cloud Functions, Azure Functions |
|                     | 消息队列服务                | AWS SQS, Google Cloud Pub/Sub, Azure Queue Storage |
|                     | 数据库服务                  | Amazon RDS, Google Cloud SQL, Azure SQL Database |
|---------------------|----------------------------|-----------------------------|
| 应用软件（SaaS）     | 邮件服务                    | Amazon WorkMail, Gmail, Outlook |
|                     | 代码托管和协作服务          | AWS CodeCommit, GitHub, GitLab |
|                     | 虚拟桌面服务                | Amazon WorkSpaces, Microsoft Office 365 |
|                     | 机器学习服务                | AWS Rekognition, Google AI Platform |
|                     | 文件存储和协作              | Dropbox, Google Drive |
|                     | 会议和通讯                  | Zoom, Microsoft Teams |




云计算的类型

- 基础设施即服务（IaaS）
  - 为云计算提供构建模块
  - 提供网络、计算机、数据存储空间
  - 最高水平的灵活性
  - 与传统的本地 IT 有易于理解的对应关系

- 平台即服务（PaaS）
  - 免除了组织管理底层基础设施的需要
  - 专注于应用程序的部署和管理

- 软件即服务（SaaS）
  - 由服务提供商运行和管理的完整产品

## Regions，Availability Zones,edge Locations区别

地域（Regions）:

地域是云服务提供商网络中的一个主要地理区域。
每个地域通常包含多个可用性区域。
地域设计用来优化地理分布，使用户可以选择靠近自己或客户的数据中心，从而减少延迟，并满足数据驻留要求。

可用性区域（Availability Zones, AZs）:

可用性区域指的是位于特定地域内的一组或多组数据中心。
它们彼此物理上分离，但通过低延迟网络连接。
可用性区域为构建高可用性应用提供了基础，因为它们之间的冗余可以防止单点故障影响整个服务。

边缘位置（Edge Locations）:

边缘位置通常是指那些靠近最终用户的网络点，用来分发缓存内容。
它们是内容分发网络（CDN）的一部分，目的是减少数据传输到用户设备的距离，从而加快加载速度和提高性能。
边缘位置不是用于部署主要计算基础设施，而是更多关注于提升数据传输的效率和速度。
总的来说，地域是最大的地理单元，包含多个可用性区域；可用性区域是构建在地域内的，保证服务可用性和容灾的数据中心集群；边缘位置则更小、更分散，主要用于数据缓存和快速分发。

## Amazon EC2（Elastic Compute Cloud)

是AWS提供的虚拟服务器服务。它允许用户快速部署和管理虚拟机，提供可伸缩的计算能力。EC2支持多种配置选项，并能与其他AWS服务集成，以实现高效、安全的云计算解决方案。

## AWS S3

**主要功能：**
- 对象存储：以对象形式存储大量数据。
- 桶（Buckets）：数据的容器，可配置访问权限和其他设置。
- 高可用性和持久性：非常适用于关键数据的备份和存储。

**主要用途：**
- 数据备份和存档：存储数据库备份和应用日志。
- 内容分发和静态网站托管：存储和分发网站的静态资源。
- 大数据分析：作为大数据解决方案的后端存储。
- 媒体存储：存储音频、视频和图像文件。
- 文件共享：通过预签名URL进行安全的文件共享。
- 应用程序资产：存储移动和桌面应用程序的用户数据。
- 灾难恢复：多地理位置的数据副本提供了灾难恢复能力。

**其他优点：**
- 高可扩展性
- 安全性
- 低成本

因为这些优点和灵活性，AWS S3被广泛应用于多种场景，从小型应用到大型企业解决方案。

## S3 Glacier

- 数据归档服务，适用于不太访问的数据
- 安全性、持久性和极低成本
- 支持静态和动态的SSL/TLS加密
- 数据检索通常需要好几个小时

## AWS Elastic Beanstalk（EB）

是一种平台即服务（PaaS）解决方案，让开发者能够快速部署和管理应用，无需关心底层基础设施。它支持多种编程语言，自动处理资源扩展和运维任务，且与其他AWS服务良好集成。

## DynamoDB (相当于亚马逊的mongodb)

- 完全托管的NoSQL数据库 
- 任意规模上实现低于10ms的低延迟，完全运行在SSD
- 支持文档和键值存储模式
- 非常适合移动、web、游戏、广告和 IOT

## RDS (相当于亚马逊的mysql)

- 关系型数据库托管服务
- 可以通过AWS控制台、RDS命令行和API进行调用
- 可扩展、支持自动冗余和备份
- 支持SQL、Oracle等数据

## Route53 (管理域名，类似于卖域名的网站)

是一种可用性高、可扩展性强的域名系统 (DNS) Web 云服务。它的目的是为开发人员和企业提供一种非常可靠且经济高效的方式，把人类可读的名称（如 www.example.com）转换为计算机用于互相连接的数字 IP 地址（如192.0.2.1），从而将最终用户路由到 Internet 应用程序。

## CloudFront（cdn服务）

- 内容交付Web服务，提供低延迟、高速和最低使用承诺的全球CDN业务
- 利用全球的边缘网络提供整个网站的访问，包括动态、静态、流媒体和交互式内容
- AWS上存储的文件生命周期策略

## API Gatway（API管理，类似middleware）

- 用于 restufl api 
- 完全托管的服务 
- 创建、发布、维护、监控和保护各种规模的API
- 可以接受和处理最大数十万个并发的API调用
- 支持包括流量管理、授权和访问控制、监控及API版本管理

## AWS CodePipeline 

是一个持续集成和持续交付（CI/CD）服务，可以自动化您的代码部署流程。这对于从源代码存储（如 GitHub）到 AWS 服务（如 Elastic Beanstalk、ECS、Lambda 等）的代码部署特别有用。

## AWS Cognito
 是一个面向客户端的身份服务，专门用于处理用户认证（Authentication）和授权（Authorization）。它简化了多种登录方式和身份提供商的管理，确保安全的用户访问和灵活的访问权限设置。同时还管理用户目录和访问令牌，使开发者能更容易地实现安全的用户访问和身份管理。

## AWS Certificate Manager（ACM）

是 Amazon Web Services（AWS）提供的一个管理 SSL/TLS 数字证书的服务。SSL（Secure Sockets Layer）和 TLS（Transport Layer Security）是用于在互联网上保护数据传输的加密协议。这些数字证书主要用于启用 HTTPS（超文本传输安全协议）连接，以保护网站和应用程序中的数据传输。

## APIdoc

apidoc 是一种用于生成API文档的工具。它可以提取源代码中的注释，并将其转换为易于理解和使用的API文档。这对于JavaScript开发人员来说非常有用，因为它可以帮助他们更快速、更准确地了解和使用不同的API接口。

**apidoc 的主要功能：**
- 从源代码中提取注释：apidoc可以扫描JavaScript源代码中的特定注释格式，例如JSDoc或JavaDoc，并提取其中的API信息。
- 生成API文档：apidoc可以将提取的注释转换为易于理解和使用的API文档。它支持多种输出格式，如HTML、PDF和Markdown等。
- 自定义文档样式：apidoc允许用户自定义文档样式，包括颜色、字体和布局等，以便与项目的整体风格保持一致。
- 支持多种标记语言：apidoc支持多种标记语言，如Markdown、AsciiDoc和reStructuredText等，以便用户可以根据自己的喜好选择适合的文档格式。
- 集成测试框架：apidoc可以与流行的JavaScript测试框架（如Mocha和Jasmine）集成，以便在生成文档时自动包含测试用例和结果。


## Async/Await

这是基于 Promise 的一种更现代和更简洁的异步编程方式。一个函数如果被声明为 async，那么它会隐式返回一个 Promise。我们可以在 async 函数内部使用 await 来暂停和恢复该函数的执行，直到 Promise 完成。例如：
```javascript
let asyncFunction = async () => {  
    let promise = new Promise((resolve, reject) => {  
        setTimeout(() => resolve(), 1000);  
    });  
  
    await promise;  
    console.log("Async function complete");  
};  
  
asyncFunction();
```

## CORS
CORS（Cross-Origin Resource Sharing，跨源资源共享）是一种安全特性，由浏览器实施，用于控制不同源（origin）的网页如何能够请求某个网站的资源。简单来说，它是一种允许或拒绝跨站请求的机制。

在没有设置 CORS 的情况下，Web 浏览器禁止从与当前页面不同的源加载资源，例如通过 AJAX 进行的 HTTP 请求。这是出于安全考虑，因为这样的请求可能泄露敏感信息或者执行恶意操作。
