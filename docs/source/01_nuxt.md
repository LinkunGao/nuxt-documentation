# Nuxt.js

See: https://nuxtjs.org/docs/get-started/installation
Nuxt.js 是一个基于 Vue.js 的通用应用框架。
通过对客户端/服务器端基础架构的抽象组织，Nuxt.js 主要关注的是应用的 <font color="#006600">UI 渲染</font>。

优点：

- 基于 Vue.js
- 自动代码分层
- 服务器端渲染
- 强大的路由功能，支持异步数据
- 静态文件服务
- ES6/7 语法支持
- 打包和压缩 JS 和 CSS
- HTML 头部标签管理
- 本地开发支持热加载
- 集成 ESLint
- 支持各种样式预处理器：SASS/LESS/Stylus 等等

## Start a new nuxt.js project

- 初始化项目

```bash
    npm init nuxt-app nuxt-demo
    yarn dev
```

## 在 package.json 文件中配置端口

```bash
    "scripts":{...},
    "config": {
        "nuxt": {
        "host": "127.0.0.1",
        "port": "3999"
        }
    },
```

## 全局添加 css

```bash
        1. 在assets文件夹中新建一个css文件夹，在css文件夹下新建一个css文件
        2. 在nuxt.config.js配置文件下：
            head:{...},
            css:[''],
```