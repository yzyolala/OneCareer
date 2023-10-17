# MEETFOOD 项目结构

## 📁 目录 & 📄 文件

### **.ebextensions**
- 包含配置，主要用于 Amazon Elastic Beanstalk 的部署。

### **.husky/**
- 由 Husky 管理，用于控制 git hooks，确保提交或推送的代码达到预定标准。

### **.gitignore**
- 列出 git 应当忽略的文件或目录。

### **config**
- 常见的配置文件目录。
  - **production.json**: 生产环境的配置文件。

### **controllers**
- 包含处理应用逻辑的控制器。
  - **user.js**: 处理与用户相关的操作。
  - **videoPost.js**: 处理与视频发布相关的操作。

### **middleware**
- 介于请求和响应之间的软件。
  - **is-auth.js**: 可能是用于检查用户是否认证的中间件。

### **models**
- 定义应用的数据结构。
  - **user.js**: 用户的数据结构。
  - **videopost.js**: 视频发布的数据结构。

### **node_modules**
- 包含项目的所有依赖项。

### **routes**
- 定义应用的路由。
  - **user.js**: 与用户相关的路由。
  - **videopost.js**: 与视频发布相关的路由。

### **uploads**
- 可能用于存储用户上传的文件。

### **util**
- 包含实用工具或助手函数。
  - **aws-cognito.js**: 与 AWS Cognito 服务相关的函数。
  - **aws-s3.js**: 与 AWS S3 服务相关的函数。
  - **constants.js**: 应用的常量。
  - **path.js**: 可能与文件路径处理相关的函数。

### **app.js**
- 应用程序的主入口文件。

## 📄 其他文件

- **99datadog.config**: 可能是 Datadog 的配置文件，Datadog 是一个监控和分析平台。
- **husky.sh**: 与 Husky 相关的脚本。
- **app.zip**: 应用的压缩版本，可能用于部署。
- **buildspec.yml**: 可能与 AWS CodeBuild 相关的配置文件。
- **package-lock.json**: 锁定每个依赖的版本，确保其一致性。
- **package.json**: 包含项目元数据和依赖列表。
