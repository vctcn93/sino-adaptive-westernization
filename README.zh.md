<p align="center">
  <picture>
    <source srcset=".github/assets/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src=".github/assets/logo-light.svg" alt="善性西化" width="340">
  </picture>
</p>

<p align="center">中文写得别扭，多半是里头立着英文的骨架。这个技能把它拆掉。</p>

<p align="center"><sub>数能化 出品</sub></p>

<p align="center">
  <a href="LICENSE"><img alt="许可" src="https://img.shields.io/github/license/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
  <a href="https://github.com/vctcn93/sino-adaptive-westernization/releases"><img alt="版本" src="https://img.shields.io/github/v/release/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
  <a href="SKILL.md"><img alt="格式" src="https://img.shields.io/badge/format-SKILL.md-blue?style=flat-square"></a>
  <a href="https://github.com/vctcn93/sino-adaptive-westernization/stargazers"><img alt="星标" src="https://img.shields.io/github/stars/vctcn93/sino-adaptive-westernization?style=flat-square"></a>
</p>

<p align="center"><a href="README.md">English</a> | 简体中文</p>

---

## 它能解决什么问题？

一个把中文修改得更符合中文习惯的Skill。两类毛病分两个文件放，因为出处不同。

规则提炼自余光中三篇文章：《中文的常态与变态》、《从西而不化到西而化之》和《论中文之西化》，它们共同判定一个句子是否地道，坏在哪里。三篇合起来，模型才拿到一个它本来没有的东西：判断一句中文坏在哪，光看它少见还不够。

第二类不是他的，是 2023 年以后编辑们围着转的那批：机器写中文留下的破绽。那个文件里没有一句话从余光中那儿借来。

语域先定，而且它决定这两套各出几分力。公文论文留住术语和被动，专栏散文按最严的来。

| # | 规则 | 信号 | 英文来源 | 改前 | 改后 | 治什么摩擦 |
|---|---|---|---|---|---|---|
| 1 | 弱动词 + 抽象名词 | 作出 / 进行 / 加以 | make a response, take action, conduct a study（余光中拆过） | 作出了十分热烈的反应 | 反应十分热烈 | 假动作撑着空名词 |
| 2 | 抽象名词占主位 | ……的提升 / 减少 / 推进 | nominalization as subject: the reduction of his income（余光中拆过） | 他的收入的减少改变了他的生活方式 | 他收入减少，乃改变生活方式 | 得先拆开名词才看见人 |
| 3 | `的`字堆叠 / 头重脚轻 | 一句三个以上`的` | relative clauses crammed before the head noun（余光中拆过） | 我见到一个长得像你兄弟说话也有点像他的陌生男人 | 我见到一个陌生男人，长得像你兄弟 | 核心名词迟到，读到就忘 |
| 4 | 假术语后缀 | ……性 / 型 / 度 / 化 / 主义 | -ness, -ity, -ization, -ism（余光中拆过） | 具有很高的知名度 | 很有名 | 给普通形容词披学术衣 |
| 5 | `之一` 与假精确 | ……之一 / 最……之一 | one of the greatest …（余光中拆过） | 李白是中国最伟大的诗人之一 | 李白是中国极伟大的诗人 | 用假精确换安全感 |
| 6 | 机械`被`字句 | 被 / 被……所 | be + past participle（余光中拆过） | 我不会被你这句话吓倒 | 你这句话吓不倒我 | 施动者藏起来，力气也走了 |
| 7 | 空转介词框架 | 关于 / 对于 / 由于……使得 | as for, regarding, owing to … so that（余光中拆过） | 由于他的家境贫穷，使得他只好休学 | 他家境贫穷，只好休学 | 框架占半句不带信息 |
| 8 | 冗余副词 / 存在句 | 成功地 / 存在着 | successfully + verb, there is（余光中拆过） | 成功地推翻了满清 | 推翻了满清 | 动词已含结果，副词白加 |
| 9 | 硬凑`和 / 及`、冗余`们` | 和 / 与 / 及 挂在形容词上；人们 | and 连形容词；英文复数 -s → 们（余光中拆过） | 起步更早及迈步更快 | 起步更早而迈步更快 | 连词当万能胶 |
| 10 | 时间条件外框 | 当……的时候 / 之后 | when …, after …（余光中拆过） | 当你把稿子写好了之后，立刻寄出去 | 你稿子一写好，立刻寄出去 | 语序已交代先后，框多余 |
| 11 | 动词与宾语隔太远 | 动词 + 长定语 + 的 + 宾语 | a heavy relative clause parked before the object（余光中拆过） | 我决不原谅任何事先没有得到我的同意就擅自引述我的话的人 | 任何人事先没有得到我同意就擅自引述我的话，我决不原谅 | 读到宾语时动词已丢 |
| 12 | 无来由的对偶否定 | 不是X，而是Y | not X but Y（你点名要的这条） | 好工具不是用来治措辞的，而是用来治骨架的 | 好工具治的是骨架 | 先立假靶子再打 |
| 13 | 黑话动词 | 实现……提升 / 赋能 / 打造 | empower, drive, enable, provide support for（推断） | 该架构为高并发场景下的系统稳定性提供了强有力的支撑 | 这套架构在高并发下更稳 | 具体动作变口号，没法验证 |
| 14 | 思维拐杖 | 值得注意的是 / 本质上 | it is worth noting that, essentially（推断） | 值得注意的是，缓存穿透往往发生在高频查询场景下 | 高频查询很容易引发缓存穿透 | 过渡垫片拖慢阅读 |
| 15 | 意义镀金 | 标志着 / 奠定了坚实基础 | marks a milestone, lays a solid foundation（推断） | 此次协议的签署标志着双方合作迈出了具有里程碑意义的一步 | 双方签了协议，正式启动合作 | 宏大叙事替具体事实 |
| 16 | 句尾分词腔 | ，推动着…… / ，象征着…… | a trailing -ing clause（推断） | 新平台整合了多方数据，推动着行业向智能化转型 | 新平台打通了多方数据 | 把 -ing 尾巴抄过来 |
| 17 | 三段式凑数 | 高效、稳定、安全 | the tricolon, English copywriting's rule of three（推断） | 新方案全面、高效、稳定 | 新方案运行稳，能替企业省钱提效 | 为节奏凑数 |
| 18 | 宣传形容词 + 模糊归因 | 丰富的 / 业界普遍认为 | vibrant, rich, experts say, studies show（推断） | 业界普遍认为，微调更适合垂直领域 | 在垂直领域，微调往往更稳妥。[缺具体评测或出处] | 借没名字的权威 |
| 19 | 格式拐杖 + 鸡血结尾 | **核心结论**： / emoji / 未来可期 | bold lead-ins, emoji, the future looks bright（推断） | **核心结论**：这套流程能帮团队省下一半时间。未来可期 | 这套流程能替团队省下一半时间 | 装饰替句子使劲 |
| 20 | 报幕句 | 接下来我们将 / 下面从三个方面 | in this section we will …（推断） | 接下来我们将从三个方面来分析缓存问题 | 缓存问题主要有三种表现。随后直接进内容 | 先说要说的人比说的多 |
| 21 | 过度隐喻 + 装饰引号 | 「全链路」「闭环」 | scare quotes（推断） | 打通「全链路」的「闭环」 | 打通整条流程 | 引号当概念重量 |
| 22 | 匀质段落 + 金句收尾 | 每节结构相同 / 每段一记重拳 | symmetrical structure, punchline copywriting（推断） | 每小节都以「效率，才是流程的终点」收尾 | 收在最后一条事实或逻辑转折上 | 像模板不像人写 |

## 安装方式

```bash
# Claude Code
git clone https://github.com/vctcn93/sino-adaptive-westernization \
  ~/.claude/skills/sino-adaptive-westernization

# 其他 harness 从各自的技能目录读同样的结构
# 手动装：整个文件夹丢到 agent 读技能的那个位置
```

> [!TIP]
> 装完重启会话，或者敲 `/reload`，技能清单才会刷新。

## 文件组织与调用方式

```text
sino-adaptive-westernization/
├── SKILL.md                      规则、语域、护栏、三层扫描
└── references/
    ├── yu-syntax-catalog.md      十一病，按篇目节次标注
    └── ai-rhetoric-patterns.md   AI-01 到 AI-11，修法不编事实
```

`SKILL.md` 只在需要的时候才展开参考文件：做完整审校，碰到边界情况，或者要核对一条引用。

| 你这么说 | 它干什么 |
|---|---|
| 帮我改改这段中文 / 读着别扭 / 有翻译腔 | 用法 A：给改后正文，附结构说明 |
| 别改，先审 / 哪儿 AI 味重 / 逐条标出处 | 用法 B：一张表，列原句、归类、最小改法 |
| *polish this Chinese / does this read machine-written* | 两种都行，规则一样 |

```text
把这段改成正常中文：<稿子>
别改，先审：这段哪些句法西化、哪些是 AI 腔？逐条标出处。
```

五步，顺序不变：定语域，过护栏，三层扫，重构，然后回头查自己的稿子有没有同样的毛病。

## 许可

MIT，全文见 [LICENSE](LICENSE)；
纪念余光中先生。
