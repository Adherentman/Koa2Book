# 路由

首先我们肯定要实现页面间的跳转，用过Express的肯定会觉得这还不简单吗！

那么我们在Koa先用原生的实现一次：

```js
const navigation = (ctx) => {
  if(ctx.request.path === '/') {
    ctx.response.body = '<a href="/koa2">点我</a>'
  }
  if(ctx.request.path === '/koa2'){
    ctx.response.body = '<h1>Koa2小书</h1>'
  }
}
app.use(navigation);
```

![](/assets/Snip20180123_2.png)![](/assets/Snip20180123_3.png)

那么肯定觉得很烦吧这样。我们每次一个路由都要去判断一次去写一次，所以我们只能用路由的中间件。

