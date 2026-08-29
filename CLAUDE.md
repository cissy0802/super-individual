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
- **实践 > 工具**：每期要提炼出读者以后能自己复用的**判据**（怎么判断一个 skill 值不值得装、怎么验收），而不只是一份清单。工具会过时，判据不会。
- 篇幅、版式、双语、术语随名即释、`.maxchars`（4000 CJK）等，与 day 系列完全一致：**直接复用最近一期 day 页的内联 `<style>` 与 section 结构**（`.week-tag` / `.intro` / `.section`+`.num`+`.claim` / `.fail` / `.res` / `.glossary` / `.refs` / `.thinking`）。
- `.week-tag` 写成 `SKILL {N} / {分类} · {榜单|深挖}`，例如 `SKILL 01 / CODING · ROUNDUP`。

## 发布

- 更新 `index.html`：在 `<!-- skill-entries -->` 标记前插入新条目（`.week` 用 `S01`、`S02`…）；`index.en.html` 同理插入 `.en` 条目。**别插到 Day 归档那一组里去。**
- `./publish.sh` 已支持 `skill` 这个 KIND，并且会同时守 `TOPICS.md` 与 `SKILLS.md` 不被改动。两个系列编号空间独立，`skill1` 不会和 `day1` 撞车。
