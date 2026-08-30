# ICP 发现执行单 — 先找买家，再脑暴点子

**用途：** 每周循环 — 从「钱在流」的地方找 **买家（Buyer）**，再反推 wedge；**禁止**先脑暴功能再找用户  
**前置：** 无产品代码要求；可与 GraalVM 主线并行（用户侦察每周 ≤6h）  
**时间盒：** **7 天 / 轮**（可重复跑，直到 Gate 通过或 Kill）  
**Last updated:** 2026-08-30

> **用户 ≠ 买家。** 正确 ICP = 上周刚疼过 + 今天有信用卡 + 48h 内能对话的窄人。  
> 能挣钱的点子不是「想出来的」，是从 **已在付钱的人** 身上挖出来的。

**方法论背景：** [`01-niche-discovery-methodology.md`](01-niche-discovery-methodology.md)（四大水源）  
**打分门禁：** [`business-framework.md`](business-framework.md) §4 硬过滤 + 软打分  
**深度调研：** 通过后克隆 [`niche-research-template.md`](niche-research-template.md)

---

## 0. 启动前快筛（5 个 Yes 才开本轮）

- [ ] 本轮只验证 **1 个 ICP 假设**（不写功能清单）  
- [ ] ICP 能用 **一句话** 说完（见 §ICP 画布）  
- [ ] 能在 **48h** 内列出 ≥15 个可 DM / 回复的目标人  
- [ ] 领域优先 **Developer-adjacent**（与 Java / Spring / indie SaaS 有交集）  
- [ ] 接受 **先访谈后脑暴** — 本周 ≤6h 用户侦察，**不开新 repo**  

**任一 No → 先收窄 ICP，或归档到 [`initial-brainstorming.md`](initial-brainstorming.md) 沙盒。**

---

## 7 天日程（勾选进度）

### Phase A — 用户侦察（Day 1–2，不写代码）

- [ ] **Day 1 AM：** 写满 §ICP 画布（1 句 ICP + 当前支出 + 出现渠道）  
- [ ] **Day 1 PM：** Reddit / GitHub 收藏 **≥10 条痛帖**，摘录 **原话**（见 §搜索词清单）  
- [ ] **Day 2 AM：** 竞品差评采矿 **≥5 条**（G2 / PH / GitHub Issues）  
- [ ] **Day 2 PM：** 列出 **15 人触达名单** + 准备招募话术（§招募话术）  
- [ ] 完成 **48h 触达测试**（§触达测试）— 未通过则 **本周 Kill 该 ICP**  

### Phase B — 钱语言访谈（Day 3–5）

- [ ] **Day 3–5：** 完成 **≥5 场** 15–20min 访谈（每天 ≤2 场）  
- [ ] 每场用 §访谈脚本 — 重点问 **上周发生的事 + 已付的钱**  
- [ ] 每场结束 10min 内写 §访谈笔记  
- [ ] 若已有手工样本（Concierge），展示后问 **预付**（Stripe Payment Link）  

### Phase C — CEO 判定（Day 6–7）

- [ ] 填 §周 Gate 表  
- [ ] 勾选 Go / Pivot / Kill（§判定规则）  
- [ ] **Go：** 周末才写 wedge（1 工作流 × 1 输出物 × 1 价格）→ 进 scorecard / 克隆 niche template  
- [ ] **Kill：** 记入沙盒，**不脑暴功能**  

---

## ICP 画布（Day 1 必填，复制修改）

```text
【谁】_______________________________________________
     （例：Spring Boot 3 + Stripe 收款的 solo SaaS founder）

【何时痛】___________________________________________
     （例：上周 Native Image 编译失败，阻塞 Cloud Run 发布）

【现在怎么办】_______________________________________
     （例：Google 2h + 试 10 次 reflect-config + 回退 JVM）

【已在付什么】_______________________________________
     （例：AWS $80/mo + 自己时薪 $50/h × 4h = $200 隐性成本）

【愿付多少】_________________________________________
     （例：$29–49/mo，若省 1 次发布阻塞）

【在哪出现】_________________________________________
     （例：r/java、Spring GitHub Discussions、IH #saas）

【48h 能否 @ 到 5 人】 是 / 否
```

**收窄自检（从宽到窄）：**

| 层级 | 示例 | 可执行？ |
|------|------|:--------:|
| ❌ 太宽 | 「独立开发者」 | 否 |
| 🟡 还行 | 「用 Java 的独立开发者」 | 勉强 |
| ✅ 可执行 | 「Spring Boot 3 + Stripe，上周 webhook 失败过」 | 是 |
| ✅✅ 最佳 | 上面这类人里 **已在 Reddit/IH 发过抱怨帖的** | **优先 @** |

---

## 48h 触达测试（Day 2 必做）

| 步骤 | 动作 | 勾选 |
|------|------|:----:|
| 1 | 在目标社区搜 10 条近 90 天帖（见 §搜索词） | [ ] |
| 2 | 对其中 5 帖写 **有帮助的回复**（不卖产品） | [ ] |
| 3 | DM 或跟帖邀请 **15 人** 聊 15min | [ ] |
| 4 | **≥5 人** 同意预约或当场聊 | [ ] |

**未达 5 人 → ICP 太宽或渠道选错 → Pivot 收窄或 Kill，不进入访谈周。**

---

## 搜索词清单（复制到 Reddit / Google）

### Reddit（在目标 Sub 内搜索）

| 意图 | 搜索词 / 模式 |
|------|----------------|
| 已在付钱 | `"I pay"`, `"we pay"`, `"budget for"` |
| 找替代品 | `"alternative to"`, `"looking for tool"` |
| 具体痛 | `"how do you handle"`, `"anyone else"` |
| 阻塞 / 亏钱 | `"blocked deploy"`, `"lost revenue"`, `"webhook failed"` |
| 报错长尾 | 粘贴 **具体 error 前 8 词** + `site:reddit.com` |

**优先 Sub（Developer-adjacent）：**  
`r/java` · `r/springboot` · `r/aws` · `r/googlecloud` · `r/selfhosted` · `r/SaaS` · `r/solopreneur` · `r/indiehackers` · `r/devops` · `r/sre`

### GitHub

| 意图 | 搜索 |
|------|------|
| 活跃痛点 | `is:issue is:open "help wanted"` + 技术关键词 |
| 被拒需求 | 竞品 repo：`is:issue "wontfix" OR "not planned"` |
| 报错讨论 | `native image` / `reflect-config` / `webhook signature` |

### 竞品差评（G2 / PH / AlternativeTo）

- [ ] 收集 **1–3 星** 评价 ≥5 条  
- [ ] 归类：定价冲击 / 太重 / 缺单功能 / 支持慢  
- [ ] 每条标注：**愿付替代品的人可能在哪出现**  

---

## 访谈脚本（15–20 分钟）

**开场（30 秒）：**  
「我在调研 **[ICP 痛点]**，不卖软件，想听你们 **上周真实怎么处理的**。」

**问题清单（每场勾选）：**

- [ ] Q1：上次遇到 **[具体场景]** 是什么时候？发生了什么？  
- [ ] Q2：当时你怎么解决的？花了 **几小时**？谁参与？  
- [ ] Q3：你现在为类似问题 **付过什么**？（SaaS / 外包 / 自己的时薪）  
- [ ] Q4：不用任何新工具， **今天** 还会再发生吗？频率？  
- [ ] Q5：若有一个东西只做 **[单一结果]**，值多少钱？（让对方先出价）  
- [ ] Q6：$__ /mo vs $__ 一次性 — 哪个更合理？  
- [ ] Q7：**愿意预付吗？**（当场 Payment Link；「考虑一下」= 记 follow-up 日期）  

**算信号 vs 不算信号：**

| ✅ 算 | ❌ 不算 |
|-------|---------|
| 「我现在付 $X 给 Y」 | 「挺有意思」 |
| 「上周因为这个耽误了发布」 | 「有需要可以试试」 |
| 预付 / Payment Link 点击 | GitHub star |
| 「能介绍我同事吗」 | 「等做好了告诉我」 |

**禁止：** 先讲你的产品构想、功能列表、AI 能力；不要问「你会不会用 AI 秘书」这类泛问题。

---

## 招募话术（复制修改）

**英文 DM（Reddit / X / IH）：**

```text
Quick research — I'm talking to [ICP] who hit [specific pain] last month.
Not selling anything — 15min to hear how you handled it.
As thanks I can share [useful artifact: checklist / sample fix / teardown].
Open to a short call this week?
```

**中文（技术社群，若 ICP 在国内）：**

```text
调研：[具体痛点]，想了解大家上周真实怎么处理、现在用什么工具。
不卖产品，聊 15 分钟。我可以分享 [一份检查清单 / 样本] 作为感谢。
这周方便私信约时间吗？
```

**Reddit 公开回复（先帮后推）：**

```text
We hit this too. What worked for us: [1–2 concrete steps].
I'm researching how other [ICP] handle [pain] — if you're open to a 15min chat, DM me.
```

---

## 周 Gate 判定（Day 6–7 填表）

| 指标 | 通过线 | 实际 |
|------|--------|------|
| 痛帖原话收集 | ≥10 条 | |
| 完成访谈 | ≥5 | |
| 承认「上周发生过」 | ≥3 人 | |
| **钱语言**（I pay / I'd pay $X） | ≥2 人 | |
| 预付或书面付款承诺 | ≥2 | |
| 48h 触达测试 | ≥5 人愿聊 | |

**结论（勾选一项）：**

- [ ] **Go** — ≥2 预付 **或** ≥3 书面「发链接我就付」→ 周末写 wedge → [`niche-research-template.md`](niche-research-template.md) + scorecard  
- [ ] **Pivot ICP** — 有痛但无钱语言 → 收窄场景（见下方 Pivot 示例）→ 再跑 3 场访谈  
- [ ] **Kill** — 0 人承认痛 **或** 0 钱语言 → 沙盒归档，**不脑暴功能**  

**Pivot 示例（从宽 ICP 收窄）：**

| 原 ICP（Kill 风险） | Pivot 后 |
|---------------------|----------|
| 「独立开发者」 | 「Spring Boot + Stripe solo，webhook 失败过」 |
| 「需要会议 AI 的团队」 | 「Staff Eng，会后 ADR 经常拖延」 |
| 「想记录生活的用户」 | 「indie hacker 每周工作复盘」 |
| 「A 股交易者」 | 仅当验证 **纪律工具 WTP** — 通常与 Global USD 战略冲突 |

---

## 周末 wedge 模板（仅 Go 后填写）

```text
For: [窄 ICP 一句话]
Pain: [上周发生的具体事件]
Outcome: [单一可交付物 — 可 commit / 可执行 / 可付款恢复]
NOT for: [明确排除谁]
Price: $__/mo（或 $__ 一次性）
Channel: [一个主渠道 — 如 r/java 长尾 SEO]
```

**通过后下一步（选一条）：**

| 类型 | 文档 |
|------|------|
| 需写代码前验证 | [`../02-product-mvp/offer-one-pager-template.md`](../02-product-mvp/offer-one-pager-template.md) |
| Concierge 手工交付 | [`../02-product-mvp/adr-concierge-validation.md`](../02-product-mvp/adr-concierge-validation.md) |
| GraalVM 类技术 wedge | [`niche-graalvm-native-image-teardown.md`](niche-graalvm-native-image-teardown.md) |
| Stripe 运维类 | [`../02-product-mvp/stripe-webhook-alert-playbook.md`](../02-product-mvp/stripe-webhook-alert-playbook.md) |

---

## 每周 KPI（CMO 周日复盘勾选）

| 指标 | 目标 | 本周 |
|------|------|------|
| 合格对话（痛 + 预算） | ≥5 | |
| 钱语言出现次数 | ≥2 | |
| 新 ICP 48h 触达 | 5 人/轮 | |
| 无验证写代码 | ≤8h | |
| 新点子进沙盒 | 不限 | |
| 新点子开 repo | **0**（无 Gate 通过） | |

---

## 访谈笔记模板

```markdown
## ICP Interview — YYYY-MM-DD — [角色/公司规模]

- ICP 假设：________________
- 上次痛点发生：__ （多久前）
- 当前解法：________ — 耗时：__ h
- 已在付：________ ($__/mo 或 隐性时薪)
- 愿出价：$__/mo — WTP：高/中/低
- 预付：是/否/考虑中（follow-up：__）
- 原话（粘贴）：
- 可介绍他人：是/否
- Pivot 提示：
```

---

## 反模式速查（脑暴前先对照）

| 反模式 | 症状 | 对照例子 |
|--------|------|----------|
| 用户 = 所有人 | 48h 触达不到 5 人 | Idea 4 秘书、Idea 6 生活 KB |
| 先功能后脑暴 | 访谈前已有 10 个 feature | 秘书 → 知识库 → 全场景膨胀 |
| 兴趣 ≠ 钱 | 5 场访谈 0 句「I pay」 | validation theater |
| 维他命定价 | 用户说「有了更好」 | 通用日程 / 生日提醒 |
| 渠道与收款错位 | 国内 C 端 + Stripe USD | 小程序生活 OS |
| 并行开 repo | 本周又写新 MVP | roadmap：并行产品线 ≤1 |

---

## 与主线关系

| 场景 | 建议 |
|------|------|
| **GraalVM Week 2–4** | ICP 已相对清晰 → 本 playbook 用于 **验证付钱**，每周用户侦察 ≤6h |
| **新沙盒点子** | 必须先跑完 **一轮 7 天** 再进 scorecard |
| **TEA / A 股** | 可触达买家，但通常 **非 USD 买家** — 单独 ICP，不与 Micro-SaaS 混排 |
| **ADR / Stripe Tier 2–3** | 各 playbook 内访谈脚本 **继承本单 Q1–Q7** |

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`business-framework.md`](business-framework.md) | 漏斗 Gate、硬过滤、软打分 |
| [`idea-scorecard-2026-08-28.md`](idea-scorecard-2026-08-28.md) | Go 后正式打分 |
| [`initial-brainstorming.md`](initial-brainstorming.md) | Kill / raw 点子沙盒 |
| [`../03-growth-and-automation/distribution-channels.md`](../03-growth-and-automation/distribution-channels.md) | Reddit 30 天节奏、BIP |
| [`../02-product-mvp/adr-concierge-validation.md`](../02-product-mvp/adr-concierge-validation.md) | Tier 3 Concierge |
| [`../02-product-mvp/stripe-webhook-alert-playbook.md`](../02-product-mvp/stripe-webhook-alert-playbook.md) | Tier 2 垂直验证 |

---

*先找买家，再脑暴。每周日复盘：无钱语言 → Kill early.*
