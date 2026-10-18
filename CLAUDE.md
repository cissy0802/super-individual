# 本仓自治规则（内容层：自停 · 自愈 · 英文泄漏自查）

TOPICS.md 是本仓选题的**唯一真相源**。以下三条每次运行都适用；trigger 的启用/停用由外部 `verify-routine-caps` 守卫按 N_pub vs N_top 统一管，**你不要去改 trigger**。

## 1. 自停（写完 TOPICS 就不再生成）
运行开头先算：
- `N_pub` = 已发布页最高编号：`ls *-day*.html`（或本仓命名 week/issue/book/topic）去 `.en.html`、去前导零取最大。
- `N_top` = TOPICS.md 最大编号：`grep '^[-*#]* *(Day|Week|Issue|Book|Topic) *[0-9]+'` 取最大。

**若 N_pub ≥ N_top（TOPICS 已全部写完）**：本次**不生成任何页面、不修改 TOPICS.md、绝不自己发明新主题**；直接结束（至多发一条『本站已写完 TOPICS 路线图，补充新主题后自动续写』的通知，且仅在你判断这是刚写完的当次时发，不要每次都发）。**这条优先级高于本仓 routine prompt 里任何"超表就自造新主题"的旧措辞。** 新主题只由 BigCat 手动或 deep-research 反哺加进 TOPICS.md；加了之后守卫会自动重开、routine 自然续写。

## 2. 自愈（保持 TOPICS ⊇ 已发布）
**只在越界时动手**：若本期 Day/编号按 TOPICS 计划写、TOPICS 里本就有这行 → 不动。只有当你发布的编号是 **TOPICS.md 里没有的**（用户手动指定主题、或 deep-research 反哺内容，当时漏记进 TOPICS）时：
1. 用本期页面标题/副标题，在 TOPICS.md **末尾 append** 一行 `- Day N: <主题> — <要点>`（前缀 Day/Week/Issue/Book/Topic 随本仓约定，先 `grep` 看已有行照抄）。
2. 与本期内容改动**一并 commit / push 到 main**。
3. **只 append，绝不修改已有行。** 否则越界页占了 `dayN`、TOPICS 缺行，日后往 TOPICS 补的 Day N 新主题会撞车永远写不出。

## 3. 英文页中文泄漏自查
生成 `*.en.html` 后、publish 前，对它 grep 这些指纹（命中=模板槽把中文漏进了英文页）：
`class="en">[一-鿿]` / `class="name-en">[一-鿿]` / `class="name-zh">[一-鿿]` / `class="cn">[一-鿿]` / `Reflections — [一-鿿]` / `class="lang-tag">ZH`
命中就修掉（删中文节点或译成英文）再 publish。**正常情况不算泄漏**：经文/古典原典+英译、孙子兵法原文+英译、term(中文) 括注、代码/分词演示、语言切换标签『中文』、主题本身是中文的页。

## 新页面必带共享脚本（免触发 inject-comments 机器人提交）

生成任何 `*.html`（含 `.en.html`）时，在 `</body>` 前直接写入这 4 行，勿遗漏：

```html
<script src="https://hub.cissychen.com/comments.js" defer></script>
<script src="https://hub.cissychen.com/search.js" defer></script>
<script src="https://hub.cissychen.com/index-button.js" defer></script>
<script src="https://hub.cissychen.com/i18n-tts.js" defer></script>
```

这样 CI 的 inject-comments 不会再对新页面追加自动提交。

## 4. 页尾两节：越界 + 十条要点（2026-10-17 起，day / skill 两个系列都适用）

**2026-10-17 起**，每篇新页（`*-day{N}.html` 与 `*-skill{N}.html`，中英两页都要）在**正文最后一个 `.section` 之后**、收尾框（`.combo` 选购卡 / `.glossary` 术语表 / `.thinking` 深入思考 / `.refs` 延伸阅读）**之前**，依次加两节。这条优先于 routine prompt 里旧的页面骨架；旧页面不补。

1. **`.crossx` 越界 · 跨学科的联想**（2026-10-17 起，必写，**3–5 条**）：写本篇里的某个工程想法和另一个领域的什么东西是**同一个结构**——像在哪、不像在哪。每条 `<b>学科 · 概念/人物</b>：…`，约 60–90 字（一两句），只有展开的那 1 条可到约 120 字。往读者的深度兴趣挂：意识、佛学、量子力学、神经科学、东西方哲学、心理学、生物进化、复杂性科学；旁支领导力、投资、商业。**别挂回本仓自己的地盘**（AI / 软件工程 / 分布式系统 / 工具生态——这些本仓天天写，挂了等于没越界）。具体研究、人物、年份必须真实准确，拿不准就换一条。原作者或被介绍的 skill/文档自己点名引用的东西进正文；我们联想到的才进越界。英文页标题 `// Crossovers`。
2. **`.takeaways` 十条要点**（2026-10-17 起，必写，**正好 10 条**）：读者拿它直接记笔记。每条一句完整的话，约 20–45 字，**单独抄出去也能看懂**：写出工具名、协议名、概念名，不用「它」「这个插件」这类要靠上下文的代词。人名/工具名不必每条都当主语开头：全组里主角的名字出现两三次就够，其余各条直接写观点、机制或事实。覆盖各节最值得记的判断、机制和代价（可含越界一两条）；顺序跟正文走。**只总结正文已经写过的东西**，不加新信息，不放引语，不放会过期的星数/安装量。英文页标题 `// Ten takeaways`。

```html
<div class="crossx">
<h3>// 越界 · 跨学科的联想</h3>
<ul>
<li><b>学科 · 概念/人物</b>：…</li>
</ul>
</div>
<div class="tk">
<h3>// 十条要点</h3>
<ol class="takeaways">
<li>…</li>
</ol>
</div>
```

CSS（最近一期页面的 `<style>` 里没有这段——2026-10-17 前的页都没有；拷完样式后**检查有没有，没有就追加进去**）：

```css
.crossx{background:rgba(255,110,196,0.05);border:1px solid rgba(255,110,196,0.25);border-radius:12px;padding:22px 24px;margin:36px 0}
.crossx h3{color:#ff6ec4;font-size:0.95rem;letter-spacing:2px;margin-bottom:10px;font-family:"SF Mono",Menlo,monospace}
.crossx ul{list-style:none;margin:0;padding:0}
.crossx li{margin:12px 0;color:#d8d6e8;font-size:0.92rem;line-height:1.75}
.crossx b{color:#ffb3e0}
.tk{margin:36px 0}
.tk h3{color:#00d4ff;font-size:0.95rem;letter-spacing:2px;margin-bottom:14px;font-family:"SF Mono",Menlo,monospace}
.takeaways{counter-reset:tk;list-style:none;margin:0;padding:0;border:1px solid rgba(0,212,255,0.25);border-radius:12px;background:rgba(0,212,255,0.04)}
.takeaways li{counter-increment:tk;position:relative;margin:0;padding:11px 18px 11px 52px;border-top:1px solid rgba(0,212,255,0.12);font-size:0.93rem;line-height:1.75;color:#d8d6e8}
.takeaways li:first-child{border-top:none}
.takeaways li::before{content:counter(tk,decimal-leading-zero);position:absolute;left:18px;top:12px;font-family:"SF Mono",Menlo,monospace;font-size:0.78rem;color:#00d4ff}
```

篇幅：越界约 400 字、十条要点约 350 字，都从正文以外的新增预算里出，**别为它压缩正文**。`.maxchars` 维持 4000 不动（2026-10-17 核过：最近 5 篇中文页最多 3172 字，加两节约 750 字仍在上限内）。
自检：`publish.sh` 已内置拦截——**只卡从未提交过的新页**，十条要点必须正好 10 个 `<li>`，越界必须 3–5 个 `<li>`；旧页面不查。

---

# 系列二：「Skills 精选」（`*-skill{N}.html` · 真相源 `SKILLS.md`）

本仓现在有**两个互不干扰的系列**，各自一套编号、一份路线图：

| 系列 | 文件名 | 路线图 | 状态 |
|---|---|---|---|
| AI 超级个体实战（原） | `{slug}-day{N}.html` | `TOPICS.md` | Day 1–59 已收口 |
| **Skills 精选（新）** | `{slug}-skill{N}.html` | `SKILLS.md` | 连载中 |

**上面「自停 / 自愈 / 英文泄漏自查」三条规则对本系列同样成立**，只是把 `TOPICS.md` 换成 `SKILLS.md`、把 `*-day*.html` 换成 `*-skill*.html`：
- `N_pub` = `ls *-skill*.html` 去 `.en.html`、去前导零取最大（注意 `skills-library-day36.html` / `skill-maintenance-day59.html` 属于 day 系列，不算）。
- `N_top` = `SKILLS.md` 里 `^- Skill [0-9]+` 的最大编号。
- `N_pub ≥ N_top` → 本次不生成、不改 `SKILLS.md`，发一条 PushNotification 请 BigCat 续单即可。

## 选题：顺序走，不跳号

`SKILLS.md` 按 `## C{n} · 分类` 分组，**节奏是「榜单开路 + 单点深挖」**：每类先一期 `[榜单]`，再 2–4 期 `[深挖]`，写完切下一类。**永远取 `SKILLS.md` 里第一个还没写的 `Skill N`**（不跨类轮询、不挑好写的写），`slug` 用表里给的英文短横线名，文件写成 `{slug}-skill{N}.html`。

## 内容要求（和 day 系列不同的地方）

- **只收真实存在的东西**：每个被点名的 skill / plugin / 仓库 / marketplace / 官方文档都要能给出链接，写进「延伸阅读」。**拿不准就不写**——绝不杜撰 skill 名、作者、星数、安装量、排名。这是本系列的生命线。
- **数字必须挂来源和日期**：星数、安装量、榜位一律写成「据 <来源>，<年-月>」。这些数字天天变，不标日期就是错的。
- **一手源优先**：官方文档（platform.claude.com / code.claude.com / 各家 docs）、GitHub 仓库本身 > SEO 聚合站。只有一份 SEO 站数据时，要写明「据某某 marketplace 的安装量榜」，别当客观事实讲。
- **每期必须有诚实的代价**：这东西什么时候是负担、什么时候不如不装、它的失败模式是什么。不写软文。
- **工具打底，判据收尾**（本系列的重心，别写反）：每期正文必须**点名 6 个以上真实可装/可读的具体条目**，每个都给链接 + 「替你干掉什么 / 怎么装怎么用 / 什么时候别装」三件事；判据放在后半程，用来在这些已点名的候选之间取舍。**跑偏自检**：点名不足 6 个、连着两节没出现具体条目名、或选购卡写成「装一个方法论型」这类占位而非具体名字 → 这期跑偏了，重写。判据是清单的附加值，不是替代品。
- **每期骨架**：`[榜单]` = 01 选品表（6–10 条，先给表再讲道理）→ 02 为什么不能混着比 → 03 三分钟验货判据 → 04 诚实的代价 → 选购卡点名「先装这三个」。`[深挖]` = 01 它替你干掉什么 + 安装命令 + 第一条能跑的用法 → 02 机制 → 03 用法与边界 → 04 代价与替代品。
- **引用日期写来源页自己的日期**，不是写稿日：一篇 2026-03 的榜单在 2026-08 引用要写 2026-03，值差得多时顺手核现值、两个数都给。
- 篇幅、版式、双语、术语随名即释、`.maxchars`（4000 CJK，2026-10-17 起含越界 + 十条要点）等，与 day 系列完全一致：**直接复用最近一期 day 页的内联 `<style>` 与 section 结构**（`.week-tag` / `.intro` / `.section`+`.num`+`.claim` / `.fail` / `.res` / `.glossary` / `.refs` / `.thinking`），2026-10-17 起再加上面第 4 节的 `.crossx` + `.takeaways`（放在最后一节之后、`.combo` 选购卡之前）。
- `.week-tag` 写成 `SKILL {N} / {分类} · {榜单|深挖}`，例如 `SKILL 01 / CODING · ROUNDUP`。

## 发布：本系列有自己的索引页 `skills.html`

站点根 `index.html` 只放**一张入口卡**指向 `skills.html`，**本系列的条目一律不写进 `index.html`**。中英两版分别是 `skills.html` / `skills.en.html`。

`skills.html` 是 **roadmap-first** 的：`SKILLS.md` 里还没写的每一期，都已经作为**灰色占位行** `<div class="entry todo">…</div>`（无 href、`todo` 类）按分类预先列在那儿了。所以发布一期时：

1. 按 `.week` 编号（`S01`、`S02`…）在 `skills.html` 里找到**本期那一行灰色占位行**，**原地**改成 `<a class="entry" href="{本期文件名}">`（去掉 `todo` 类、加 href，内部结构不变）。`skills.en.html` 同理换成 `.en.html` 文件名。
2. **绝不要在末尾另 append 一行**（会重复）。只有当该期在 `skills.html` 里确实找不到灰行时，才 fallback append 到 `<!-- skill-entries -->` 标记前，且要 append 进它所属的 `## C{n}` 分类组里。
3. **每次运行开头先对齐**：扫一遍 `SKILLS.md`，凡是 BigCat 新加、而 `skills.html` / `skills.en.html` 里还没有对应行的条目，按分类顺序补一条灰色占位行（两个页面都要补）。分类组标题 `.group` 也随之补齐。

`./publish.sh` 已支持 `skill` 这个 KIND：它会自动把「index 引用检查」指向 `skills.html` / `skills.en.html`（而不是根 index），并同时守 `TOPICS.md` 与 `SKILLS.md` 不被改动。两个系列编号空间独立，`skill1` 不会和 `day1` 撞车。
