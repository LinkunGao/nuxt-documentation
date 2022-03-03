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

- 貌似没有成功

```bash
        1. 在assets文件夹中新建一个css文件夹，在css文件夹下新建一个css文件
        2. 在nuxt.config.js配置文件下：
            head:{...},
            css: ["~assets/css/normalize.css"],
```

## 在 nuxt.config.js 下配置 webpack 的 loader

```bash
    head:{...},
    build:{
        loaders:[
            {
                test:/\.(png|jpe?g|gif|svg)$/,
                loader:"url-loader",
                query:{
                    limit:10000,
                    name:'img/[name].[hash].[ext]'
                }
            }
        ]
    },
```

## 路由 router

- 在 pages 文件夹下，建两个子文件夹，about，news
- 在这两个文件夹下分别创建 index.vue 文件
  ```bash
      <template>
          <div>
              <h2>About Index page</h2>
              <ul>
              <li><a href="/">Home</a></li>
              </ul>
          </div>
      </template>
  ```
- 在 pages 文件夹下的 index.vue 文件中更改如下代码：

```bash
        <template>
            <div>
                <ul>
                <li><a href="/">HOME</a></li>
                <li><a href="/about">About</a></li>
                <li><a href="/news">News</a></li>
                </ul>
            </div>
        </template>
```

- 在 nuxt 环境下，推荐使用的是 nuxt-link 标签，所以我们要把 a 标签替换为 nuxt-link 标签

```
    <template>
            <div>
                <ul>
                <li><nuxt-link :to="{name:'index'}">HOME</nuxt-link></li>
                <li><nuxt-link :to="{name:'about'}">About</nuxt-link></li>
                <li><nuxt-link :to="{name:'news'}">News</nuxt-link></li>
                </ul>
            </div>
        </template>
```

- nuxt-link 标签
  - name 是路由，填写具体的文件或文件夹名
  - params 是跳转是的传参
  ```bash
      <nuxt-link :to="{ name: 'news', params: { newId: 3306 } }">
        News
      </nuxt-link>
  ```
  - 在 news/index.vue 下接收参数：
  ```bash
        <p>NewsID:{{$route.params.newsId}}</p>
  ```
- nuxt 动态路由

  - 在对应的文件夹下创建以 \_ 开头的文件，
    例如在 news 文件夹下创建 \_id.vue 作为接收动态路由的文件。
    ```
    // news-id 中的 - 对应的是 _id.vue 中的 _
        <li>
            <nuxt-link :to="{ name: 'news-id', params: { id: 123 } }">
                new-1
            </nuxt-link>
        </li>
        <li>
            <nuxt-link :to="{ name: 'news-id', params: { id: 12344 } }">
                new-2
            </nuxt-link>
        </li>
    ```

- css transition 动画

  - 在 css 中添加：

    ```bash
        .page-enter-active,
        .page-leave-active {
            transition: opacity 2s;
        }

        .page-enter,
        .page-leave-active {
            opacity: 0;
        }

        .test-enter-active,
        .test-leave-active {
            transition: all 2s;
            font-size: 12px;
        }

        .test-enter,
        .test-leave-active {
            opacity: 0;
            font-size: 40px;
        }
    ```

    - page 对应的是全局动画，test 是局部动画需要引用

    ```
        // 在 about 中引用，需要在 about/index.vue 的 <script></script>中添加
        <script>
            export default {
                transition: "test",
            };
        </script>
    ```

- nuxt 默认模版

  - 首先根目录下创建 app.html, nuxt 会自动把它当作为默认模版

  ```
      <!DOCTYPE html>
          <html lang="en">
          <head>
              {{HEAD}}
          </head>
          <body>
              <p>Skycoco Blog</p>
              {{APP}}
          </body>
          </html>
  ```

  更改模版之后，必须重启服务器

  - 在 layout 下定义模版布局

- add json
  see: https://myjson.dit.upm.es/
