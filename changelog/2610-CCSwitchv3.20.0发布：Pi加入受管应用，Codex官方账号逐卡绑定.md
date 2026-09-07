# CC Switch v3.20.0 发布：Pi 加入受管应用，Codex 官方账号逐卡绑定

> 原文链接：[https://www.sz003.com/ccswitchdt/2610](https://www.sz003.com/ccswitchdt/2610)

<p><a href="https://www.sz003.com/ccswitchdt" target="_blank" rel="noopener">CC Switch</a> 能管的工具又多了一个。8 月 18 日发的 v3.20.0 把 Pi 收进来，成了第九个受管应用。这事不是多一个开关那么简单，Pi 从供应商到提示词再到会话用量，整套都能在这一处管了。手里同时握着 <a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a>、Claude Code 和 Pi 的用户不在少数，以前要分头去几个目录里配，现在能统一进一个界面。</p>
<figure><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903114635_519407.png" alt="CC Switch v3.20.0 版本更新概念图" style="max-width:100%;height:auto"></figure>
<h2>Pi 接入带了个明白的边界</h2>
<p>Pi 是拿累加模式接的，和 OpenCode、Hermes 同类，多供应商共存，启用与否等于它的键在不在 models.json 里。供应商表单照 Pi 原生 schema 做成结构化编辑器，内置 58 个预设和 57 个模型的能力目录。边界划得很清楚，CC Switch 绝不把 Pi 内置供应商物化进 models.json，绝不读写 Pi 的 auth.json，也不碰默认供应商和默认模型，登录和选模型还是 Pi 自己的事。用量看板新增独立来源，逐模型记下 token 消耗，成本、错误和中断轮次分开统计。工具管好切换和统一入口，不越权动应用的私账，这个分寸拿捏得舒服。</p>
<h2>Codex 官方账号能多开，一张卡绑一个</h2>
<p>Codex 侧补的是账号管理的课。认证中心现在能存任意多个 ChatGPT 登录，新建官方供应商卡时，直接在下拉框里选一个已授权的账号完成绑定，也可以照旧加一张不绑账号的空卡，跟着 codex CLI 本地登录走。切换进绑定卡会把完整的令牌包写进 auth.json，裸 codex CLI 也拿这个账号跑，令牌过期还能自行续期。官方特意退出了自动故障转移，重试永远不会把账单记到另一个账号头上。账号开销是实打实的真金白银，串一次账比慢一点烦人得多。</p>
<h2>WebSearch 通了，Windows 的账也还了</h2>
<p>Claude Code 的内置 WebSearch 在 GPT 路由下终于能用，搜索在上游执行，结果带引用返回，次数照常进用量。v3.19.2 在 WSL 路径上配置无法更新和切换的坑填上了，CI 从此跑在真实 WSL2 上。Windows 版本检测大修，注册表 PATH 合并，独立安装器目录，PATH 默认项，几个来源一次扫全。Codex 模型目录支持逐模型声明思考档位，各家预设按官方文档预填真实档位，DeepSeek、火山方舟这类都有据可依，智谱 GLM 的关闭思考选项也终于选得到了。模型下拉全换成可输入过滤的组合框，几百个模型直接搜名字。备份链路加固，SQL 逐值保真往返，截断文件导入前直接拒绝，恢复先在暂存库整体校验。</p>
<h2>升级提醒</h2>
<p>这版带数据库迁移，v16 升 v17，升级前自动备份。整版 69 个提交、284 个文件，Pi 用户和 Codex 多账号用户都值得升。下载只认官网 ccswitch.io 和 GitHub Releases，CC Switch 完全免费开源，任何收费渠道都是冒牌，遇到直接绕开。</p>

---

原文链接：[https://www.sz003.com/ccswitchdt/2610](https://www.sz003.com/ccswitchdt/2610)
