## Nodejs常见问题总结

#### 1.通过node读取文件，返回给前端二进制文件流，前端创建可下载的链接
服务端读取到文件流之后，需要设置返回的响应头。

```
// koa 

// 类型为二进制流
ctx.set('content-type', 'application/octet-stream')
// 前端会从 content-disposition 属性中读取下载链接显示的文件名
ctx.set('content-disposition','attachment;filename="test.xlsx"')
// 将 content-disposition 属性暴露出去
ctx.set('access-control-expose-headers', "*")
```


[Content-Disposition](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Disposition): 在常规的HTTP应答中，Content-Disposition 响应头指示回复的内容该以何种形式展示，是以内联的形式（即网页或者页面的一部分），还是以附件的形式下载并保存到本地。

[Access-Control-Expose-Headers](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Access-Control-Expose-Headers):响应首部 Access-Control-Expose-Headers 列出了哪些首部可以作为响应的一部分暴露给外部。如果不设置，默认情况下只暴露以下六种响应首部
 - Cache-Control
 - Content-Language
 - Content-Type
 - Expires
 - Last-Modified
 - Pragma


前端： todo ... 

