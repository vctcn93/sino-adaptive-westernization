# Sino-adaptive Westernization

**善性西化** — an agent skill that audits Chinese prose for stiff, literal Westernization (*西而不化*) and modern LLM rhetoric, then rewrites it into idiomatic Chinese that keeps its precision.

一个 Agent 技能：先审出中文里僵硬的直译西化句法（西而不化）和当下 LLM 腔，再改写成自然、有节奏而且不丢精确度的中文。

---

## What it does

Give it a Chinese draft — AI-generated, translated, or written by a human under translator's brain — and it works in a fixed order: set the register, apply non-negotiable guardrails, scan three layers, reconstruct positively, then check its own output for rhythm. It reports either a clean rewrite or a diagnostic table of offending fragments with minimal repairs.

给它一段中文稿子——AI 生成的、翻译来的、或者人写的但带着翻译腔的——它按固定顺序处理：先定语域，再走不可让步的护栏，三层扫描，做正向重构，最后自查自己的输出节奏。产出可以是干净的重写稿，也可以是逐条列问题的诊断表（原句 / 归类出处 / 最小改法）。

The guardrails matter more than the rules. It will not invent data, dates, or sources to make a hollow sentence sound concrete; when a claim is genuinely unsupported it flags `[缺具体例证/来源，建议补充]` and leaves the gap visible. Deliberate style — poetry, dialogue, dialect, legal formulas, Qian Zhongshu-style long periodic sentences — is protected rather than flattened.

护栏比规则本身更要紧。它不会为了让空话听起来具体而去编数据、编日期、编出处；遇到实在没有支撑的说法就标 `[缺具体例证/来源，建议补充]`，把窟窿留在明处。故意为之的风格——诗、对话、方言、合同条文、钱锺书式的长句——是保护对象，不是清理对象。

## Two rule layers, deliberately separate

Layer 1 is Yu Guangzhong's sentence-level diagnostics: eleven patterns drawn from 《中文的常态与变态》《从西而不化到西而化之》《论中文之西化》 — weak verbs propping up abstract nouns, abstract nouns in subject position, stacked `的` and top-heavy pre-modifiers, fake jargon suffixes (`……性/化/度`), hedging `之一`, mechanical `被`, hollow prepositional frames, redundant `成功地`, forced `和/及`, `当……的时候`, and objects stranded far from their verbs.

第一层是余光中的句法诊断：十一种病，出自《中文的常态与变态》《从西而不化到西而化之》《论中文之西化》——弱动词撑抽象名词、抽象名词占主位、`的`字堆叠与头重脚轻的前饰、假术语后缀（`……性/化/度`）、滥用的`之一`、机械`被`字句、空转介词框架、冗余的`成功地`、硬凑的`和/及`、`当……的时候`、以及动词与宾语拉得太远。

Layer 2 is modern editorial criteria for LLM output: unprompted binary negation (`不是 X，而是 Y`), buzz-verbs (`赋能 / 助力 / 打造`), thinking crutches (`值得注意的是`), significance inflation (`标志着`), trailing participle clauses (`，推动着……`), hollow triads, promo adjectives, fuzzy attribution, formatting crutches, signposting, overworked metaphors, and the aphorism-after-every-section habit.

第二层是针对 LLM 输出的现代编辑标准：无来由的对偶否定（`不是 X，而是 Y`）、黑话动词（`赋能 / 助力 / 打造`）、思维拐杖（`值得注意的是`）、意义镀金（`标志着`）、句尾分词腔（`，推动着……`）、三段式凑数、宣传形容词、模糊归因、格式依赖、报幕句、过度使用的隐喻、以及节节都要金句收尾的毛病。

The split is not decoration. Yu's diagnoses are cited to specific essays and sections; the AI-rhetoric rules are not his, and labeling them as his would be fabricated scholarship. The skill states this provenance boundary explicitly and instructs the model never to invent page numbers.

这个分层不是包装。余光中的诊断严格标注篇目与节次；AI 腔那套不是他的说法，硬算到他头上就是伪造学术来源。技能里把这条界线写死了，并要求模型绝不编造页码。

## Install

Clone it where your agent looks for skills. For Claude Code:

把仓库克隆到你的 agent 找技能的位置。以 Claude Code 为例：

```bash
git clone https://github.com/vctcn93/sino-adaptive-westernization \
  ~/.claude/skills/sino-adaptive-westernization
```

Codex and other harnesses read the same layout from their own skills directory. If you use the skills CLI, `npx skills add vctcn93/sino-adaptive-westernization` also works — this repository is a plain `SKILL.md` skill with support files, no build step.

Codex 和其他 harness 从各自的技能目录读同样的结构。用 skills CLI 的话 `npx skills add vctcn93/sino-adaptive-westernization` 也能装——本仓库就是标准的 `SKILL.md` 加支撑文件，没有构建步骤。

## Two ways to use it

Mode A is a direct revision: the cleaned text plus three to five notes on what structurally changed. Mode B is a diagnostic audit — a table of original fragment, pattern class with citation, and the minimal repair — for when you want to see the reasoning instead of just the result.

用法 A 是直接改稿：给改后正文，加三到五条结构性修订说明。用法 B 是诊断审计：一张表，列原句片段、归类与出处、最小改法——想看清判断依据而不是只拿到结果时用它。

Mode A, ask plainly:

```text
把这段改成正常中文：<paste your draft>
```

Mode B, ask for the reasoning:

```text
别改，先审：这段有哪些西化句法和 AI 腔？逐条标出处。
```

Register is picked first and it changes everything. Technical, academic, and official writing keeps established terminology (`可读性`, `鲁棒性`), genuine conditionals, and passives where the actor is unknown; essays and commentary get the aggressive treatment; email and spoken text go for directness. If you don't say, general prose is assumed.

语域先定，而且决定后面全部尺度。技术、学术、公文留住既有术语（`可读性`、`鲁棒性`）、真实的条件句、以及施动者不明的被动；专栏评论散文按最严标准清；邮件和口播追求直给。你不指定时按一般散文处理。

## What's inside

```text
SKILL.md                            101 lines — mission, register rules, guardrails, 3-layer scan, output modes
references/yu-syntax-catalog.md      43 lines — 11 Yu diagnostics with citations and before/after pairs
references/ai-rhetoric-patterns.md   97 lines — AI-01…AI-11, signals, why it hurts, non-hallucinating repairs
```

`SKILL.md` 只放会改变判断的规则，细节全在 `references/`。做完整审校、碰到边界情况、或要核对引用时才展开参考文件——这样常规改稿不会把上下文塞满。

`SKILL.md` keeps only the rules that change a judgment; detail lives in `references/`. Load those for a full audit, borderline cases, or verifying a citation — routine editing shouldn't need them.

## Provenance and limits

Quotations from Yu Guangzhong's essays are short citations used for critical commentary, cited by essay and section (never by invented page numbers). The skill is not affiliated with or endorsed by the Yu Guangzhong estate. It also does not claim to cover all of Chinese prose style: it targets Westernization and LLM tics specifically, and says so instead of pretending to be a general writing coach. If a passage is already clean, the skill is instructed to say so rather than manufacture edits.

余光中原文的引用是评论性短引用，按篇目与节次标注（绝不编页码）。本技能与余光中著作权方无关联，也未获其授权或背书。它也不假装覆盖全部中文文风问题——只针对西化与 LLM 腔，并且会明说这个边界；稿子本来干净时，技能被要求直说干净，而不是硬凑修改。

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, ship it, sell what you build with it; keep the copyright notice.

MIT 许可，详见 [LICENSE](LICENSE)。可以随便用、改、发、拿去收费，留着版权声明就行。
