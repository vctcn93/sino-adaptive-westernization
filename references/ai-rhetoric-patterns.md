# Modern AI Rhetoric & Structural Uniformity Patterns

> **Scope & Provenance**: The patterns below are modern editorial criteria targeting habits common in LLM-generated Chinese prose. They are **not** sourced from Yu Guangzhong's 1970s–1980s essays (with the sole borrowing of Yu's observation on `而` in `《常态》03` as a repair tool).

---

## Part I: High-Frequency AI Rhetorical Clichés

### AI-01: Unprompted Binary Negation (`不是 X，而是 Y` / `not X but Y`)
- **Signals**: `不是 X，而是 Y`、`并非 X，是 Y`、`不再是……而是……`、`与其说 X，不如说 Y`、`X 不是问题，Y 才是`
- **Why it hurts**: LLMs overuse English *not X, but Y* as an artificial dramatic pivot—inventing a strawman position X just to knock it down before stating Y.
- **When to keep**: Keep only when the reader genuinely holds misconception X and needs it cleared before moving on.
- **Repairs**:
  1. Delete the negated half and state Y directly.
  2. Replace with direct contrast or `而` (`《常态》03`: `而` carries both *and* and *but*).
- **Example**:
  - *Before*: `好工具不是用来治措辞的，而是用来治骨架的。`
  - *After*: `好工具治的是骨架。` *(Or, if contrasting explicitly: `好工具重在调骨架，不在雕琢表面措辞。`)*

### AI-02: Modern Buzz-Verbs & Action Inflation
- **Signals**: `实现……的提升 / 突破`、`提供……的支持 / 支撑`、`发挥……的作用`、`带来……的体验`、`赋能`、`助力`、`打造`、`构建……体系`、`驱动`
- **Why it hurts**: Corporate jargon combined with weak-verb structure turns concrete actions into bloated abstractions.
- **Repairs**: Name what actually happens using plain transitive verbs (`加快`, `稳住`, `帮`, `建`, `省`).
- **Example**:
  - *Before*: `该架构为高并发场景下的系统稳定性提供了强有力的支撑，实现了处理效率的显著提升。`
  - *After*: `这套架构在高并发下更稳，处理也更快。`

### AI-03: Thinking Crutches & Meta-Transitions
- **Signals**: `值得注意的是`、`需要指出的是`、`事实上`、`本质上`、`归根结底`、`换句话说`、`毫无疑问`、`综上所述`、`由此可见`
- **Why it hurts**: Models generate transition pads while "steering" into the next clause. In finished prose, they signal insecurity and slow the reader down.
- **Repairs**: Delete the transition pad outright; let the insight stand on its own. Keep `事实上` or `换句话说` only when genuinely reversing a prior assumption or re-explaining a dense concept.
- **Example**:
  - *Before*: `值得注意的是，缓存穿透往往发生在高频查询场景下。本质上，这是架构设计不足导致的。`
  - *After*: `高频查询很容易引发缓存穿透，根子往往在架构设计。`

### AI-04: Significance Inflation (`意义镀金`)
- **Signals**: `标志着`、`见证了`、`是……的最好证明`、`具有里程碑意义`、`奠定了坚实基础`、`开启了……的新时代`
- **Why it hurts**: Substitutes grand historical framing for concrete facts.
- **Repairs**: Cut the inflated clause. If the original text contains concrete next steps or effects, state those plainly; **never invent specifics not present in the source**.
- **Example**:
  - *Before*: `此次协议的签署标志着双方合作迈出了具有里程碑意义的一步，为未来的生态共赢奠定了坚实基础。`
  - *After*: `双方签了协议，正式启动合作。` *(If concrete deliverables exist in the source, state them here instead.)*

### AI-05: Trailing Participle Clauses (`句尾分词腔`)
- **Signals**: `，象征着……`、`，反映着……`、`，推动着……`、`，确保了……`、`，彰显了……`
- **Why it hurts**: Copies English trailing `-ing` / `-ed` clauses (`..., symbolizing...`, `..., thereby ensuring...`) onto the tail of a finished Chinese sentence, turning an assertion vague.
- **Repairs**: End the sentence cleanly at the main verb, or split the consequence into a separate sentence with a concrete subject.
- **Example**:
  - *Before*: `新平台整合了多方数据，打破了信息孤岛，推动着行业向智能化转型。`
  - *After*: `新平台打通了多方数据。` *(If the text specifies concrete operational changes resulting from this, state them in a new sentence.)*

### AI-06: Hollow Triads (`三段式凑数`)
- **Signals**: Rapid three-item noun/adjective chains (`高效、稳定、安全`; `降本、增效、提质`; `全面、深入、系统`) stacked purely for cadence.
- **Exemption (Critical)**: **Never collapse genuine checklists, technical specs, metrics, or distinct items** (e.g., `延迟、吞吐量、丢包率` or three distinct arguments) just to avoid three-item lists.
- **Repairs**: When items overlap or merely pad rhythm, merge or keep only the distinct, verifiable points.
- **Example**:
  - *Before*: `新方案全面、高效、稳定，助力企业降本、增效、提质。`
  - *After*: `新方案运行稳，能替企业省钱提效。`

### AI-07: Promotional Adjectives & Fuzzy Attribution
- **Signals**:
  - *Promo bloat*: `丰富的`、`迷人的`、`令人叹为观止的`、`充满活力的`、`独一无二的`、`必访之地`
  - *Fuzzy authority*: `业界普遍认为`、`多项研究表明`、`专家指出`、`有分析称`
- **Repairs**:
  - If the source contains concrete features or named experts/studies, bring those facts forward.
  - **If no concrete facts or named sources exist in the input**, delete the empty wrapper or flag `[缺具体例证/来源，建议补充]`. Do **not** invent scenery, metrics, or dates.
- **Example**:
  - *Before*: `业界普遍认为，微调比单纯改提示词更适合垂直领域。`
  - *After*: `在垂直领域，微调往往比单纯改提示词更稳妥。[缺具体评测或出处，建议补充]`

### AI-08: Formatting Crutches & Uplifting Boilerplate Endings
- **Signals**:
  - Bold lead-ins inside narrative prose (`**核心痛点**：`), check/rocket emojis (`✅ 🚀 💡`), excessive em-dashes (`——`) used as dramatic pauses.
  - Closing cliches (`未来可期`, `书写更加辉煌的篇章`, `携手共进`, `迈向新征程`).
- **Repairs**: Strip formatting crutches so sentence structure carries the emphasis; end abruptly on the last concrete takeaway or genuine next step from the text.
- **Example**:
  - *Before*: `**核心结论**：🚀 这套流程——毫不夸张地说——能帮团队省下一半时间。未来可期，让我们共同开启高效办公的新篇章！`
  - *After*: `这套流程能替团队省下一半时间。`

---

## Part II: Structural Uniformity Patterns (Discourse Level)

Evaluate these holistically by reading section-to-section flow—do not invent character quotas or numeric thresholds.

### AI-09: Signposting & Throat-Clearing (`报幕句`)
- **Symptom**: Paragraphs opening with announcements of what the writer is about to say (`接下来我们将探讨……`, `在展开之前，先交代背景`, `下面从三个方面来看`).
- **Repair**: Delete the announcement and start directly with the substance.

### AI-10: Overworked Metaphors & Decorative Quotes
- **Symptom**: Repeating the same governing metaphor (`手术 / 病灶`, `护城河`, `拼图`, `抓手`) at every transition or section ending; wrapping ordinary words in `「」` or `""` (`实现了「全链路」的「闭环」`) to manufacture conceptual weight.
- **Repair**: Introduce a metaphor once (or bookend opening and closing) and let literal prose carry the middle. Strip quotation marks from everyday words; reserve quotes for direct speech, newly defined domain terms, or clear irony.

### AI-11: Uniform Paragraphs & Aphorism-Every-Section Closers (`金句收尾`)
- **Symptom**: Every section follows an identical visual blueprint (short hook → three bullets → pithy one-liner aphorism at the end), or almost every paragraph sits at the exact same two-to-three-sentence length.
- **Repair**:
  - Let prose density follow complexity: merge fragmented micro-paragraphs when developing a continuous argument, and leave factual sections short without forcing a dramatic closing punchline.
  - Keep at most one or two truly earned closing lines across an essay; end ordinary sections directly on the final fact or logical bridge.