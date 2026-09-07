# AGENTS.md是什么？6万开源项目在用的AI编程说明书，Codex官方支持

> 原文链接：[https://www.sz003.com/jiaocheng/2557](https://www.sz003.com/jiaocheng/2557)

<p>最近翻热门开源仓库，根目录里总能撞见一个新面孔：AGENTS.md。GitHub 上用它的项目已过 6 万，OpenAI 自家主仓库里躺着 88 个。这是什么东西。一份专给 AI 编码工具看的项目说明书，README 给人读，AGENTS.md 给 agent 读。</p>
<p>怎么就突然火了。想想让 AI 帮忙写代码最磨人的环节：写不出来反而是小事，真正卡住的是它不懂你的项目。依赖怎么装，测试怎么跑，提交信息什么格式，新会话每开一次，同样的交代就得重来一遍。AGENTS.md 就是冲这份重复劳动去的，标准的解药。</p>
<p><img decoding="async" src="https://cdn.laoshoucun.com/web/codex/2026/08/20260825010321_788755.png" alt="AGENTS.md 文档概念图"></p>
<h2>写什么进去：朴素是美德</h2>
<p>官方给它的定位收得紧：构建步骤，测试命令，代码风格，PR 规范，全是塞进 README 会撑爆、对人类贡献者又没多大用的信息。典型的一份长这样：</p>
<p><code>## Setup commands<br />- Install deps: pnpm install<br />- Run tests: pnpm test<br />## Code style<br />- TypeScript strict mode</code></p>
<p>没有新语法，没有 YAML，纯 Markdown 一份。它的价值从来不在格式，在约定：agent 一进项目就知道去哪儿找指令，你不用回回现喂。</p>
<h2>monorepo 的大考验：就近原则</h2>
<p>打磨得最细的场景是嵌套：仓库根目录摆一份总的，各子项目再各摆一份，agent 读取时就近优先，动哪个子目录的代码，先翻哪个目录的文件，子项目的指令天然压过全局。这不是纸面设计，OpenAI 主仓库 88 个文件各管一摊，就是拿它当基础设施在跑。</p>
<h2><a href="https://www.sz003.com/" target="_blank" rel="noopener">Codex</a> 原生支持，零配置</h2>
<p>进入项目目录，Codex 自己就会发现并读走这个文件，一行配置都不用加。你唯一要做的，是把它提交进仓库根目录。写法与 CONTRIBUTING.md 一个路数，把&#8221;你会跟新同事交代什么&#8221;写进去，就对了。</p>
<p>这笔投入还格外划算：AGENTS.md 已经是事实标准，Cursor，Gemini CLI，GitHub Copilot 的 coding agent，Devin，Windsurf，Aider，VS Code，一家不落全支持，写一份，全家桶通用。</p>
<p>实操建议有点反直觉：从最短的版本起步。三条命令（装依赖，跑测试，构建）加两条风格约束，先让它转起来。agent 每犯一个错，就补一条进去。别一上来就憋大而全的规范文档，这是给机器读的操作手册，不是企业文化手册。写法细节，站内<a href="https://www.sz003.com/jiaocheng" target="_blank" rel="noopener">教程</a>栏目里有展开。</p>

---

原文链接：[https://www.sz003.com/jiaocheng/2557](https://www.sz003.com/jiaocheng/2557)
