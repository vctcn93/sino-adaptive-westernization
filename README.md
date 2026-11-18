<p align="center">
  <picture>
    <source srcset=".github/assets/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src=".github/assets/logo-light.svg" alt="sino-adaptive-westernization" width="340">
  </picture>
</p>

<p align="center">Chinese prose with an English skeleton. This takes the skeleton out.</p>

<p align="center"><sub>数能化 出品</sub></p>

<p align="center">
  <a href="LICENSE"><img alt="license" src="https://img.shields.io/github/license/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
  <a href="https://github.com/vctcn93/sino-adaptive-westernization/releases"><img alt="version" src="https://img.shields.io/github/v/tag/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
  <a href="SKILL.md"><img alt="format" src="https://img.shields.io/badge/format-SKILL.md-blue?style=flat-square"></a>
  <a href="https://github.com/vctcn93/sino-adaptive-westernization/stargazers"><img alt="stars" src="https://img.shields.io/github/stars/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
</p>

<p align="center">English | <a href="README.zh.md">简体中文</a></p>

---

## What it catches

A skill for auditing and rewriting Chinese prose. It holds two sets of trouble in two files, kept apart because they come from different places.

Yu Guangzhong's three essays supply the first set. 《中文的常态与变态》 separates the normal from the abnormal and gives every disease a name you can point at. 《从西而不化到西而化之》 tells westernization that damages a sentence from borrowing that pays off, and works fifty-one examples to show the difference. 《论中文之西化》 follows the syntax back through history. Read together they hand a model something it lacked: a way to call a sentence broken, not merely rare.

The second set is not his. It is what editors have been arguing about since 2023, the tells of Chinese written by a machine. Nothing in that file is borrowed from the essays.

| # | Rule | Signals | English source | Before | After | What it fixes |
|---|---|---|---|---|---|---|
| 1 | Light verb + abstract noun | 作出 / 进行 / 加以 / 给予 / 予以 | *make a response, take action, conduct a study* (Yu) | 作出了十分热烈的反应 | 反应十分热烈 | An empty verb propping up an empty noun |
| 2 | Abstract noun in subject position | ……的提升 / 减少 / 推进 + 改变 / 带动 / 影响 | nominalization as subject: *the reduction of his income* (Yu) | 他的收入的减少改变了他的生活方式 | 他收入减少，乃改变生活方式 | The reader unpacks the noun before seeing who did what |
| 3 | Stacked 的, top-heavy modifiers | three or more 的 in one clause | relative clauses and compound modifiers crammed before the head noun (Yu) | 我见到一个长得像你兄弟说话也有点像他的陌生男人 | 我见到一个陌生男人，长得像你兄弟，说话也有点像他 | The head noun arrives too late to matter |
| 4 | Fake jargon suffixes | ……性 / ……型 / ……度 / ……化 / ……主义 | *-ness, -ity, -ization, -ism* (Yu) | 具有很高的知名度 | 很有名 | An academic coat on a plain adjective |
| 5 | 之一 and false precision | ……之一 / 最……之一 / 在一定程度上 | *one of the greatest …* (Yu) | 李白是中国最伟大的诗人之一 | 李白是中国极伟大的诗人 | Hedging that buys safety and gives nothing |
| 6 | Mechanical 被 | 被 / 被……所 / 被……给 | *be + past participle* (Yu) | 我不会被你这句话吓倒 | 你这句话吓不倒我 | The actor disappears, and the force with it |
| 7 | Idling prepositional frames | 关于 / 对于 / 作为 / 由于……使得 | *as for, regarding, owing to … so that* (Yu) | 由于他的家境贫穷，使得他只好休学 | 他家境贫穷，只好休学 | Half a sentence spent on a frame that carries nothing |
| 8 | Spare adverbs, there-is sentences | 成功地 / 存在着 / ……的原因 | *successfully + verb, there is / there exists* (Yu) | 成功地推翻了满清 | 推翻了满清 | The verb already contains the result |
| 9 | Forced 和 / 及, redundant 们 | 和 / 与 / 及 on verbs and adjectives; 人们 | *and* joining adjectives; English plural *-s* → 们 (Yu) | 起步更早及迈步更快 | 起步更早而迈步更快 | Conjunctions used as all-purpose glue |
| 10 | when / after frames | 当……的时候 / 当……之后 | *when …, after …* (Yu) | 当你把稿子写好了之后，立刻用挂号信寄给编辑 | 你稿子一写好，立刻用挂号信寄给编辑 | Word order already carries the sequence |
| 11 | Verb separated from its object | verb + long modifier + 的 + object | a heavy relative clause parked before the head noun (Yu) | 我决不原谅任何事先没有得到我的同意就擅自引述我的话的人 | 任何人事先没有得到我同意就擅自引述我的话，我决不原谅 | By the object, the verb is gone |
| 12 | Unearned binary negation | 不是X，而是Y / 并非……而是 | *not X but Y* (inferred) | 好工具不是用来治措辞的，而是用来治骨架的 | 好工具治的是骨架 | A straw man raised just to be knocked down |
| 13 | Corporate verbs | 实现……提升 / 提供……支撑 / 赋能 / 助力 / 打造 | *empower, drive, enable, provide support for* (inferred) | 该架构为高并发场景下的系统稳定性提供了强有力的支撑 | 这套架构在高并发下更稳 | A concrete action turned into a slogan |
| 14 | Thinking crutches | 值得注意的是 / 本质上 / 换句话说 | *it is worth noting that, essentially, in other words* (inferred) | 值得注意的是，缓存穿透往往发生在高频查询场景下 | 高频查询很容易引发缓存穿透，根子往往在架构设计 | Filler that slows a reader who already follows |
| 15 | Significance inflation | 标志着 / 见证了 / 奠定了坚实基础 | *marks a milestone, lays a solid foundation* (inferred) | 此次协议的签署标志着双方合作迈出了具有里程碑意义的一步 | 双方签了协议，正式启动合作 | Grand framing standing in for a fact |
| 16 | Trailing participle | ，推动着…… / ，象征着…… | a trailing *-ing* clause hung off a finished sentence (inferred) | 新平台整合了多方数据，打破了信息孤岛，推动着行业向智能化转型 | 新平台打通了多方数据 | A claim softened into a gesture |
| 17 | Filler triads | 高效、稳定、安全 / 降本、增效、提质 | the tricolon, English copywriting's rule of three (inferred) | 新方案全面、高效、稳定，助力企业降本、增效、提质 | 新方案运行稳，能替企业省钱提效 | Rhythm padded out with near-synonyms |
| 18 | Promo adjectives, vague authority | 丰富的 / 业界普遍认为 / 专家指出 | *vibrant, rich, experts say, studies show* (inferred) | 业界普遍认为，微调比单纯改提示词更适合垂直领域 | 在垂直领域，微调往往比单纯改提示词更稳妥。[缺具体评测或出处，建议补充] | Authority with no name attached |
| 19 | Formatting crutches, pep-talk endings | **核心结论**： / emoji / 未来可期 | bold lead-ins, emoji, *the future looks bright* (inferred) | **核心结论**：这套流程能帮团队省下一半时间。未来可期 | 这套流程能替团队省下一半时间 | Decoration doing the work the sentence should do |
| 20 | Signposting | 接下来我们将 / 下面从三个方面来看 | *in this section we will …* (inferred) | 接下来我们将从三个方面来分析缓存问题 | 缓存问题主要有三种表现。（随后直接进内容） | Announcing the thing instead of saying it |
| 21 | Overworked metaphor, scare quotes | each transition reuses one metaphor; 「全链路」「闭环」 | *scare quotes* (inferred) | 打通「全链路」的「闭环」 | 打通整条流程 | Quotation marks used as conceptual weight |
| 22 | Even paragraphs, aphorism closers | identical section shapes; a punchline every time | symmetrical structure, *punchline* copywriting (inferred) | 每小节都以「效率，才是流程的终点」这类句子收尾 | 收在最后一条事实或逻辑转折上 | Reads like a template, not a person |

## Install

```bash
# Claude Code
git clone https://github.com/vctcn93/sino-adaptive-westernization \
  ~/.claude/skills/sino-adaptive-westernization

# other harnesses read the same layout from their own skills directory
# manual: copy the folder anywhere your agent looks for skills
```

> [!TIP]
> Restart the session or run `/reload` afterwards. Skill lists are read at startup.

## Files and how it is called

```text
sino-adaptive-westernization/
├── SKILL.md                      rules, register, guardrails, three-layer scan
└── references/
    ├── yu-syntax-catalog.md      11 diagnostics, cited to essay and section
    └── ai-rhetoric-patterns.md   AI-01 to AI-11, repairs that invent nothing
```

`SKILL.md` opens a reference file only when the job needs it: a full audit, a borderline case, or a citation you have to check.

| You say | What happens |
|---|---|
| 帮我改改这段中文 / 读着别扭 / 有翻译腔 | Mode A: cleaned text, plus notes on what moved |
| 别改，先审 / 哪儿 AI 味重 / 逐条标出处 | Mode B: a table of fragments, pattern class, minimal repair |
| *polish this Chinese / does this read machine-written* | Either mode, same rules |

```text
把这段改成正常中文：<稿子>
别改，先审：这段哪些句法西化、哪些是 AI 腔？逐条标出处。
```

Five steps, always in order: fix the register, run the guardrails, scan the three layers, rebuild the sentence, then check your own output for the same tics.
