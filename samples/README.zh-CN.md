# JStachio 视图示例

[English](README.md) | [简体中文](README.zh-CN.md)

[hello.norm](hello.norm) 是 `micronaut.views.jstachio@3` 的单文件消费者。带注解的页面模型通过真实 Micronaut HTTP 响应渲染类型化列表，并对用户输入做 HTML 转义。服务仅监听 `127.0.0.1:18768`。

在仓库根目录运行：

```sh
norm run samples/hello.norm
```

在另一终端请求：

```sh
curl 'http://127.0.0.1:18768/sample/hello?name=Norm'
curl 'http://127.0.0.1:18768/sample/hello?name=%3Cscript%3E%26'
```

两次请求均返回 HTTP 200。第一个正文为 `<h1>Hello, Norm!</h1><ul><li>typed view</li><li>escaped text</li></ul>`；第二个以 `<h1>Hello, &lt;script&gt;&amp;!</h1>` 开头。按 Ctrl+C 停止服务。
