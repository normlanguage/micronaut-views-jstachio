# JStachio views samples

[English](README.md) | [简体中文](README.zh-CN.md)

[hello.norm](hello.norm) is a single-file consumer of `micronaut.views.jstachio@2`. Its annotated page model renders a typed list and escapes user-supplied text through a real Micronaut HTTP response. The server binds only to `127.0.0.1:18768`.

From the repository root, run:

```sh
norm run samples/hello.norm
```

In another terminal:

```sh
curl 'http://127.0.0.1:18768/sample/hello?name=Norm'
curl 'http://127.0.0.1:18768/sample/hello?name=%3Cscript%3E%26'
```

Both return HTTP 200. The first body is `<h1>Hello, Norm!</h1><ul><li>typed view</li><li>escaped text</li></ul>`; the second starts `<h1>Hello, &lt;script&gt;&amp;!</h1>`. Stop the server with Ctrl+C.
