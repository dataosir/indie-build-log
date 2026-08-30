# ADR Concierge 验证清单 — 技术评审录音 → ADR 草稿

**用途：** Tier 3 候选 — Idea 5-D1（**只验证、不写产品**）  
**前置：** 无 GraalVM Gate 要求；建议每周 ≤4h，**不与 GraalVM Week 2–4 抢时间**  
**时间盒：** **14 天**，全程手工 Concierge  
**Last updated:** 2026-08-30

> 不卖「会议 AI」，只卖 **「评审录音 → 可进 repo 的 ADR markdown 草稿」**。  
> Otter 给摘要；你要验证的是 **ADR 结构 + 工程团队愿意付钱**。

---

## 0. 启动前快筛

- [ ] 能拿到 ≥3 段 **脱敏** 技术评审录音（15–45min，含架构讨论）  
- [ ] 能触达 ≥5 个 Staff Eng / Tech Lead / 架构师（英文或中文均可，优先 Global）  
- [ ] 接受 **0 代码** — 仅 Whisper + LLM prompt + 手工编辑  
- [ ] 通过线：**≥2 人愿意预付 $29/mo**（或 $49 一次性买 3 份）  
- [ ] CEO 确认：本验证 **不新开 repo**；通过后才有资格进 scorecard 正式打分  

---

## 14 天日程（勾选进度）

### Phase A — 样本制作（Day 1–4）

- [ ] **Day 1：** 定 ADR 输出模板（见下方 §模板）— 与 [adr.github.io](https://adr.github.io/) 对齐  
- [ ] **Day 2：** 选 1 段录音 → Whisper 转写 → 第一版 prompt 出 ADR 草稿  
- [ ] **Day 3：** 人工修订草稿至「可 PR」质量（标出 `[TBD]` 待决项）  
- [ ] **Day 4：** 再完成 2 份样本（共 3 份，覆盖不同场景：选型 / 迁移 / 技术债）  
- [ ] 每份样本附 **1 页 PDF 或 Notion**：原文摘要 vs ADR 草稿对比（给访谈对象看）  

**样本场景建议（至少覆盖 2 种）：**

| # | 场景 | 录音来源 |
|---|------|----------|
| 1 | 数据库选型（Postgres vs Dynamo） | 团队评审 / 模拟 |
| 2 | 服务拆分 / 单体迁移 | RFC 讨论 |
| 3 | 技术债偿还优先级 | 架构周会 |

### Phase B — 访谈 + Concierge 交付（Day 5–12）

- [ ] **Day 5：** 列出 15 目标人；发 cold DM / 社群帖（见 §招募话术）  
- [ ] **Day 5–8：** 完成 ≥5 场 20min 访谈（展示样本，不先推销）  
- [ ] **Day 8–11：** 对愿意试用的 ≥3 人，**免费交付 1 份** ADR 草稿（48h SLA）  
- [ ] **Day 11–12：** 交付后 24h 内问预付（Stripe Payment Link $29/mo 或 $49/3-pack）  

### Phase C — 判定（Day 13–14）

- [ ] 汇总指标表（§Gate 判定）  
- [ ] CEO Decision Log：Go / Pivot / Kill  
- [ ] 若 Go：复制 [`offer-one-pager-template.md`](offer-one-pager-template.md) → `offer-adr-draft-v1.md`  
- [ ] 若 Kill：归档至 scorecard backlog，**不编码**  

---

## 访谈脚本（20 分钟）

**开场：**  
「我在验证：技术评审会后，团队要不要一份 **直接能进 repo 的 ADR 草稿**。想听你们现在怎么记决策，不卖软件。」

**问题清单（每场勾选）：**

- [ ] Q1：你们有正式 ADR 流程吗？用啥工具？（Markdown / Confluence / 没有）  
- [ ] Q2：上次重要技术决策，会后多久才有书面记录？谁写？  
- [ ] Q3：看这份样本（展示 3 份之一）— 哪部分有用？哪部分不能用？  
- [ ] Q4：若 **上传录音 → 48h 内 ADR 草稿**，哪些场景会用？（选型 / 复盘 /  onboarding）  
- [ ] Q5：错误决策记录漏了，代价是什么？（返工、扯皮、新人不懂）  
- [ ] Q6：$29/mo 无限上传 vs $49 买 3 次 — 哪个更合理？  
- [ ] Q7：**愿意预付吗？**（当场发 Payment Link；「考虑一下」= 记 follow-up 日期）  

**禁止：** 承诺实时字幕、承诺整合 Jira/Linear、承诺 100% 准确（样本里保留 `[TBD]` 是 feature）

---

## ADR 输出模板（Concierge 交付格式）

```markdown
# ADR-NNN: [决策标题 — 动词短语]

**Date:** YYYY-MM-DD  
**Status:** Proposed | Accepted | [TBD]  
**Deciders:** [从录音提取，不确定标 TBD]  
**Consulted:** [...]

## Context
[问题背景 — 2–4 段，引用评审中的约束]

## Decision Drivers
- [驱动因素 1]
- [驱动因素 2]

## Considered Options
1. **Option A:** ... — Pros / Cons
2. **Option B:** ... — Pros / Cons

## Decision Outcome
**Chosen:** Option X  
**Because:** [...]

### Positive Consequences
- ...

### Negative Consequences
- ...

## Pros and Cons of the Options
[表格或列表]

## Links
- 评审录音时间戳 / 相关 PR / RFC [TBD]

---
*Draft generated from review recording — human review required before merge.*
```

**质量自检（交付前勾选）：**

- [ ] 有明确 **Decision Outcome**（不是会议摘要）  
- [ ] 至少 2 个 **Considered Options**  
- [ ] 不确定处标 `[TBD]`，不编造  
- [ ] ≤2 页 markdown（可进 repo）  

---

## Concierge 交付 SOP（单客户）

| Step | 动作 | SLA |
|------|------|-----|
| 1 | 客户发录音（Drive / 邮件，签署「仅用于生成 ADR」） | — |
| 2 | Whisper 转写 + LLM 按模板生成 v0 | 4h |
| 3 | 人工修订 30–60min | 24h |
| 4 | 交付 Notion / GitHub gist + 15min 可选 walkthrough | **48h** |
| 5 | 24h 后：预付询问 + Payment Link | — |

- [ ] 准备标准邮件模板（交付 + 预付询问）  
- [ ] 准备 Stripe Payment Link：$29/mo 或 $49 one-time（3 次）  

---

## Gate 判定（Day 14）

| 指标 | 通过线 | 实际 |
|------|--------|------|
| 完成访谈 | ≥5 | |
| 确认「会后 ADR 难写 / 拖延」痛点 | ≥3 人 | |
| 免费试用交付 | ≥3 份 | |
| 样本有用评分（1–5） | 均分 ≥3.5 | |
| **预付或书面付款承诺** | **≥2** | |

**结论（勾选一项）：**

- [ ] **Go** — 进入 scorecard 正式打分 + 考虑 2 周自动化 MVP（上传 → ADR，仍 **事后批处理**）  
- [ ] **Pivot** — 收窄场景（仅「架构选型」或仅「Incident → ADR」与 5-D2 合并）  
- [ ] **Kill** — 痛点真实但 WTP 不足；保留为 GraalVM 内容选题（「我们如何用 ADR 管 Native Image 决策」）  

---

## 招募话术（复制修改）

**英文 DM（r/engineering / LinkedIn）：**

```text
Quick research question — after tech review meetings, does your team
write ADRs? I'm testing a concierge service: upload a 30min recording →
ADR markdown draft in 48h. Looking for 5 eng leaders for a 20min chat.
Not selling yet — want to show you a sample. Interested?
```

**中文（技术社群）：**

```text
调研：你们技术评审会后，决策记录（ADR）谁写、多久能出？
我在手工验证「录音 → ADR 草稿」48h 交付，找 5 位 Tech Lead 聊 20 分钟，
给看样本，不涉及推销。有兴趣私信。
```

---

## 成本与边界（防止验证失控）

| 项 | 预算 |
|----|------|
| 本周工时上限 | **≤4h**（不含 GraalVM 主线） |
| Whisper + LLM / 3 份样本 | < $10 |
| 免费交付份数上限 | 3（第 4 份起收 $49 或拒绝） |

**不做：** 实时会议 bot、Slack 集成、Confluence 插件、小程序  

---

## 访谈笔记模板

```markdown
## ADR Interview — YYYY-MM-DD — [角色]

- 公司规模：__ 人工程团队
- 现有 ADR 流程：有/无 — 工具：
- 会后记录延迟：__ 天 / 经常没有
- 样本编号：1/2/3 — 评分（1-5）：
- 最有用段落：
- 不能用的地方：
- $29/mo WTP：高/中/低
- 预付：是/否
- 原话：
- Follow-up：
```

---

## 与主线关系

| 关系 | 说明 |
|------|------|
| GraalVM（Idea 1） | **无协同** — 验证排 GraalVM 访谈 / landing 之后 |
| Idea 5 录音管道 | **共享** Whisper + LLM pipeline；通过后勿另开「会议产品」 |
| Idea 5-D2 Incident | 若 ADR Kill 但「复盘」痛点强 → pivot 到 postmortem，见 [`stripe-webhook-alert-playbook.md`](stripe-webhook-alert-playbook.md) Tier 2 扩展 |

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`../01-market-research/idea-scorecard-2026-08-28.md`](../01-market-research/idea-scorecard-2026-08-28.md) | Idea 5-D1 backlog |
| [`../01-market-research/initial-brainstorming.md`](../01-market-research/initial-brainstorming.md) | Idea 5 拓展树 |
| [`tech-spike-template.md`](tech-spike-template.md) | 仅 Go 后自动化 spike |
| [`../01-market-research/business-framework.md`](../01-market-research/business-framework.md) | 硬过滤 / 打分 |
