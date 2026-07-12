# Finding-Unknowns Skills

**An orchestrator skill + 8 phase skills that make Claude help you find what you don't know — before it gets expensive to fix.**

*[中文版见下方](#中文) ⬇️*

---

## English

### 1. Source

The idea and every technique here come from **Thariq Shihipar**'s (Anthropic, Claude Code team) essay [*A Field Guide to Fable: Finding Your Unknowns*](https://claude.com/blog/a-field-guide-to-claude-fable-finding-your-unknowns). Read it for the full reasoning; this repo just turns it into runnable skills.

> Community project. Distilled, with attribution, from a public essay by Thariq Shihipar. **Not an official Anthropic repository.**

### 2. How this repo is built

Each skill keeps the author's original wording for *why* the technique matters, lightly rephrased from the essay's second person ("ask Claude to…") into direct instructions **to** Claude ("your job is to…"), since a skill is something the user hands to the agent. Each one then carries the **verbatim example prompts from the essay**, kept in the user's own first-person voice so you can copy them straight into a session.

So each skill = *original essence, rephrased for the agent* + *the essay's real examples*. Nothing invented, nothing padded.

### 3. The skills

| Command | Phase | What it does / when to use |
|---|---|---|
| [`/finding-unknowns`](skills/finding-unknowns/SKILL.md) | **Orchestrator** | The map of the whole method. Enter here to be routed to the right phase skill; it detects where you are and redirects. |
| [`/blindspot-pass`](skills/blindspot-pass/SKILL.md) | Before | Surface your unknown unknowns in an unfamiliar area or domain, then help you prompt better. New to the code/domain and don't even know the questions? Start here. |
| [`/brainstorm-prototypes`](skills/brainstorm-prototypes/SKILL.md) | Before | Wildly different throwaway variations you react to, for taste you can't verbalize. Use when you'll "know it when you see it" (design, UX, tone). |
| [`/interview-me`](skills/interview-me/SKILL.md) | Before | One question at a time, architecture-changing questions first. Use when you've brainstormed but ambiguity remains. |
| [`/reference-hunt`](skills/reference-hunt/SKILL.md) | Before | Use working source code as the spec, even across languages. Use when you can't describe it but some code somewhere does it right. |
| [`/implementation-plan`](skills/implementation-plan/SKILL.md) | Before | A plan that leads with the decisions you're most likely to change, mechanical work at the bottom. Use when you're ready to build. |
| [`/implementation-notes`](skills/implementation-notes/SKILL.md) | During | Log every deviation from the plan so the next attempt learns from this one. Keep running during long builds. |
| [`/pitch-packager`](skills/pitch-packager/SKILL.md) | After | Bundle spec + prototype + notes into a buy-in doc for reviewers. Use when you need approval or a shareable summary. |
| [`/change-quiz`](skills/change-quiz/SKILL.md) | After | A comprehension quiz you must pass before you merge. Use after a large or unfamiliar change. |

### 4. The orchestrator (the extra piece)

The essay describes 8 techniques but leaves the sequencing to you. This repo adds a **9th skill, `finding-unknowns`**, that ties them into one workflow.

- **As a front door:** run `/finding-unknowns` at the start of a non-trivial task. It carries the four-unknowns table and the before → during → after timeline, then routes you to the right phase skill.
- **As an auto-router:** once you're in the workflow, it reads the conversation to detect where you are — a fresh unfamiliar task → `blindspot-pass`; a settled plan with edits underway → `implementation-notes`; a finished diff and talk of merging → `pitch-packager` / `change-quiz` — and redirects to the next skill instead of making you remember which one.
- **The loop:** *what you learn becomes the map for next time.* What a quiz exposes or a deviation reveals sharpens the map for the next project.

Every phase skill is also directly callable on its own (e.g. `/blindspot-pass`), so you can skip the orchestrator whenever you already know the step you want.

### 5. Install

#### Claude Code

**As a plugin (recommended):**

```
/plugin marketplace add chen-xin-94/finding-unknowns-skills
/plugin install finding-unknowns@finding-unknowns-skills
```

Installing as a plugin groups every skill under a `(finding-unknowns)` label in the slash menu — the same way Superpowers shows `(superpowers)` — so you can tell at a glance which skills came from this repo.

**Manually:** copy any `skills/<name>/` folder into `~/.claude/skills/` (all projects) or a project's `.claude/skills/`. Loose skills work fine but won't carry the `(finding-unknowns)` label.

#### OpenAI Codex

Copy `skills/*` into `~/.codex/skills/` — Codex reads the same `SKILL.md` format natively. (Codex has no plugin/marketplace system, so there's no grouped label; the skills just appear on their own.)

#### Any agent (universal)

Vercel's `skills` CLI auto-detects your coding agent (Claude Code, Cursor, Codex, and more) and installs into the right place:

```
npx skills add chen-xin-94/finding-unknowns-skills
```

Add `--list` to preview the skills, or `--skill blindspot-pass` to install just one.

### License

[MIT](LICENSE) for the skill text in this repo. The underlying techniques belong to their author; attribution above.

---

<a name="中文"></a>

## 中文

### 1. 源头

本仓库的思想与全部技巧,均来自 **Thariq Shihipar**(Anthropic,Claude Code 团队)的文章 [*A Field Guide to Fable: Finding Your Unknowns*](https://claude.com/blog/a-field-guide-to-claude-fable-finding-your-unknowns)。完整原理请读原文;本仓库只是把它做成可直接调用的 skill。

> 社区项目。基于 Thariq Shihipar 的公开文章提炼并注明出处。**非 Anthropic 官方仓库。**

### 2. 本仓库的实现方式

每个 skill 都保留作者对"这个技巧为什么重要"的原始表述,只是把文章里第二人称的写法("让 Claude 去做…")轻度改写成**直接对 Claude 下达的指令**("你的任务是…")——因为 skill 是 user 交给 agent 看的东西。每个 skill 再附上**文章里的 example 原句**,保留 user 第一人称口吻,方便你直接复制进会话使用。

所以每个 skill = *原文精髓(改写成对 agent 说话)* + *文章真实的 example*。不编造、不注水。

### 3. Skill 列表

| 命令 | 阶段 | 内容 / 何时使用 |
|---|---|---|
| [`/finding-unknowns`](skills/finding-unknowns/SKILL.md) | **主编排** | 整套方法的地图。从这里进入即可被导向对应阶段的 skill;它会判断你在哪一步并自动 redirect。 |
| [`/blindspot-pass`](skills/blindspot-pass/SKILL.md) | 之前 | 在陌生领域/代码区找出你的"不知道自己不知道",帮你把 prompt 提得更准。刚接触、连该问什么都不知道时,从这里开始。 |
| [`/brainstorm-prototypes`](skills/brainstorm-prototypes/SKILL.md) | 之前 | 给出几个差异极大的一次性方案供你反应,用于说不清的品味。适用于"看到才知道要什么"(设计、UX、语气)。 |
| [`/interview-me`](skills/interview-me/SKILL.md) | 之前 | 一次一个问题,先问会改架构的。头脑风暴后仍有歧义时用。 |
| [`/reference-hunt`](skills/reference-hunt/SKILL.md) | 之前 | 用现成源码当规格,跨语言也行。你描述不出、但某处代码正好实现了它时用。 |
| [`/implementation-plan`](skills/implementation-plan/SKILL.md) | 之前 | 一份把"你最可能改的决策"放最前、机械工作放最后的计划。准备动工时用。 |
| [`/implementation-notes`](skills/implementation-notes/SKILL.md) | 之中 | 记录每一处对计划的偏离,让下一次尝试从这次学到东西。长任务过程中持续记。 |
| [`/pitch-packager`](skills/pitch-packager/SKILL.md) | 之后 | 把 spec + 原型 + 笔记打包成让评审快速理解、同意的文档。需要 buy-in 或可分享的总结时用。 |
| [`/change-quiz`](skills/change-quiz/SKILL.md) | 之后 | 一份 merge 前你必须通过的理解测验。大改动或不熟悉的改动后用。 |

### 4. 主编排 skill(额外加的一块)

文章讲了 8 个技巧,但没规定顺序。本仓库额外加了**第 9 个 skill `finding-unknowns`**,把它们串成一条完整工作流。

- **作为总入口:** 非平凡任务开始时运行 `/finding-unknowns`。它带着四类未知的表格和"之前 → 之中 → 之后"的时间线,把你导向对应阶段的 skill。
- **作为自动路由:** 进入工作流后,它读取对话上下文判断你在哪一步——全新陌生任务 → `blindspot-pass`;计划已定、正在改代码 → `implementation-notes`;diff 完成、在谈 merge → `pitch-packager` / `change-quiz`——并 redirect 到下一个该用的 skill,你不用记是哪一个。
- **闭环:** *你学到的东西,会成为下次的地图。* 测验暴露的、偏离揭示的,都会让下一个项目的地图更清晰。

每个阶段 skill 也都能单独调用(如 `/blindspot-pass`),已知道要哪一步时可跳过编排层。

### 5. 安装

#### Claude Code

**作为 plugin(推荐):**

```
/plugin marketplace add chen-xin-94/finding-unknowns-skills
/plugin install finding-unknowns@finding-unknowns-skills
```

以 plugin 方式安装,slash 菜单里每个 skill 都会带上 `(finding-unknowns)` 标签——和 Superpowers 显示 `(superpowers)` 是同一套机制——一眼就能认出哪些 skill 来自本仓库。

**手动安装:** 把任意 `skills/<name>/` 文件夹复制到 `~/.claude/skills/`(全局)或某个项目的 `.claude/skills/`。散装安装也能用,只是不会带 `(finding-unknowns)` 标签。

#### OpenAI Codex

把 `skills/*` 复制到 `~/.codex/skills/`——Codex 原生读取相同的 `SKILL.md` 格式。(Codex 没有 plugin/marketplace 系统,因此没有分组标签,skill 会各自单独出现。)

#### 任意 agent(通用)

Vercel 的 `skills` CLI 会自动识别你的编码 agent(Claude Code、Cursor、Codex 等)并装到对应位置:

```
npx skills add chen-xin-94/finding-unknowns-skills
```

加 `--list` 预览全部 skill,或 `--skill blindspot-pass` 只装一个。

### 许可

本仓库的 skill 文本采用 [MIT](LICENSE) 许可。底层技巧归原作者所有,出处见上。
