# Koa2介绍

官网，Koa --- 基于Node.js平台的下一代Web开发框架。

其实就是Express的下一代吧。它是有Express原班人马来打造的，致力于成为一个更小、更富有表现力、更健壮的 Web 框架。

## 安装

Koa2 依赖的Node版本为 node v7.6.0 或者 更高版本。

我则是用：

> $ nvm install 9
>
> $ nvm use 9
>
> $ yarn add koa
>
> 或者可以：
>
> $ nvm install 9
>
> $ nvm use 9
>
> $ npm install koa

```js
//创建文件夹
$ mkdir example-koa
$ yarn init/npm init

//安装koa
$ yarn add koa
```

### 不变的Hello World

```js
const Koa = require('koa');
const app = new Koa();

const port = 8888;
app.use( async(ctx) => {
    ctx.body = "Hello World !"
})

app.listen(port);
console.log("Server is running at port " + port )
```

### 跑程序！

```
node index.js
```

我们访问http:localhost:8888 就能见到`Hello World! `啦！！

