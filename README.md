# Sino-adaptive Westernization

**善性西化**，一个审中文、也改中文的 Agent 技能。

It reads a Chinese draft, works out which register it is in, scans for stiffness, then rewrites. Where a claim is empty it says so instead of inventing detail.

它读一段中文，先看是什么文体，扫一遍僵的地方，然后动手改。碰上没有依据的空话，它明说这儿缺东西，不自己补。

## What it catches

Two rule sets, in separate files, because they come from different authors. Merging them would put words in a dead man's mouth.

分两个文件放，出处不同。混着谈，等于替别人认领他没说过的话。

Yu Guangzhong's eleven are cited to essay and section: weak verbs holding up abstract nouns, stacked `的`, mechanical `被`, fake jargon suffixes (`……性`, `……化`), hollow prepositional frames, and clauses where the verb and its object are half a sentence apart.

余光中那十一病在 `references/yu-syntax-catalog.md`，每条标了出自哪篇哪节：弱动词撑抽象名词、`的`字堆叠、机械`被`字句、假术语后缀（`……性`、`……化`）、空转的介词框架，还有那种动词和宾语隔着半句话的长句。

The model set sits in `references/ai-rhetoric-patterns.md` with no Yu attribution, because it isn't his: binary negation with no misconception behind it, significance inflation (`标志着`), the `，推动着……` tail, the aphorism every section ends on.

模型那套在 `references/ai-rhetoric-patterns.md`，不挂他的名字：没有真误解也要摆的对偶（`不是X，而是Y`）、意义镀金（`标志着`、`奠定了坚实基础`）、句尾拖着的`，推动着……`、每小节都用金句收口。

## A pass, before and after

```text
改前  该架构为高并发场景下的系统稳定性提供了强有力的支撑，实现了处理效率的显著提升。
改后  这套架构在高并发下更稳，处理也更快。

改前  值得注意的是，缓存穿透往往发生在高频查询场景下。本质上，这是架构设计不足导致的。
改后  高频查询很容易引发缓存穿透，根子往往在架构设计。
```

## Install

```bash
git clone https://github.com/vctcn93/sino-adaptive-westernization \
  ~/.claude/skills/sino-adaptive-westernization
```

Codex and other harnesses read the same layout from their own skills directory. With the skills CLI, `npx skills add vctcn93/sino-adaptive-westernization` works too; this repo is a plain `SKILL.md` plus support files, no build step.

Codex 和别的 harness 从各自的技能目录读同样的结构。用 skills CLI 的，`npx skills add vctcn93/sino-adaptive-westernization` 也行，本仓库就是 `SKILL.md` 加支撑文件，没有构建步骤。

## Two ways to ask

```text
把这段改成正常中文：<稿子>
```

Straight revision: the cleaned text, plus three to five notes on what moved.

直接给改后正文，附三到五条结构说明。

```text
别改，先审：这段哪些句法西化、哪些是 AI 腔？逐条标出处。
```

A table instead: original fragment, pattern class with citation, the smallest repair. Use it when you want to see the reasoning.

给一张表，列原句、归类出处、最小改法。想看清凭什么这么改的时候用。

## Register first

Official documents, papers and email don't get cleaned to essay standards. Technical terms stay (`可读性`, `鲁棒性`), and so do passives where the actor is unknown. What goes is the fake verb (`进行详细的研究`) and the modifier pile in front of the noun. Spoken text and email want it plainer still. If you don't say, general prose is assumed.

公文、论文、邮件不该按专栏散文的标准清。「可读性」「鲁棒性」这类术语留住，施动者不明时的被动也留住。该清的是「进行详细的研究」这种假动作，和堆在名词前面的长定语。邮件和口播更简单，直说。你没指定，按一般散文处理。

## Files

```text
SKILL.md                              101 行   规则、语域、护栏、三层扫描、输出模式
references/yu-syntax-catalog.md        43 行   十一病，带引用和改前改后
references/ai-rhetoric-patterns.md     97 行   AI-01 到 AI-11，含不编造事实的修法
```

Detail lives in `references/`. Open them for a full audit or a borderline case; routine editing gets by on `SKILL.md` alone.

细节都在 `references/` 里。做完整审校、碰到边界情况时再展开，日常改稿只看 `SKILL.md` 就够。

## Sources

Quotes from Yu are short phrases, cited by essay and section, never by invented page numbers. This repo is not affiliated with the rights holders and carries no endorsement from them.

余光中的话只取短语，按篇目和节次标注，不编页码。本仓库与著作权利方无关，未获授权或背书。

It covers two kinds of trouble and nothing else. Don't hand it a manuscript and expect a verdict on whether the piece was worth writing.

它只管西化和 LLM 腔这两类毛病。别拿它当通用写作教练，也别指望它替你判断文章值不值得写。

A clean passage should get called clean. Manufacturing edits to look busy is its own disease.

稿子本来就干净时，它应该说干净。硬凑一堆修改出来，那是另一种毛病。

## License

MIT, see [LICENSE](LICENSE). Use it, fork it, charge for what you build with it, keep the notice.

MIT 许可，见 [LICENSE](LICENSE)。随便用、改、发、拿去收费，留着版权声明就行。
