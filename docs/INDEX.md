# 文档总目录 (Master Index)

> **维护规则（COO 铁律）：** 新增、移动、重命名或删除任何 `.md` 文件时，**同一轮改动内**必须同步更新本目录。  
> **SSOT（单一来源）：** 本页是**全库文档清单的唯一权威**；`README.md`、子目录 README 等**不得**再维护等价的逐文件目录表——只保留仓库简介 / 分区用途，并链到本页。  
> **Git：** Agent 每轮改动结束自动 **commit**；**push 由用户决定**。  
> **最后全量校对：** 2026-09-06

---

## 当前执行（Live）

> 详细字段见 [`04-indie-log/CURRENT-STATUS.md`](04-indie-log/CURRENT-STATUS.md) — **每周日 scorecard 后同步更新本节摘要。**

| 字段 | 值 |
|------|-----|
| Day / Week | Day 10 / W2 |
| Funnel | **B — Validation** |
| Primary bet | GraalVM Native Image 助手 |
| 本周 ONE bet | offer v1 + 5 外联 + 2 访谈 |
| 90d 访谈 | 0 / 25 |
| Revenue | $0 |

---

## 快速入口

| 我想… | 去看 |
|--------|------|
| **今天公司跑到哪了** | [`04-indie-log/CURRENT-STATUS.md`](04-indie-log/CURRENT-STATUS.md) |
| 记外联 / 访谈 | [`04-indie-log/outreach-log.md`](04-indie-log/outreach-log.md) |
| 抛一个新点子、走四角色评审 | [`01-market-research/idea-intake-sop.md`](01-market-research/idea-intake-sop.md) |
| 查所有已记录的点子 | [`01-market-research/initial-brainstorming.md`](01-market-research/initial-brainstorming.md) |
| 看已打分、当前 Primary bet | [`01-market-research/idea-scorecard-2026-08-28.md`](01-market-research/idea-scorecard-2026-08-28.md) |
| 每日怎么干活 | [`../daily_sop.md`](../daily_sop.md) |
| 商业漏斗与 Kill 规则 | [`01-market-research/business-framework.md`](01-market-research/business-framework.md) |
| 换帽子（CEO/CMO/CTO/COO） | [`../roles/`](../roles/) |

---

## 根目录

| 路径 | 类型 | 说明 | 更新 |
|------|------|------|------|
| [`README.md`](../README.md) | 对外 | 仓库简介、分区布局；**文档清单见 INDEX** | 2026-09-06 |
| [`daily_sop.md`](../daily_sop.md) | SOP | 创始人每日标准作业（帽子切换循环） | 2026-09-06 |
| [`.cursor/rules/git-and-docs.mdc`](../.cursor/rules/git-and-docs.mdc) | 规则 | Agent：自动 commit、SSOT、不主动 push | 2026-09-06 |

---

## `roles/` — 角色工作区

| 路径 | 角色 | 说明 | 更新 |
|------|------|------|------|
| [`CEO-chief-executive-officer.md`](../roles/CEO-chief-executive-officer.md) | CEO | 战略、Runway、时间分配、决策日志 | 2026-08-28 |
| [`CMO-chief-marketing-officer.md`](../roles/CMO-chief-marketing-officer.md) | CMO | 市场调研、验证、分发、文案 | 2026-08-28 |
| [`CTO-chief-technology-officer.md`](../roles/CTO-chief-technology-officer.md) | CTO | MVP、技术栈、Tech Spike、AI 杠杆 | 2026-08-28 |
| [`COO-chief-operating-officer.md`](../roles/COO-chief-operating-officer.md) | COO | 财务、自动化、知识库、INDEX + SSOT + Git 落盘 | 2026-09-06 |

---

## `docs/00-constraints/` — 生存约束

| 路径 | 类型 | 说明 | 更新 |
|------|------|------|------|
| [`runway-and-living-wage.md`](00-constraints/runway-and-living-wage.md) | 约束 | Runway、生活 MRR、全球收款清单 | 2026-08-28 |

---

## `docs/01-market-research/` — 市场调研与点子管线

| 路径 | 类型 | 说明 | 状态 | 更新 |
|------|------|------|------|------|
| [`idea-intake-sop.md`](01-market-research/idea-intake-sop.md) | **SOP** | **新点子四角色评审 + Validation 冻结期 + SSOT + Git** | 活跃 | 2026-09-06 |
| [`initial-brainstorming.md`](01-market-research/initial-brainstorming.md) | 沙盒 | Idea 1–10 原始脑暴 + 拓展树 | 活跃 | 2026-09-07 |
| [`idea-scorecard-2026-08-28.md`](01-market-research/idea-scorecard-2026-08-28.md) | 评分 | 种子点子硬过滤 + 软打分；Top 1 = GraalVM | 活跃 | 2026-08-28 |
| [`business-framework.md`](01-market-research/business-framework.md) | 框架 | 商业漏斗、Micro-Niche 打分表、Kill 规则 | 活跃 | 2026-08-28 |
| [`01-niche-discovery-methodology.md`](01-market-research/01-niche-discovery-methodology.md) | 方法 | 利基发现：去哪找、怎么筛 | 活跃 | 2026-08-28 |
| [`icp-discovery-playbook.md`](01-market-research/icp-discovery-playbook.md) | Playbook | 7 天买家优先验证清单 | 活跃 | 2026-08-28 |
| [`niche-research-template.md`](01-market-research/niche-research-template.md) | 模板 | 复制后开新 niche 调研 | 模板 | 2026-08-28 |
| [`niche-graalvm-native-image-teardown.md`](01-market-research/niche-graalvm-native-image-teardown.md) | 调研 | GraalVM Native Image 竞品与痛点拆解 | 活跃 | 2026-08-28 |

### 点子索引（`initial-brainstorming.md`）

| # | 标题 | 状态 | 备注 |
|---|------|------|------|
| 1 | GraalVM / Native Image 打包伴侣 | ✅ Primary bet | Scorecard 29 分 |
| 2 | API 按量计费网关 | ❌ Kill | 硬过滤 FAIL |
| 3 | Spring Boot 轻量监控 | 🟡 续研 | Scorecard 25 分 |
| 4 | AI 私人秘书 | 🟡 沙盒 | 拓展树 A–E |
| 5 | 录音 / 实时声音总结 | 🟡 沙盒 | 与 Idea 4-A1 相邻 |
| 6 | 私人生活知识库 | 🟡 沙盒 | Idea 4 迭代 |
| 7 | 炒股兴趣周边 | 🟡 沙盒 | 兴趣轨 |
| 8 | 微信/QQ 群日报 | 🟡 沙盒 | Idea 4-B3 变体 |
| 9 | 离谱野史 × 语音故事 | 🟡 沙盒 | 2026-09-06；场景已拆 |
| 10 | 垂直品类即时配送（宠物粮 / 应急包 / 移动摊） | 🟡 沙盒 | 2026-09-07；wedge=C；文档首验 C1；创始人兴趣 C5b 鹌鹑摊 / C6 露营夜间茶摊（E4/E5 二选一）；B2 归档 |

---

## `docs/02-product-mvp/` — 产品与 MVP

| 路径 | 类型 | 说明 | 更新 |
|------|------|------|------|
| [`monetization-strategy.md`](02-product-mvp/monetization-strategy.md) | 策略 | Stripe、买断 vs 订阅、预售先于代码 | 2026-08-28 |
| [`services-offer-graalvm.md`](02-product-mvp/services-offer-graalvm.md) | Offer | 现金轨：GraalVM 咨询 SKU ($2.5k+) | 2026-08-28 |
| [`services-offer-trading-discipline.md`](02-product-mvp/services-offer-trading-discipline.md) | Offer | 兴趣轨：交易纪律小班 (¥3.9k) | 2026-08-28 |
| [`adr-concierge-validation.md`](02-product-mvp/adr-concierge-validation.md) | ADR | Concierge 手动验证架构决策 | 2026-08-28 |
| [`stripe-webhook-alert-playbook.md`](02-product-mvp/stripe-webhook-alert-playbook.md) | Playbook | Stripe webhook 失败排查 | 2026-08-28 |
| [`landing-page-checklist.md`](02-product-mvp/landing-page-checklist.md) | 清单 | Landing 页发布前检查 | 2026-08-28 |
| [`offer-one-pager-template.md`](02-product-mvp/offer-one-pager-template.md) | 模板 | 一页 Offer（谁 / 痛 / 价） | 2026-08-28 |
| [`offer-graalvm-native-v1.md`](02-product-mvp/offer-graalvm-native-v1.md) | Offer | GraalVM SaaS Offer v1 草稿 | 2026-09-06 |
| [`tech-spike-template.md`](02-product-mvp/tech-spike-template.md) | 模板 | 48h 技术实验记录 | 2026-08-28 |

---

## `docs/03-growth-and-automation/` — 增长与自动化

| 路径 | 类型 | 说明 | 更新 |
|------|------|------|------|
| [`README.md`](03-growth-and-automation/README.md) | 说明 | 本子目录用途（清单见 INDEX） | 2026-09-06 |
| [`distribution-channels.md`](03-growth-and-automation/distribution-channels.md) | 策略 | $0 广告冷启动：BIP、Reddit、PH | 2026-08-28 |
| [`ai-operating-stack.md`](03-growth-and-automation/ai-operating-stack.md) | 策略 | AI 工具栈、COGS 红线 | 2026-08-28 |
| [`deployment-and-ops-minimum.md`](03-growth-and-automation/deployment-and-ops-minimum.md) | 运维 | Hetzner + Stripe webhook 最小部署 | 2026-08-28 |
| [`tea-promotion-one-pager.md`](03-growth-and-automation/tea-promotion-one-pager.md) | 对外 | TEA 推广一页纸（准入引擎） | 2026-08-28 |

---

## `docs/04-indie-log/` — 构建日志

| 路径 | 类型 | 说明 | 更新 |
|------|------|------|------|
| [`CURRENT-STATUS.md`](04-indie-log/CURRENT-STATUS.md) | **仪表盘** | **执行状态 SSOT — 今日看这一页** | 2026-09-06 |
| [`outreach-log.md`](04-indie-log/outreach-log.md) | CRM | 外联 / 访谈记录 | 2026-09-06 |
| [`roadmap-and-milestones.md`](04-indie-log/roadmap-and-milestones.md) | 路线图 | 90 天里程碑 → 首笔 USD | 2026-08-28 |
| [`2026-08-28-kickoff.md`](04-indie-log/2026-08-28-kickoff.md) | 日志 | 项目启动宣言 | 2026-08-28 |
| [`daily-logs/README.md`](04-indie-log/daily-logs/README.md) | 说明 | 每日日志用法（清单见 INDEX） | 2026-09-06 |
| [`daily-logs/2026-08-28-week1-scorecard.md`](04-indie-log/daily-logs/2026-08-28-week1-scorecard.md) | 周报 | Week 1 scorecard | 2026-08-28 |
| [`daily-logs/2026-09-06-week2-scorecard.md`](04-indie-log/daily-logs/2026-09-06-week2-scorecard.md) | 周报 | Week 2 scorecard | 2026-09-06 |

---

## 按类型浏览

| 类型 | 文档 |
|------|------|
| **SOP / 流程** | `daily_sop.md`, `idea-intake-sop.md`, `icp-discovery-playbook.md`, `adr-concierge-validation.md` |
| **框架 / 方法** | `business-framework.md`, `01-niche-discovery-methodology.md` |
| **模板（复制即用）** | `niche-research-template.md`, `offer-one-pager-template.md`, `tech-spike-template.md` |
| **点子管线** | `initial-brainstorming.md` → `idea-scorecard-*.md` → niche teardown |
| **当前执行** | `CURRENT-STATUS.md`, `outreach-log.md`, `offer-graalvm-native-v1.md`, `idea-scorecard-2026-08-28.md` |
| **角色** | `roles/CEO|CMO|CTO|COO-*.md` |

---

*找不到文档？先搜本页；仍没有 → 按 [`idea-intake-sop.md`](01-market-research/idea-intake-sop.md) 新建并登记。*
