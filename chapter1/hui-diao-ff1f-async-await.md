# 回调？async/await

一个官网下的小栗子：

```js
const Koa = require('koa');
const app = new Koa();

// x-response-time

app.use(async (ctx, next) => {
  const start = Date.now();
  await next();
  const ms = Date.now() - start;
  ctx.set('X-Response-Time', `${ms}ms`);
});

// logger

app.use(async (ctx, next) => {
  const start = Date.now();
  await next();
  const ms = Date.now() - start;
  console.log(`${ctx.method} ${ctx.url} - ${ms}`);
});

// response

app.use(async ctx => {
  ctx.body = 'Hello World';
});

app.listen(3000);
```

大家可以直接复制代码到之前创建的文件里去运行。

在 Koa 的世界里，万物皆中间件，实际上一个 Koa 应用就是一个对象，这个对象包含一个中间件数组。

async/await需要注意以下几点：

* async 函数返回一个 Promise 对象，可以使用 then 方法添加回调函数

* await 命令后面，可以跟 Promise 对象和原始类型的值

* await 命令后面的 Promise 对象，运行结果可能是 rejected，所以最好把 await 命令放在 try...catch 代码块中。

更多async/await可以参看以下资料：

mdn：[https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/async\_function](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/async_function)

