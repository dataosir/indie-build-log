# Stripe Webhook 专报 — 验证与 MVP 执行单

**用途：** Tier 2 候选 — Idea 3 垂直化 + Idea 4-D4 合并（「Indie Java 站长运维助手」第一 SKU）  
**前置：** GraalVM（Idea 1）已过 **Gate B**（≥1 付费 **或** ≥3 书面预付意向）**或** Day 60 复盘后 CEO 书面批准  
**时间盒：** 验证 2 周 → MVP 2–3 周（仅当验证通过）  
**Last updated:** 2026-08-30

> 不卖「监控平台」，只卖 **「Stripe webhook 失败 → 人话解释 + 建议动作」**。  
> 叙事避开「AI 秘书」— 卖可执行的运维结果。

---

## 0. 启动前快筛（5 个 Yes 才开本 playbook）

- [ ] GraalVM 主线未因本线而暂停访谈 / landing / 交付  
- [ ] 能在 48h 内触达 ≥5 个「Spring Boot + Stripe 收款」的 indie / 小团队  
- [ ] Stripe 账户可收 USD（与 GraalVM 共用即可）  
- [ ] 愿意定价 **$29–49/mo**（$9 通用监控不做）  
- [ ] CEO 书面记录：**并行产品线 ≤ 1** — 本线仅在 Gate B 后启动  

**任一 No → 留在 scorecard backlog，不写代码。**

---

## Week 1 — Concierge 验证（零产品代码）

### Day 1–2：样本与话术

- [ ] 收集 **3 份脱敏** webhook 失败场景（自己的项目 / 朋友许可 / 公开 gist）  
- [ ] 手工写 3 份「专报」样本（Telegram 消息格式，≤200 字 + 3 条 action items）  
- [ ] 完成 Offer 一句话（填入下方）  

```text
For: Solo / small-team Java founders using Stripe
Pain: Webhook failures silently lose revenue; grep logs at 2am
Outcome: Morning Telegram digest — what failed, why, what to check first
Price: $39/mo (or $49/mo annual)
NOT for: Teams already on Datadog/PagerDuty with dedicated SRE
```

- [ ] 列出 15 个目标联系人（indie hackers、r/SaaS、Spring 社群、个人网络）  
- [ ] 预约 ≥5 次 20min 访谈（Calendly / DM）

### Day 3–5：访谈（每天 ≤2 场，每场记笔记）

**开场（30 秒）：**  
「我在调研 Stripe webhook 失败时，Java 站长怎么发现、怎么修。不卖东西，想听你的真实流程。」

**核心问题（勾选已问）：**

- [ ] Q1：上次 Stripe webhook 失败是什么时候？花了多久发现？  
- [ ] Q2：你现在怎么监控？（Actuator / 日志 / 什么都没有）  
- [ ] Q3：失败时典型根因是什么？（签名、超时、幂等、部署窗口）  
- [ ] Q4：若每天早上有一条 Telegram：**失败笔数 + 可能原因 + 检查清单**，值多少钱？  
- [ ] Q5：$39/mo 自动发 vs 免费自己 grep — 差在哪？  
- [ ] Q6：愿意 **预付 $39 试用 2 周** 吗？（当场 Stripe Payment Link 或「我发 invoice」）  

**每场结束后 10 分钟内：**

- [ ] 笔记写入 Notion / `docs/04-indie-log/daily-logs/`  
- [ ] 标注：WTP（高/中/低）、当前工具、是否愿意预付  

### Day 6–7：判定 Gate

| 指标 | 通过线 | 实际 |
|------|--------|------|
| 完成访谈 | ≥5 | |
| 确认「昨晚 webhook 挂过」痛点 | ≥3 人 | |
| 愿意预付 / Payment Link 点击 | ≥2 | |
| 样本专报「有用」评分（1–5） | 均分 ≥4 | |

**结论（勾选一项）：**

- [ ] **Go → Week 2 MVP**（≥2 预付或 ≥3 书面「发链接我就付」）  
- [ ] **Pivot offer**（改价格 / 改载体 / 改「仅签名失败」子场景）— 再跑 3 场访谈  
- [ ] **Kill / 合并回 Idea 3 沙盒** — 记入 Decision Log，不写代码  

---

## Week 2–3 — MVP（仅 Go 后执行）

### 范围铁律（禁止膨胀）

| 做 | 不做 |
|----|------|
| Spring Boot Starter：读 webhook 相关日志 / 端点健康 | 通用 APM、全量 Prometheus |
| Stripe 签名失败、5xx、超时、重复事件 四类 | MRR 图表、Baremetrics 竞品功能 |
| Telegram 每日摘要 + **即时**失败推送 | Email 为主、Slack 集成 v1 |
| 单租户、单 Stripe account | 多租户 SaaS 控制台 |

### CTO 任务清单（时间盒 2–3 周）

**Week 2**

- [ ] Spike ≤8h：Actuator + 应用日志能否可靠识别 Stripe webhook 失败（用 3 份样本验证）  
- [ ] `spring-boot-starter` 骨架：依赖注入 + 配置项 `stripe.webhook.path`  
- [ ] Telegram Bot：失败即时推送 + 每日 08:00 digest（cron）  
- [ ] README：5 分钟接入（`application.yml` 示例）  
- [ ] 给 Week 1 预付用户手动部署 1 台（Concierge 交付）  

**Week 3**

- [ ] 处理 2 个真实用户的 edge case（各 ≤4h）  
- [ ] Landing 子页或独立单页：价格 $39/mo + Stripe Payment Link  
- [ ] Fulfillment：付款后 48h 内发 jar + 配置文档  
- [ ] 退款政策写清（7 天无理由 OK）  

### CMO 任务清单（与 CTO 并行）

- [ ] 1 篇 Reddit「How I debug Stripe webhooks on Spring Boot」（带专报截图，非硬广）  
- [ ] 3 条 X thread：真实失败故事 + 「我做了个 digest bot」  
- [ ] 更新 scorecard：Idea 3 垂直化重新打分  

---

## 定价与 SKU（v1 单 SKU）

| 档位 | 价格 | 包含 |
|------|------|------|
| **Solo** | $39/mo | 1 app、Telegram、即时 + 日报 |
| ~~Team~~ | 不做 v1 | v2 再议 |

**升级路径（记 backlog，不做 v1）：** Incident 口述 → postmortem（Idea 5-D2）、晨间全量告警摘要（Idea 4-D3）

---

## 14 天 KPI（MVP 上线后）

| 指标 | 目标 | 实际 |
|------|------|------|
| 预付 / 付费用户 | ≥3 | |
| 活跃 Telegram 推送 | ≥2 用户 7 天内收到真实告警 | |
| 支持 ticket | ≤5（超出 → 收窄范围） | |
| MRR | ≥$117 | |

未达标 → 改 **wedge**（如只做 `checkout.session.completed` 失败），不加功能。

---

## 访谈笔记模板（复制即用）

```markdown
## Interview — YYYY-MM-DD — [匿名/姓名]

- 角色：solo founder / backend lead / ...
- 栈：Spring Boot __ / Stripe since __
- 最近 webhook 事故：有/无 — 简述：
- 当前发现方式：
- 对样本专报评分（1-5）：
- $39/mo WTP：高/中/低
- 预付意愿：是/否/考虑
- 原话摘录：
- 下一步：
```

---

## Kill / Pivot 触发器

- Day 14 验证结束：**0 预付** 且 **<3 人承认痛点** → Kill  
- MVP 上线 30 天：**<2 付费留存** → 并入 GraalVM 内容获客（写一篇 teardown 归档）  
- 支持时间 **>20% 周工时** → 砍掉「日报」，只做「即时失败」  

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`../01-market-research/idea-scorecard-2026-08-28.md`](../01-market-research/idea-scorecard-2026-08-28.md) | Idea 3 / 4-D4 backlog |
| [`../01-market-research/initial-brainstorming.md`](../01-market-research/initial-brainstorming.md) | 拓展树来源 |
| [`tech-spike-template.md`](tech-spike-template.md) | Week 2 spike 记录 |
| [`landing-page-checklist.md`](landing-page-checklist.md) | 上线前检查 |
| [`offer-one-pager-template.md`](offer-one-pager-template.md) | Offer 正式版 |
| [`../04-indie-log/roadmap-and-milestones.md`](../04-indie-log/roadmap-and-milestones.md) | 并行产品线 ≤1 |
