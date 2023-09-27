# 环境搭建指南

## 1. 检查 Node.js 版本

确保您的 Node.js 版本是14或以上。在终端中输入以下命令来查看当前版本：

```bash
node -v
```

## 2. 安装 Watchman

Watchman 是一个可以监听本地文件变化的工具，用于支持 React Native 的热重载功能（在本地代码 ⽂件变化后，相应的React Native程序也会⾃动重新加载）

使用以下命令安装 Watchman：

```bash
brew install watchman
```

## 3. 安装 Ruby

确保您的 Ruby 版本是2.7.5。如果不是，按照以下步骤进行安装和配置：

### 安装 rbenv:

如果您还没有安装 `rbenv`，可以使用 Homebrew 来安装它：

```bash
brew install rbenv
```

### 初始化 rbenv:

初始化 `rbenv` 并将其添加到您的 shell 配置文件中：

```bash
rbenv init
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc
```

**注意**：如果您使用的是 bash 而不是 zsh，请将上述命令中的 `~/.zshrc` 替换为 `~/.bash_profile`。

### 安装 Ruby 2.7.5:

使用 `rbenv` 安装 Ruby 2.7.5：

```bash
rbenv install 2.7.5
```

### 设置 Ruby 版本:

将全局 Ruby 版本设置为 2.7.5：

```bash
rbenv global 2.7.5
```

### 验证 Ruby 版本:

验证您的 Ruby 版本：

```bash
ruby -v
```

**关于 Ruby**: Ruby 是一种动态、面向对象的编程语言，由 Yukihiro Matsumoto（也被称为 Matz）在1990年代在日本设计和开发。Ruby 特别注重简洁和生产效率，拥有优雅的语法。

## 4. 安装 Bundler

`Bundler` 是一个管理 Ruby 依赖的工具。

使用以下命令安装 Bundler：

```bash
gem install bundler
```

如果遇到写入权限的错误，请使用 `sudo`：

```bash
sudo gem install bundler
```


