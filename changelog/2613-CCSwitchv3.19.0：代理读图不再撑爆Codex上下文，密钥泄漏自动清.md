# CC Switch v3.19.0：代理读图不再撑爆 Codex 上下文，密钥泄漏自动清洗

> 原文链接：[https://www.sz003.com/ccswitchdt/2613](https://www.sz003.com/ccswitchdt/2613)

<p>在代理下读图，曾经是个吞 token 的无底洞。图片会被序列化成工具文本再上送，按纯文本计费，膨胀近 9000 倍，一张截图就能吃掉 10 万加 token。两三张图就能把 <a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a> 会话卡死在 400 报错上，跑 UI 评审、截图比对的活儿几乎没法用。</p>
<figure><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903115540_755794.png" alt="CC Switch v3.19.0 版本更新概念图" style="max-width:100%;height:auto"></figure>
<p>7 月 30 日发布的 <a href="https://www.sz003.com/ccswitchdt" target="_blank" rel="noopener">CC Switch</a> v3.19.0，主线是让你更放心。头一件事就是修这个读图问题，跟着是一轮集中式安全加固。</p>
<h2>读图还原原生格式</h2>
<p>所有转换桥现在把图片还原成原生格式再上送，文件与音频在两条 Chat 桥上一并支持。真实测试里，同一轮回放从 8.5 万 token 降到约 1.2 万，缓存命中率 99%。修完以后，跑设计稿评审这类重贴图场景，Codex 会话不再动不动撑爆，本地代理这条路才算真正走得通。</p>
<h2>两条要你动手的安全项</h2>
<p>集中式加固里有两条需要用户花一分钟确认。一是 Gemini 供应商的密钥泄漏，通用配置共享片段此前会把 GOOGLE_API_KEY 这类凭据复制进每个使用它的供应商，本版关闭这条路径并在升级后自动清洗，凡是进过共享片段的密钥都应视为已暴露，先轮换再重填。二是 ccswitch:// 导入链接的确认框，此前可能显示不出即将写入的命令，现在把要执行的命令和每一项参数完整列出来，URL、环境变量也逐条展示，凭据类值脱敏，高危值高亮，用量脚本默认以禁用状态导入。曾打开过来源不明导入链接的建议核对一次。</p>
<h2>更省心的两件事</h2>
<p>模型定价可以交给 models.dev 自动维护，开关默认关闭，开启后启动时自动刷新所选模型的价格，手工改价会记进专门文件，重建数据库也不丢。应用内更新改走 dl.ccswitch.io 镜像，GitHub 访问不畅也能顺利升级，minisign 签名校验不变，镜像本身不被信任。Grok CLI 官方登录模式的用量也进看板了，SuperGrok 订阅余量直接显示在供应商卡片上，fork 密集的 Codex 用量历史导入也明显提速。</p>
<h2>要不要升</h2>
<p>Gemini 用户升级后记得先轮换密钥再重填，这是本版唯一需要动手的安全动作。重度贴图用户不用犹豫，读图 token 从 8.5 万降到 1.2 万的差距，跑几轮活就值回升级成本。</p>

---

原文链接：[https://www.sz003.com/ccswitchdt/2613](https://www.sz003.com/ccswitchdt/2613)
