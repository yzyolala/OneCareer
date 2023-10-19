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

# Nodemon

**Nodemon** 是一个实用的工具，主要用于开发Node.js应用程序。其主要功能是监控你的应用程序中的任何更改并自动重启服务器。这样，开发者就不必每次修改代码后手动停止并重新启动应用程序。

## 主要特点：

1. **实时监控**：当你保存文件时，它会自动检测文件更改并重新启动应用程序。
2. **不需要更改任何代码**：nodemon是一个命令行工具，所以你不需要在你的应用程序中做任何特定的修改来使用它。
3. **忽略特定文件或目录**：你可以配置nodemon来忽略特定文件或目录的更改，这样它就不会因为不相关的文件更改而触发重启。
4. **支持多种文件类型**：默认情况下，nodemon会监视.js、.coffee和.litcoffee文件，但你可以通过配置来监视其他类型的文件，例如.html、.css等。
5. **集成多种工具**：nodemon也支持与其他工具（如debuggers）一起使用，为开发者提供更流畅的开发体验。
   
> 在你的start脚本中，使用nodemon启动app.js会确保，每当你对app.js或其任何依赖进行更改并保存时，应用程序都会自动重新启动，从而为你提供即时的反馈。这大大加速了开发过程，因为你不再需要手动停止并重启服务器。

---

# Husky

**Husky** 是一个npm包，它可以让开发者轻松地设置和使用 Git hooks。Git hooks 是在 Git 仓库中的特定操作（例如 commit、push）触发的脚本。这些脚本可以帮助你自动执行一些任务，如代码风格检查、单元测试、linting等，从而确保只有满足特定条件的代码能被提交或推送到仓库。

## 主要特点：

1. **简化 Git hooks 的设置**：通过简单的配置，你可以为你的项目设置特定的 Git hooks。
2. **与 npm/yarn 脚本集成**：你可以在 package.json 中直接配置 husky，与其他npm/yarn脚本协同工作。
3. **支持多种Git hooks**：包括 pre-commit、post-commit、pre-push 等，允许在不同的 Git 操作前后运行自定义脚本。
4. **与 linting 和测试工具集成**：常见的用例是在 pre-commit hook 中运行 linters（如 ESLint、Prettier）或测试工具，以确保不会提交不符合代码规范或失败的测试的代码。
5. **跨平台**：无论是在Linux、Mac还是Windows上，husky都能正常工作.

> 在你的 prepare 脚本中，husky install 通常用于设置 husky 的 Git hooks。这样，当其他开发者克隆项目并安装依赖时，他们也会自动获得相同的 Git hooks 设置，从而确保代码的一致性和质量。

---

# Git, Git hooks, 和 GitHub 

## Git：

- 是一个开源的版本控制系统，用于跟踪文件的更改、合并代码和协同开发。
- 它是命令行工具，但也有图形界面的客户端。
- Git可以在本地工作，不依赖于任何中央服务器或在线服务。

## Git hooks：

- Git hooks 是 Git 的一个特性，允许开发者为特定的 Git 事件（如提交、推送等）挂载脚本。当这些事件发生时，相关的脚本会自动执行。
- 这些脚本可以在你提交代码前进行代码质量检查、运行测试、通知其他工具等。
- Git hooks 是本地的，通常存储在 .git/hooks 目录中。

## GitHub：

- GitHub 是一个基于 Git 的代码托管平台。它使开发者可以在线存储、分享和协作开发代码。
- 除了代码托管，GitHub 还提供了一系列的工具和特性，如代码审查、项目管理、自动化操作（如 GitHub Actions）等。
- 虽然 GitHub 提供了自己的 "webhooks" 和 "Actions" 功能来进行自动化，但它们是基于

