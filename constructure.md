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

```javascript
{
  "name": "class1",                                       // 项目名称为"class1"
  "version": "1.0.0",                                     // 项目版本为1.0.0
  "description": "class 1",                               // 项目描述为"class 1"
  "main": "index.js",                                     // 项目的主入口文件为"index.js"
  "scripts": {                                            // npm脚本定义
    "prepare": "husky install",                           // prepare脚本，用于安装husky
    "start": "npm install && nodemon app.js"              // start脚本，用于安装npm依赖并使用nodemon启动app.js
  },
  "author": "",                                           // 项目作者信息为空
  "license": "ISC",                                       // 项目使用的许可证为ISC
  "dependencies": {                                       // 项目的生产依赖
    "aws-sdk": "^2.1455.0",                               // AWS的JavaScript SDK，用于与AWS服务交互
    "bcrypt": "^5.1.1",                                   // 用于密码哈希和比较的库
    "body-parser": "^1.20.0",                             // 用于解析请求体的中间件
    "cognito-express": "^3.0.3",                          // 用于集成Amazon Cognito和Express.js的库
    "cors": "^2.8.5",                                     // 用于处理跨域请求的中间件
    "date-and-time": "^3.0.3",                            // 日期和时间处理库
    "dd-trace": "^4.16.0",                                // DataDog的APM跟踪库
    "express": "^4.18.2",                                 // 一个流行的Web服务器框架
    "express-rate-limit": "^6.3.0",                       // 用于Express应用的速率限制中间件
    "express-validator": "^7.0.1",                        // 用于Express应用的请求验证中间件
    "mongoose": "^7.5.4",                                 // 用于MongoDB的对象数据模型(ODM)库
    "mongoose-paginate-v2": "1.4.1",                      // 为Mongoose模型提供分页功能的插件
    "multer": "^1.4.5-lts.1"                              // 用于处理multipart/form-data的中间件，主要用于上传文件
  },
  "devDependencies": {                                    // 项目的开发依赖
    "eslint": "^8.49.0",                                  // JavaScript的静态代码检查工具
    "husky": "^8.0.3",                                    // 用于管理git钩子的工具，常用于pre-commit或pre-push操作
    "nodemon": "^3.0.1",                                  // 用于自动重新加载代码更改的工具，主要用于开发时
    "prettier": "^3.0.3",                                 // 代码格式化工具
    "prettier-quick": "^0.0.5"                            // 快速运行Prettier的工具，只格式化更改的文件
  }
}

```

nodemon是一个实用的工具，主要用于开发Node.js应用程序。其主要功能是监控你的应用程序中的任何更改并自动重启服务器。这样，开发者就不必每次修改代码后手动停止并重新启动应用程序。

以下是nodemon的主要特点：

实时监控：当你保存文件时，它会自动检测文件更改并重新启动应用程序。
不需要更改任何代码：nodemon是一个命令行工具，所以你不需要在你的应用程序中做任何特定的修改来使用它。
忽略特定文件或目录：你可以配置nodemon来忽略特定文件或目录的更改，这样它就不会因为不相关的文件更改而触发重启。
支持多种文件类型：默认情况下，nodemon会监视.js、.coffee和.litcoffee文件，但你可以通过配置来监视其他类型的文件，例如.html、.css等。
集成多种工具：nodemon也支持与其他工具（如debuggers）一起使用，为开发者提供更流畅的开发体验。
在你的start脚本中，使用nodemon启动app.js会确保，每当你对app.js或其任何依赖进行更改并保存时，应用程序都会自动重新启动，从而为你提供即时的反馈。这大大加速了开发过程，因为你不再需要手动停止并重启服务器。
