# 1. Apifox = Postman + Swagger + Mock + JMeter

**Swagger**: 通过良好的API设计，帮助前端和后端工程师并行开发，避免了顺序等待的模式，使得前端可以在后端完全开发完成之前就开始工作（帮助前端工程师后端工程师避免顺序锁死的开发模式，只要我们的api design设计好，前端不用等后端开发完才能继续开发了）。

**Mock**: 它提供了模拟请求和生成虚拟数据的功能，使前端能够在后端实际提供数据之前测试和开发。

**JMeter**: 用于进行各种测试，包括压力测试和质量测试，以确保API的稳定性和性能。这有助于提前发现和解决潜在的问题，确保API在生产环境中表现良好。

# 2. Backend Dev Environment Setup

- Install VS Code
- Install Node.js
- Install Prettier, Eslint, and Gitlens (download from the "Explore" section)
- Install Git
- Install dev dependencies: `npm install --save-dev eslint prettier lint-staged husky nodemon`
- **Prettier & pretty-quick**: Code formatter
- **Eslint**: JavaScript代码检查工具
- **Husky**: 简化Git钩子操作的工具，让其变得轻松愉快

# 3. 配置

**ESlint**:Npm eslint --init
```javascript
{
 "env": {
 "browser": true,
 "es2021": true
 },
 "extends": 
["eslint:recommended"]
}
```
**Prettier**:
● add a .prettierrc.json file
```javascript
{
 "bracketSpacing": true,
 "semi": true,
 "singleQuote": true,
 "trailingComma": "all",
 "printWidth": 80,
 "tabWidth": 2
}
```
● To check out all the available options, head over to the Prettier Documentation. ● Also add a .prettierignore file to your project root to ignore files
```javascript
package-lock.json
yarn.lock
node_modules
# any other unwanted files 
or folders
```
**Husky**:
确保您已经正确安装了 husky，可以使用以下命令安装：

npm install husky --save-dev
运行以下命令来初始化 husky 钩子：

npx husky install
这将创建 .husky 文件夹并设置 Git 钩子。

然后，您可以使用以下命令来添加一个预定义的钩子，比如 pre-commit 钩子：

npx husky add .husky/pre-commit "npm test"
这将在 .husky 文件夹中创建一个 pre-commit 钩子脚本，该脚本会在每次提交前运行 npm test 命令

在pre-commit hook中加入：npx pretty-quick



