# koa-router使用

这是用的比较多的一个路由，而且还是比较推荐的。

## 安装

> npm install koa-router
>
> yarn add koa-router

## 使用

我这里上的是typescript版和js版没啥差别：

```typescript
import * as Koa from 'koa';
import * as koaRouter from 'koa-router';


const app = new Koa();

const router = new koaRouter();

const port: number = 8088;

router.get('/404', async (ctx) => {
  ctx.body = '404!!!'
});

// 加载koa路由中间件
app.use(router.routes()).use(router.allowedMethods());

app.listen(port);
console.log("Server is running at port " + port );

```



