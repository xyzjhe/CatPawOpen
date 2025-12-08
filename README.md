## CatPawOpen

[猫爪源协议文档参考](https://github.com/git8477/CatPawOpen)

本仓库是猫爪源的示例项目，将配置功能以网页的方式提供，并集成到源中，希望降低猫爪源的使用门槛

关键代码：
- `esbuild.js`：添加编译前端项目的插件，将页面产物编译进到最终的bundle中
- `src/index.js`：注册前端项目的路由，并监听0.0.0.0，允许局域网访问配置页面
- `src/website`：前端项目的实现

为了验证可行性，本仓库内集成了部分站源，几乎全部抄袭自其他仓库，感谢：道长、真心、奥秘

### 公参

| 参数 | 用途 |
|-------|:-----:|
| req / res | 请查看[fastify文档](https://fastify.dev) |
| req.server.config | index.config.js的配置内容 |
| req.server.db | [node-json-db](https://github.com/Belphemur/node-json-db)实例 |
| req.server.messageToDart | 调用App的action，[action清单](#) |
| req.server.address() | url、port |