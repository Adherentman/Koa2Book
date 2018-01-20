# Context

用过Express的都知道，它只有两个对象：一个为`Request`还有一个`Response`。那么在Koa中，多了一个对象为`Context`它将node中的`request`和`response`对象封装到单个对象中，为编写 Web 应用程序和 API 提供了许多有用的方法。

_每个_请求都将创建一个`Context`，并在中间件中作为接收器引用，或者`ctx`标识符：

```js
app.use(async ctx => {
  ctx; // 这是 Context
  ctx.request; // 这是 koa Request
  ctx.response; // 这是 koa Response
});
```

再看一段：

```js
app.use(async (ctx, next) => {
  await next();
  ctx.body = 'Hello World';  //这代表了response.body
});
```

所以正如官网所说的：

为方便起见许多上下文的访问器和方法直接委托给它们的`ctx.request`或`ctx.response`，不然的话它们是相同的。 例如`ctx.type`和`ctx.length`委托给`response`对象，`ctx.path`和`ctx.method`委托给`request`。



看了第二段代码我们可能对上面那句话好理解些。

