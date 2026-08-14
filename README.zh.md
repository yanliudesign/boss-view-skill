[English](./README.md) · 中文

# 👔 老板视角汇报 · Boss View

把零散的工作记录，变成老板能快速看懂进展、影响、风险与所需支持的 Executive Update。

[![Version](https://img.shields.io/badge/VERSION-1.0.0-2ea44f?style=flat-square&labelColor=333)]()
[![Stars](https://img.shields.io/github/stars/yanliudesign/boss-view?style=flat-square&label=STARS&color=e37f2c&labelColor=333)](https://github.com/yanliudesign/boss-view/stargazers)

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-d97757?style=flat-square&labelColor=1a1a1a&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![GitHub Copilot](https://img.shields.io/badge/GitHub_Copilot-Skill-8957e5?style=flat-square&labelColor=1a1a1a&logo=githubcopilot&logoColor=white)](https://github.com/features/copilot)
[![Codex](https://img.shields.io/badge/Codex-Skill-2ea44f?style=flat-square&labelColor=1a1a1a)]()

这是一个用于周报、工作汇报、Manager Sync、1:1 和项目进展同步的 Agent Skill。你只需要丢进一段顺序混乱、甚至不完整的工作记录，它会从老板 / Manager / Executive 的视角重新组织信息，并自动生成一份可导出 PDF / Markdown 的单文件 HTML 报告。

它不会把“忙”包装成“有价值”，也不会编造缺失的数据。没有证据的地方，会明确标注需要补充。

```text
零散记录                         老板视角
───────────────────────────      ───────────────────────────
“开了 5 个会，改了 3 版”     →   推进了什么结果
“转化率还是比较低”           →   有什么业务风险
“下周准备增加 tutorial”      →   接下来做什么
“需要老板帮忙协调资源”       →   需要什么支持
```

## 30 秒开始使用

安装后，直接把零散记录贴进 Claude Code 或 VS Code 对话：

> 帮我整理成老板视角的周报：这周和工程师一起改了 onboarding，试了三个版本，发现很多新用户不知道怎么使用 Skill，下周准备增加 tutorial。

也可以自然地说：

- “帮我写一下这周的 weekly update。”
- “从老板视角重写这段工作汇报。”
- “把这些笔记整理成简洁的 1:1 update。”
- “这段周报太像流水账了，帮我突出 impact。”

也可以点名汇报对象，让重点随角色变化：

> 把这份 update 改成写给 CPO 看的版本。

## 选择汇报对象

Boss View 内置 6 种决策视角。选择角色会改变信息优先级、可能的追问、风险表达和 Ask，但绝不会改变底层事实。

| 汇报对象 | 优先关注 |
| --- | --- |
| **CEO** | 战略、增长、资源配置、机会成本 |
| **CPO** | 用户价值、产品判断、学习速度、采用率 |
| **CTO** | 技术风险、依赖、可靠性、可扩展性 |
| **VP Design** | 用户洞察、体验质量、设计判断、跨团队推进 |
| **VP Product** | 产品方向、优先级、路线图影响、市场信号 |
| **Direct Manager** | 执行进度、交付风险、个人 ownership、所需支持 |

如果用户未指定对象，也无法从上下文可靠判断，则默认使用 **Direct Manager**，并在可复制正文之外说明这一假设。不会把 6 个角色混成一份面面俱到、没有重点的通用汇报。

## 你会得到什么

每次汇报都会围绕同一条 Executive Narrative 组织：

1. **Executive Summary** — 用 2–3 句话说清进展、影响和下一步
2. **Key Wins** — 只保留最值得老板关注的成果
3. **Business Impact** — 在有依据时，连接收入、增长、采用率、效率、客户体验或风险降低
4. **Challenges / Risks** — 区分真正的 Blocker、Risk、Dependency 和 Open Question
5. **Next Steps** — 提炼优先动作；用户提供时才写 Owner 和 Timeline
6. **Ask** — 明确需要老板决策、给资源、协调团队、提供方向或解除阻塞
7. **Manager Questions** — 预测 3–5 个老板最可能追问的问题，并提供回答建议
8. **Copy-ready Version** — 可直接贴进 Slack、Email、Notion、周会或 1:1 的最终版本

同一份内容还会使用 Offer Toolkit 的视觉系统组装成正式 HTML 报告：cream paper、强层级、决策前置摘要、打印友好的卡片、双语内容和固定导出工具栏。

没有有效信息的部分可以省略。如果没有明确 Ask，会写 **No immediate action needed.**，不会为了格式完整而虚构需求。

## 五步工作法

```text
1  提取信息    What · Why · Result · Metrics · Challenge · Impact · Next · Ask
2  老板重构    不照搬原始顺序，按管理者关心的问题重新排序
3  结构化      生成 Executive Update，把结果与活动量分开
4  预测追问    预判 3–5 个最可能出现的 Manager Questions
5  最终交付    输出简洁、专业、可直接复制的完整版本
```

核心转换只有一句话：

> **从“我做了什么”，转向“什么被推进了、为什么重要、接下来会怎样”。**

## 改写前后

**原始输入**

> 这周开了 5 个会，改了 3 版设计，和工程师讨论了很多细节。

**只换一种说法，还不够**

> 本周完成 5 次会议并迭代 3 版设计。

**老板视角**

> Aligned Design and Engineering on the new onboarding flow and moved the project toward implementation.

会议数量不是重点。真正值得汇报的是：做成了什么决定、推动了什么进展、带来了什么业务结果。

## 四条原则

1. **绝不编造** — 数字、结果、客户反馈和商业影响必须来自用户输入。
2. **结果优先于活动量** — 会议、文档和迭代只有在解释“推进了什么”时才值得出现。
3. **先基于现有信息出初版** — 即使输入很短、很乱，也先给出可用结果；之后最多追问 3 个关键问题。
4. **保留用户真实语气** — 普通团队 update 不应被写成 CEO 演讲。Clear > Concise > Impactful > Authentic。

## 语言规则

国际职场语境下，Copy-ready Version 默认使用英文；如果用户明显处于中文语境，或明确要求中文，则整份汇报使用中文。解释和补充问题跟随用户使用的语言。

## 安装

把仓库克隆到本地：

```bash
git clone https://github.com/yanliudesign/boss-view.git
```

Claude Code：

```bash
mkdir -p ~/.claude/skills
cp -R boss-view ~/.claude/skills/boss-view
```

VS Code 用户可以把整个文件夹放入自己的 prompts / skills 目录，再从 Copilot Chat 触发。具体目录可能因本地配置而异。

## 文件结构

```text
boss-view/
├── SKILL.md                         # 工作流与输出规则
├── examples/
│   └── executive-update-template.html # 单文件 HTML 报告模板
├── references/
│   ├── executive-lenses.md          # 6 种汇报对象决策视角
│   └── executive-report-spec.md     # HTML 生成与校验规则
├── README.md                        # English documentation
└── README.zh.md                     # 中文文档
```

## 什么样的输入最有帮助

不需要提前整理格式，直接提供以下素材即可：

- 一周的工作笔记，或一段想到哪写到哪的项目 update
- 上线、决策、实验、用户反馈和跨团队协作结果
- 有上下文、可以解释意义的数据
- 阻塞项、依赖、开放问题和关键取舍
- 下一步、负责人、时间，以及需要管理层提供的支持

缺失的信息会被标记为待补充，不会用虚构事实填满。

## 相关链接

- [SKILL.md](./SKILL.md) — 完整工作流与输出规则
- [Executive audience lenses](./references/executive-lenses.md) — 各角色的信息优先级、追问与 Ask
- [Executive report template](./examples/executive-update-template.html) — 单文件 HTML 报告骨架
- [yanliudesign on GitHub](https://github.com/yanliudesign) — 更多 Agent Skills 与设计工具

Created by [Dreameryanyan](https://www.linkedin.com/in/yanliudesign/) · [LinkedIn](https://www.linkedin.com/in/yanliudesign/) · [X](https://x.com/yanliudreamer) · [Xiaohongshu](https://www.xiaohongshu.com/notification)