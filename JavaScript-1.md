## Node.js 和 Express.js

- **Node.js** 是一项技术，用于在服务器上运行 JavaScript 代码，它使用了 V8 JavaScript 引擎。
- **Express.js** 是一个建立在 Node.js 上的 Web 应用程序框架，它简化了在 Node.js 上构建 Web 应用程序的过程。
- Node.js 是 Express.js 的运行环境，Express.js 则是一个更高级的抽象，用于简化 Web 应用程序的开发。
- Express.js 可以看作是在 Node.js 的基础上提供了更高级别的 API，使得开发 Web 应用程序更加容易和快速。
- 使用 Node.js 和 Express.js 可以构建完整的 Web 应用程序，包括处理路由、HTTP 请求、数据库访问、模板渲染等。Node.js 提供了运行环境，Express.js 提供了开发 Web 应用程序的框架。

## NPM

NPM (Node Package Manager) 是用于管理 Node.js 包的工具，您可以使用 `npm install packagename` 命令来安装包。

## SQL 和 NoSQL 的区别：

| 特点         | SQL                                     | NoSQL                                         |
|--------------|-----------------------------------------|-----------------------------------------------|
| 存储模型    | 表格（表）                               | 多种数据模型，包括文档型、键值对、列族、图形等  |
| 扩展性       | 垂直方向易扩展（通过增强硬件）          | 水平方向易扩展（跨多个服务器添加节点）       |
| 适用场景    | 高度结构化数据，不预期结构更改         | 快节奏、敏捷开发，数据一致性不是首要考虑问题  |
| 示例         | 银行                                    | 高交易负载的应用                             |

## MongoDB

MongoDB 是一种基于文档的非关系型数据库，可以跨平台运行。它基于集合（Collection）和文档（Document）的概念：

- **Collection** 是一组 MongoDB 文档，类似于关系数据库中的表格。
- **Document** 是一组键值对，具有动态模式，允许不同文档具有不同的字段集合和结构。

## MongoDB Atlas

MongoDB Atlas 是一个完全托管的云数据库服务，它处理了在云服务提供商（如 AWS、Azure 和 GCP）上部署、管理和维护 MongoDB 的复杂性。MongoDB Atlas 是在云中部署、运行和扩展 MongoDB 的最佳方式。

## 与数据库交互的两种常见方法：

- 使用数据库的本机查询语言（例如 SQL）。
- 使用对象数据模型（ODM）或对象关系模型（ORM），将数据表示为 JavaScript 对象，然后映射到底层数据库。

## Mongoose

Mongoose 是用于 Node.js 的 MongoDB 驱动和对象模型库，用于更轻松地管理和操作 MongoDB 数据库。下面是一个示例：

```javascript
const mongoose = require('mongoose');//引入Mongoose库
const Schema = mongoose.Schema;//定义Schema
//在这一步中，创建了一个名为"userTestSchema"的Mongoose Schema实例。这个Schema定义了两个字段，
//分别是"userName"和"firstName"。每个字段都有一个类型（type）属性，分别是String类型，用于存储字符串数据。
//此外，"userName"字段还具有一个"unique"属性，表示它的值在数据库中必须是唯一的，不允许重复。
const userTestSchema = new Schema({
    userName: {
        type: String,
        unique: true,
    },
    firstName: {
        type: String,
    },
});
//导出模型
module.exports = mongoose.model('UserTest', userTestSchema);
//通过调用mongoose.model方法，将"userTestSchema"编译成一个Mongoose模型，并将其导出。
//这个模型被命名为"UserTest"，并且它将用于在数据库中进行操作，例如创建、读取、更新和删除与"userTestSchema"相对应的文档。
```

## 中间件函数

中间件函数是在应用程序请求-响应循环中执行的功能性函数，通常用于处理 HTTP 请求。它们具有访问请求对象（`req`）和响应对象（`res`）的能力，并可以调用下一个中间件函数来继续请求的处理。中间件函数可以执行以下任务：

- **执行任何代码：** 中间件函数可以包含任何 JavaScript 代码，用于处理请求的逻辑。这可以包括验证、日志记录、身份验证等操作。

- **对请求和响应对象进行更改：** 中间件可以修改请求对象和响应对象，例如添加、删除或修改请求头、响应内容等。

- **终止请求-响应循环：** 中间件函数可以决定是否终止请求-响应循环，即不再调用后续中间件函数，通常用于处理错误或特殊情况。

- **调用堆栈中的下一个中间件函数：** 中间件函数通常使用名为 `next` 的变量来调用下一个中间件函数，以确保请求继续传递给下一个处理程序或中间件。

中间件是构建 Web 应用程序的重要组成部分，它们可以用于执行各种任务，从请求验证到路由处理和错误处理。它们提供了一种模块化和可重用的方式来构建强大的应用程序。


