# CC Switch v3.20.1 适配 Codex 0.149：第三方切换 401 根治，Team 账号不再互相覆盖

> 原文链接：[https://www.sz003.com/ccswitchdt/2609](https://www.sz003.com/ccswitchdt/2609)

<p><a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a> 0.149 干了一件事，把不少人的切换习惯掀翻了：自定义 provider 不再从 <code>auth.json</code> 继承环境凭据。凡是按旧默认方式把密钥写进 <code>auth.json</code> 再切第三方供应商的，切完一跑就是 Missing API key，401 直接拍脸上。GitHub 上 issue #6744 把这个问题报得又准又细，官方也认，顺着这条线定下了整个版本的方向。</p>
<p>8 月 28 日发布的 <a href="https://www.sz003.com/ccswitchdt" target="_blank" rel="noopener">CC Switch</a> v3.20.1，就是来还这笔账的。</p>
<figure><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903114635_083632.png" alt="CC Switch v3.20.1 适配 Codex 0.149：第三方切换 401 根治，Team 账号不再互相覆盖" style="max-width:100%;height:auto"></figure>
<h2>切换从此只认 config，auth.json 退回本岗</h2>
<p>CC Switch 的应对不是打补丁，是换玩法。第三方切换整体改成 config-only，密钥写进供应商自己的 [model_providers.*] 配置表，字段叫 experimental_bearer_token，Codex 0.48 起就支持。auth.json 回归它本来的岗位，只放官方 ChatGPT 登录。以前用老格式攒下的配置，占用保留 id 的旧表，缺 name 字段的表，还有顶层 openai_base_url 的旧式路由，每次切换和接管都会自动修成可加载的形状。写之前还有一道预检，Codex 0.149 加载不了的组合会被点名拒绝，不再出现 CC Switch 提示切换成功、Codex 却起不来的局面。</p>
<h2>同一个 Team，账号各归各</h2>
<p>第二条硬账是账号打架。托管的 ChatGPT 账号以前拿 workspace ID 当主键，可这个 ID 标识的是工作区不是人。同一个 Team workspace 里两个人登录，后登录的会把先登录的令牌悄悄盖掉，供应商绑定也跟着指到最后一个登录的人，账单记到谁头上全凭运气。现在账号按本地身份建键，用 OIDC subject 当用户身份凭证，同一 workspace 的登录并存为独立账号行。接管路由下的请求还会核对绑定账号，真拿着另一名成员的登录态去跑，会得到明确的&#8221;请重启 Codex&#8221;报错，而不是被静默转发。老用户要做一件事：存量托管账号逐个去认证中心点一次重新登录，否则一直处于隔离状态。</p>
<h2>顺手的硬修复，还有扫描提速</h2>
<p>数据可靠性补了三处。编辑供应商保证必达 live 配置，崩溃残留的备份行不再劫持写入。Codex 编辑框显示自己这张卡的密钥，不再串染共享 auth.json 里别张卡遗留的 key。恢复备份不再把没有启用 prompt 的应用文件截断成空，手写的 CLAUDE.md、AGENTS.md 这类文件保住了。用量侧新增自动扫描会话记录的开关，大会话文件改成字节游标增量扫描，12 MB 的活跃文件从整读 6 秒降到 9 毫秒。</p>
<h2>升级提醒</h2>
<p>这版带数据库迁移，v17 升 v18，升级前自动备份，跑过新版再降级得还原备份。两件事要单独提。还在用 Codex 0.48 以前版本的用户注意，config-only 写进去的令牌字段老版本根本不读，该升 Codex 就升。另外网上已经有打着 CC Switch 旗号收费的假站，这个软件完全开源免费，官方渠道只有官网 ccswitch.io 和 GitHub Releases，让你充值、跟你要登录凭据的一律是冒牌。</p>
<p>要升级的直接去官网或 GitHub Releases 拿安装包，装完在认证中心把老账号重新登录一遍，就能继续正常切供应商了。</p>

---

原文链接：[https://www.sz003.com/ccswitchdt/2609](https://www.sz003.com/ccswitchdt/2609)
