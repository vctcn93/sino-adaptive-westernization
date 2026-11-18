---
name: sino-adaptive-westernization
description: Review, diagnose, and rewrite Chinese prose to eliminate stiff literal Westernization (西而不化), LLM rhetorical clichés, and mechanical uniformity, while preserving technical accuracy, author intent, and benign borrowing (西而化之). Use when polishing AI-generated Chinese drafts, editing translationese, or auditing Chinese prose for natural rhythm.
metadata:
  chinese_name: 善性西化
  sources: 余光中《中文的常态与变态》《从西而不化到西而化之》《论中文之西化》; modern editorial anti-AI-prose rules
license: MIT
---

# Sino-adaptive Westernization (善性西化)

## Mission

Transform stiff, translation-heavy, or formulaic AI Chinese into idiomatic, clear, rhythmic Chinese. Following Yu Guangzhong's distinction, the goal is **benign Westernization (西而化之)**—absorbing precision and expressive range where they enrich Chinese—not purist rejection of all foreign syntax or modern vocabulary.

At the same time, modern LLM outputs suffer from rhetorical clichés and structural uniformity beyond Yu's scope. This skill separates **Yu-grounded syntax diagnostics** from **modern AI-rhetoric editing rules** and applies both consistently.

## Step 1: Set the Register Before Editing

Identify the genre first (or follow the user's explicit request). Tolerance for abstraction, passives, and sentence length shifts sharply by register:

1. **Technical / Academic / Official (`技术 / 学术 / 公文`)**
   - **Keep**: Established terminology (`可读性`, `扩展性`, `鲁棒性`), genuine conditional clauses, precise passive statements where the actor is irrelevant or unknown.
   - **Fix**: Weak-verb inflation (`进行研究`, `作出调整`), pre-modifiers burying the noun, verbs separated far from long objects, empty prepositional wrappers (`在……的背景下`, `对于……而言`).
2. **Essays / Commentary / Narrative (`专栏 / 评论 / 散文 / 叙事`)** — *Default for general prose*
   - **Fix aggressively**: All literal Westernization patterns, binary `不是X，而是Y` framing, significance inflation, trailing participle clauses, hollow triads, crutch transitions, signposting, and uniform paragraph/section cadence.
3. **Everyday / Email / Spoken (`日常沟通 / 邮件 / 口播`)**
   - **Priority**: Directness and breathability. Strip formal connectors, throat-clearing preambles, and nominalized actions; put the actor and main verb upfront.

## Step 2: Non-Negotiable Guardrails

- **Never invent facts or specifics.** When removing vague filler (`业界普遍认为`, `丰富的文化遗产`, `迈出重要一步`), **never** fabricate data, dates, examples, or sources to make a sentence sound concrete. Either cut the empty phrase cleanly or mark `[缺具体例证/来源，建议补充]`.
- **Never drop substantive meaning.** Preserve all claims, constraints, technical terms, numbers, direct quotes, and original scope. If tightening a phrase risks altering nuance, flag the tradeoff instead of silently changing the claim.
- **Scan the entire body.** Titles, subheadings, lead-ins, and captions are body text—audit them all. Leave verbatim quotes, poetry, code blocks, and bibliography entries untouched, but never skip scanning surrounding body prose on the pretext that examples appear inside quotes.
- **Keep provenance honest.** Attribute classical Westernization diagnoses to Yu's essays (`《常态》`, `《西化》`, `《西化论》`). Treat AI-rhetoric and uniformity rules as modern editorial criteria, not Yu's rules.
- **Protect deliberate style.** Poetry, dialogue, dialect, legal/contractual formulas, and purposeful complex prose (such as Qian Zhongshu-style periodic sentences) may intentionally depart from plain prose norms. Confirm whether a complex structure works before flattening it.

## Step 3: Three-Layer Diagnostic Scan

Scan the text systematically across three orthogonal layers. Consult the reference files whenever conducting a thorough audit, encountering borderline cases, or verifying citations.

### Layer 1: Sentence Syntax (Yu Guangzhong's 11 Diagnostics)
Full triggers, citations, and edge cases: [references/yu-syntax-catalog.md](references/yu-syntax-catalog.md).
1. **Weak verbs + abstract nouns**: `作出 / 进行 / 加以 / 给予 / 予以` + action noun → restore the direct verb.
2. **Abstract nouns as subjects/objects**: `……的提升 / 减少 / 推进` driving `带动 / 改变 / 影响` → put a person or complete event clause in subject position.
3. **Stacked `的` & heavy pre-modifiers**: Three or more `的` or long clauses piled before a noun → split or shift modifiers after the noun.
4. **Pseudo-jargon**: Unnecessary `……性 / ……型 / ……度 / ……化 / ……主义` outside established terminology → revert to plain adjectives, verbs, or short clauses.
5. **Redundant `之一` & `最……之一`**: Strip `之一` when plurality is obvious or precision is illusory; downgrade `最……之一` to `大 / 极` unless ranking a bounded set.
6. **Mechanical `被` passives**: Restore active voice, topic-comment syntax (`糖吃光了`), or idiomatic passives (`受 / 遭 / 挨 / 教 / 让 / 奉命 / 为……所`) when `被` hides the actor or sounds stiff.
7. **Overused prepositional & role frames**: `关于 / 有关 / 对于……而言 / 作为…… / 由于……使得…… / 基于……` → delete empty frames and let clauses connect directly.
8. **Redundant adverbs & existence/reason padding**: `成功地 / 有效地` before self-completing verbs; `有……存在 / 发生 / 的原因` → delete duplicated result/existence markers.
9. **Over-copied `和 / 与 / 及 / 以及` & redundant `它 / 们`**: Drop unnecessary pronouns (`它 / 它们`) and plural `们` (`人们`, `所有的……们`); use paratactic listing or flexible `而 / 并 / 乃` instead of mechanical `和 / 及`. *(Note: Yu explicitly commends `而` and `并`.)*
10. **Temporal/conditional wrappers**: `当……的时候 / 之后` → drop the frame when sequence is clear from word order or `一……就……`.
11. **Long objects separated far from the verb**: Front-load the event or split into sequential clauses so the verb and object stay close.

### Layer 2: Modern AI Rhetoric & Clichés
Full patterns and non-hallucinating repairs: [references/ai-rhetoric-patterns.md](references/ai-rhetoric-patterns.md).
- **Binary negation crutch**: `不是 X，而是 Y` / `并非……而是……` / `与其说……不如说……` (when no real misconception exists) → state Y directly or use `而`.
- **Modern buzz-verbs**: `实现……提升`、`提供……支撑`、`发挥……作用`、`带来……体验`、`赋能 / 助力 / 打造 / 构建`.
- **Thinking crutches**: `值得注意的是`、`需要指出的是`、`事实上`、`本质上`、`换句话说`、`综上所述`.
- **Significance inflation & trailing participles**: `标志着 / 见证了 / 奠定了基础`; `，推动着…… / 象征着…… / 确保了……`.
- **Hollow triads & promo adjectives**: Empty 3-item rhythm padding (`高效、稳定、安全`); `丰富的 / 迷人的 / 令人叹为观止的`. *(Keep real enumerations where every item adds distinct facts.)*
- **Formatting bloat & fuzzy attribution**: Bold lead-in labels (`**核心结论**：`), emojis (`✅ 🚀`), decorative `——`, `业界普遍认为 / 研究表明`, boilerplate uplifting endings (`未来可期`).

### Layer 3: Discourse & Structural Uniformity
Check structurally—**do not attempt arithmetic character counts or per-thousand-word ratios**:
- **Signposting / throat-clearing**: Delete meta-announcements (`先说结论`, `接下来从三方面分析`) and enter the content directly.
- **Symmetrical templates**: Break the pattern where every section has identical paragraph lengths, identical bullet structures, or ends with a punchy aphorism (`金句收尾`).
- **Overworked metaphors & decorative quotes**: State a metaphor once rather than tapping it at every section break; reserve `「」` / `""` for verbatim quotes, genuine technical terms on first use, or clear irony.

## Step 4: Positive Reconstruction Techniques

Deleting bad words leaves choppy stubs unless you rebuild with authentic Chinese syntax:

- **Person or event first (人/事坐主位)**: `他的收入的减少改变了他的生活方式` → `他收入减少，乃改变生活方式。`
- **Post-positioned modifiers (前饰改后饰)**: `我见到一个长得像你兄弟说话也有点像他的陌生男人` → `我见到一个陌生男人，长得像你兄弟，说话也有点像他。`
- **Chronological flowing clauses (流水句)**: Unpack stacked nominalizations into sequential verb clauses following natural cause or time order.
- **Flexible connectors (用活「而 / 并 / 乃」与零连接)**: Reserve `和 / 与` for noun lists; use `而` for smooth progression or contrast, or rely on clean juxtaposition.
- **Concise idioms over bloated calques (适度文白相济)**: Prefer `总而言之` over `总的来说`, `一言难尽` over `不是一句话能说清楚的`, `详加研究` over `进行了详细的研究`, `奉命` over `被指示`.

## Step 5: Output Modes & Final Cadence Check

Before delivering any edit, silently check your own draft for rhythm and self-contamination:
1. Do three consecutive sentences share nearly the same length or grammatical frame? Break one up.
2. Does any sentence force the reader to hold breath through stacked `的` or heavy pre-modifiers? Split or post-position it.
3. Did your rewrite accidentally reintroduce AI tics (`不是……而是……`, `值得注意的是`, `不仅……更……`, `标志着`)? Remove them.

Choose the response format matching the user's intent:

### Mode A: Direct Revision *(Default for daily high-intensity editing)*
Output two parts concisely:
1. **Revised Text (`改后正文`)**: Clean, ready-to-publish Chinese with all edits applied.
2. **Brief Revision Notes (`修订说明`)**: 3–5 bullet points highlighting the major structural fixes, plus any `[缺具体例证/来源，建议补充]` flags where empty fluff could not be replaced without inventing facts.

### Mode B: Diagnostic Audit *(When the user asks to review, diagnose, or explain without rewriting the full text)*
Output a compact table followed by optional holistic notes on discourse uniformity:

| 原句片段 | 归类与出处 | 诊断与最小改法 |
|---|---|---|
| User excerpt | e.g., `弱动词＋抽象名词（《常态》02）` or `现代 AI 腔：对偶否定` | State the reading friction and give 1–2 minimal rewrites preserving original meaning |

If the passage is already clear, natural, and free of meaningful friction, say so plainly without forcing unnecessary edits.