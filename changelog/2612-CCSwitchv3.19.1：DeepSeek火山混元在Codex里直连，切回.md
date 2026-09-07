# CC Switch v3.19.1：DeepSeek 火山混元在 Codex 里直连，切回官方不再卡 401

> 原文链接：[https://www.sz003.com/ccswitchdt/2612](https://www.sz003.com/ccswitchdt/2612)

<p>用国产模型的 <a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a> 用户，以前总要过一道本地代理做协议转换，多一跳就多一处出问题的可能。7 月 31 日的 v3.19.1 把这层收掉了，DeepSeek、火山方舟 Coding Plan 和腾讯混元这三家，官方 Codex 文档都确认端点原生支持 Responses API，请求从此可以直连。这也是这个项目第一次一个版本删除的东西比新增的还多。</p>
<figure><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903115540_864357.png" alt="CC Switch v3.19.1 版本更新概念图" style="max-width:100%;height:auto"></figure>
<h2>三条国产网关直连</h2>
<p>DeepSeek 和火山方舟 Coding Plan 的既有预设，从 Chat 格式改成原生格式，供应商卡片上的需要路由标记和切换提示一并消失，请求不再过本地代理做协议转换。腾讯混元 TokenHub 是本版新加的预设，一上来就是原生直连。一个例外要单独说，DeepSeek V4 Pro 暂时还不能直连，厂商侧还没开通它的 Codex 集成，直连先用 V4 Flash，预设默认就是它。DeepSeek 用户还能拿到厂商自己发布的模型目录，apply_patch 这类自带能力和配套的提示词框架成套保留，不再被压成中性模板。</p>
<h2>切回官方 Codex 不再卡死</h2>
<p>此前从第三方供应商切回内置的官方条目，第三方的 key 会留在 auth.json 里，Codex 拿着它去请求官方端点，稳定 401。文件在，它又不退回自己的登录界面，应用里没有出路。这一版把这条尾巴收掉，登录界面能正常弹出来。顺带修了 Claude Desktop 的用量双算，自 3.18.0 起经本地网关的流量在看板里被记了两遍，现在明细行还在的日子会自动回到正确数字，不用手动重建。</p>
<h2>别的尾巴一起收</h2>
<p>Grok Build 从设置页升级只报 os error 2 的问题，根子是 npm 分发时图形界面启动的应用看不到 node，已修。手动把 API 格式改成 OpenAI Chat 或 Anthropic 的 Grok Build 供应商，开启接管的请求会打到一个没注册的路由直接 404，现在一起处理了，请求缓存键注入也恢复正常。8 个此前一直按 $0 记账的模型补上内置定价，界面文案修正了 39 处语言问题，繁体中文那块半英文的面板也补全了。</p>
<h2>要不要升</h2>
<p>这一版是收尾版本，没有数据库迁移。在 DeepSeek 和官方订阅之间来回切的用户收益最大，<a href="https://www.sz003.com/ccswitchdt" target="_blank" rel="noopener">CC Switch</a> 按供应商整段快照还原配置，这是它和厂商一键脚本最实际的区别。用 V4 Pro 的用户再等等厂商侧开通。</p>

---

原文链接：[https://www.sz003.com/ccswitchdt/2612](https://www.sz003.com/ccswitchdt/2612)
