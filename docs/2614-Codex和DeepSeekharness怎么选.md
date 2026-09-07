# Codex 和 DeepSeek harness 怎么选

> 原文链接：[https://www.sz003.com/jiaocheng/2614](https://www.sz003.com/jiaocheng/2614)

<p>我自己用 <a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a> 有一阵了，改代码、跑测试都靠它。最近老有人来问 Codex 和 DeepSeek harness 怎么选，我干脆把 harness 拉出来，跟 Codex 放一块比了七条。比完才回过味，这俩压根不该放一块比高下，不是一个层级的东西。</p>
<p>harness 这词我是比到一半才搞明白的。字面是马具，套到 AI 上，模型是马，agent 是骑手，harness 是中间那套鞍具。它装的是一整套 agent 运行时，不是某一个 agent，我之前也差点当它是智能体。</p>
<p><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903120910_977113.jpg" alt="harness 是智能体的载体：模型、harness、agent 三层关系" /></p>
<p>Codex 这边我熟，它是台装好的电脑，桌面、终端、沙箱、权限都配好了，我打开就能干活。harness 得自己配，接哪个模型、挂哪些工具，全自己来。</p>
<p><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/09/20260903120910_433608.jpg" alt="Codex 是装好的产品，DeepSeek harness 是能自己拼的底座" /></p>
<p>上手这块反差最大。我用 Codex 从来不用操心环境，选个项目说清任务，它自己就去读代码改文件了。harness 我照着文档捋了半天，模型、插件、profile、工具、工作区这些概念一个没落下，才勉强理清。</p>
<p>模型自由度是我最花时间的一条。Codex 走 OpenAI 的模型，好处是省心，代价是我早想换个模型试试，一直懒得折腾。harness 不挑模型，DeepSeek、OpenAI、Anthropic 都接，可模型没选好，工具调用出错、任务打转，得自己兜。</p>
<p>扩展这事我一开始也听岔了。都说 Codex 封闭、harness 开源，我后来查了才知道 Codex 底层也开源，SDK 和 server 都有。差别在能换多少，harness 那边插件、模型、工具、界面，几乎都能拆了重装。</p>
<p>真拿去干活，Codex 的 Git 审查、worktree、云端执行、权限审批是一套完整流程，我改真实项目就用它。harness 也能读文件、跑终端、开子 agent，但不少功能得靠插件撑。</p>
<p>干活留下的痕迹也不一样。Codex 把任务过程、工具输出、diff 都摆出来给我看。harness 记的是会话日志，系统提示词、工具调用、结果都写进去，能恢复能回放。</p>
<p>最后是成熟度。Codex 我用了这么久，沙箱、网络、异常这些坑都替我趟平了。harness 还在预览期，接口说改就改，越自由，自己要操的心越多。</p>
<p>七条比下来，再看 DeepSeek 为什么做 harness 就通了。API 价压得低，harness 又开源，图的不是跟 Codex 抢用户，是把搭 agent 的门槛降下来。门槛一低，小团队拿便宜模型就能攒出能用的 agent。</p>
<p>选哪个，看你要成品还是要底座。今天就要上手，选 Codex。想自由换模型、自己攒 agent，选 harness。先把这道题想清楚，比纠结参数管用。</p>

---

原文链接：[https://www.sz003.com/jiaocheng/2614](https://www.sz003.com/jiaocheng/2614)
