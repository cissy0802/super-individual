# Skill Shelf Roadmap — 「Skills 精选」系列选题表

> **⚠️ routine 须知**：本表是**本系列**（`*-skill{N}.html`）的唯一真相源，与 `TOPICS.md`（已收口的 Day 1–59 工程系列）互不相干、编号各走各的。
> 只写下面**已列出**的条目；**全部写完就停**——别自己发明新条目、别往本文件加行，只发一条 PushNotification 请 BigCat 续单。
> 新条目由 BigCat 手动或 deep-research 反哺加入。

## 这个系列在做什么

收录**市面上真实存在、真的被人用**的 AI skills / plugins / rules / MCP servers，以及各家官方与一线团队沉淀下来的 **AI 使用最佳实践**；按分类每日推送。

**节奏 = 榜单开路 + 单点深挖**：每个分类先出**一期榜单**（这一类有哪些、谁排在前面、按什么判据选、什么时候不该装），随后 **2–4 期**从该类里挑最值得的单个 skill / 单条实践**深挖**（它到底怎么工作、真实用法、边界与代价），再切下一个分类。

**硬规矩（技术站的生命线）**
1. **只收真实存在的东西**：每个被点名的 skill / 仓库 / marketplace / 官方文档都要能给出链接。**拿不准就不写**，绝不杜撰名字、星数、安装量、作者。
2. **数字必须挂来源和日期**：星数、安装量、排名一律写成「据 <来源>，<年-月>」，因为这些天天在变。
3. **不做软文**：每一期都要有诚实的代价 —— 这东西什么时候是负担、什么时候不如不装。
4. **实践优先于工具**：工具会过时，判据不会。每期都要提炼出**读者自己以后能复用的判断标准**，而不只是一份清单。
5. 编号 `Skill N` 与文件名 `{slug}-skill{N}.html` 一一对应，按写作顺序递增。

---

## C1 · 编码与代码库（Coding & Codebase）

- Skill 1 [榜单]: coding-skills-roundup — AI 编码 skills 榜单 — 三种形态别混着比（方法论型 / 单点工具型 / 官方产出型）；把官方 skill authoring 检查表反过来当选购单；装多了的 context 税与触发冲突；skill vs subagent vs MCP 的分工
- Skill 2 [深挖]: superpowers — Superpowers：把方法论编进 skill — brainstorm → plan → TDD → 两段式 review 的强制流水线；composable skills 如何自动触发；跨 8 个 harness 的可移植性；小任务上它为什么是负担
- Skill 3 [深挖]: code-review-skills — 代码审查类 skills — 审查清单进 prompt vs 进 skill；为什么「审查」是 skill 的甜区（高频 + 有客观 oracle）；假阳性治理；和 CI 门禁怎么分工
- Skill 4 [深挖]: git-workflow-skills — Git 工作流类 skills — commit message / PR 描述 / changelog 三件套；diff 作为唯一输入的可靠性；团队约定如何编码成 examples pattern；什么时候一条 git hook 比 skill 更合适

## C2 · 元技能：做 skill 的 skill（Meta — Building Skills）

- Skill 5 [榜单]: meta-skills-roundup — 元技能榜单 — skill-creator / mcp-builder / artifacts-builder 这类「造工具的工具」；官方 spec 与 template；为什么先写 eval 再写文档
- Skill 6 [深挖]: skill-authoring — 官方 skill authoring 最佳实践精读 — name/description 的硬约束与触发机制；progressive disclosure 三种模式；自由度阶梯（窄桥 vs 旷野）；500 行与一层引用的由来
- Skill 7 [深挖]: skill-eval — 给 skill 写 eval — 先建 baseline 再写 skill；三个场景起步；Claude A 写 / Claude B 用的双实例迭代法；怎么判断一次改动是真提升
- Skill 8 [深挖]: agents-md — AGENTS.md 与跨 harness 可移植性 — 一份指令喂多个 agent；与 CLAUDE.md / Cursor rules 的关系；仓库级约定该写什么、不该写什么

## C3 · 工具连接层：MCP 与集成（MCP & Integrations）

- Skill 9 [榜单]: mcp-servers-roundup — MCP server 榜单 — 按星数与真实使用量排的头部服务；文档检索 / 浏览器 / 代码托管 / 办公套件四条主线；每接一个 server 交多少 context 税
- Skill 10 [深挖]: context7-docs-mcp — 文档检索类 MCP — 把「最新版官方文档」灌进 agent，治的是训练截止日期这个病；何时不如直接贴文档
- Skill 11 [深挖]: playwright-mcp — 浏览器自动化 MCP — accessibility tree vs 截图两条路线；为什么结构化快照比像素更省 token 也更稳；测试与抓取的边界
- Skill 12 [深挖]: mcp-security — 接 MCP 的安全边界 — 不可信工具返回值即注入面；权限最小化与人工确认门；tool 名冲突与全限定名

## C4 · 文档与办公产出（Docs & Deliverables）

- Skill 13 [榜单]: office-skills-roundup — 办公产出类 skills 榜单 — docx / pdf / pptx / xlsx 官方四件套为什么是「最能立刻变现」的一类；模板型 skill 的共同结构
- Skill 14 [深挖]: docx-xlsx-internals — 文档类 skill 怎么做到「不坏文件」 — 解包-改 XML-校验-重打包的循环；把校验脚本当反馈闭环；确定性操作为什么要写成脚本而不是让模型现编
- Skill 15 [深挖]: brand-guidelines — 品牌与风格类 skill — 把风格指南变成可执行约束；风格类 skill 最难的是验收标准

## C5 · 写作与内容（Writing & Content）

- Skill 16 [榜单]: writing-skills-roundup — 写作类 skills 榜单 — 去 AI 味 / 长文起草 / 摘要 / SEO 各解决什么；为什么写作类 skill 的口碑分歧最大
- Skill 17 [深挖]: humanizing-writing — 「去 AI 味」类 skill — 它到底在删什么句式；把个人 voice 编成 skill 的做法；检测器军备竞赛的坑
- Skill 18 [深挖]: examples-over-rules — 写作类 skill 的通用配方：examples pattern — 三对输入/输出比十条规则更管用；样例怎么选、几个够

## C6 · 研究与信息（Research & Information）

- Skill 19 [榜单]: research-skills-roundup — 研究类 skills 榜单 — 深度研究 / 竞品情报 / 证据链三条线；强研究 skill 的共同点是留下可追溯的痕迹
- Skill 20 [深挖]: research-workflow-skill — 把研究流程写成 workflow skill — 问题→方法→来源→证据→综合→存疑的检查表模式；引用核验作为反馈闭环
- Skill 21 [深挖]: source-grounding — 来源接地与引用可信度 — 哪些内容模型几乎必编（URL/引文/日期）；工具接地怎么改判；二手 SEO 站不能当来源

## C7 · 数据与分析（Data & Analysis）

- Skill 22 [榜单]: data-skills-roundup — 数据分析类 skills 榜单 — NL→SQL / 图表 / 异常检测 / 报告生成；为什么这一类最依赖组织私有上下文
- Skill 23 [深挖]: domain-reference-skill — 按域拆 reference 的 skill 结构 — 一个 SKILL.md 挂多份领域文档，用到哪份读哪份；schema 与口径规则写在哪
- Skill 24 [深挖]: plan-validate-execute — plan-validate-execute 模式 — 让模型先产出可机器校验的中间计划，再执行；批量与破坏性操作的标准打法

## C8 · Agent 编排与自动化（Agent Orchestration & Automation）

- Skill 25 [榜单]: orchestration-skills-roundup — 编排类 skills 与 plugin 榜单 — subagent / hooks / slash command / plugin 各自的位置；什么时候一个 skill 就够、什么时候要上编排
- Skill 26 [深挖]: subagents-vs-skills — subagent 与 skill 怎么分工 — 上下文隔离 vs 指令注入；并行 fan-out 的收益与协调税
- Skill 27 [深挖]: hooks-automation — hooks 与确定性自动化 — 该由代码保证的别交给模型；把「每次都要做」的事钉死在钩子上
- Skill 28 [深挖]: building-effective-agents — 官方《Building effective agents》精读 — workflow 与 agent 的分界；五种基础模式；「能不上 agent 就不上」的成本论

## C9 · 安全 · 审查 · 治理（Safety, Review & Governance）

- Skill 29 [榜单]: safety-skills-roundup — 安全与治理类 skills 榜单 — 密钥扫描 / 依赖审计 / 越权检查 / 输出校验；安全类 skill 必须 fail-closed
- Skill 30 [深挖]: untrusted-skills — 装别人的 skill 有多危险 — skill 即可执行指令与脚本；准入审查清单；marketplace 的信任层级
- Skill 31 [深挖]: truth-first-skills — 「诚实优先」类 skill — 逼模型说「不知道」；把不确定性写进输出契约；怎么验收这类 skill

## C10 · 个人生产力与知识管理（Personal Productivity & PKM）

- Skill 32 [榜单]: pkm-skills-roundup — 个人生产力类 skills 榜单 — 会议纪要 / 收件箱 / 笔记整理 / 日程；这一类为什么最该自建而不是装现成的
- Skill 33 [深挖]: personal-skill-from-repetition — 从重复劳动里长出自己的 skill — 观察「每次都要重新解释的东西」；一次真实任务→一个 skill 的最短路径
- Skill 34 [深挖]: skill-library-hygiene — 个人 skill 库的卫生 — 命名一致性、去重、废弃、按使用度淘汰；什么时候该把 skill 合并回 prompt
