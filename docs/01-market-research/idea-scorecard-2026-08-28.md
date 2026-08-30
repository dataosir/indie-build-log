# Idea Scorecard — 2026-08-28

**Source ideas:** [`initial-brainstorming.md`](initial-brainstorming.md)  
**Method:** [`business-framework.md`](business-framework.md) §4 Micro-Niche Scorecard  
**新点子入场：** 先跑 [`icp-discovery-playbook.md`](icp-discovery-playbook.md) 7 天 Gate，再进本表打分  
**Owner:** CEO + CMO（Week 1 KPI）

---

## 硬过滤（7 项全 YES 才进入软打分）

| # | Filter | Idea 1 GraalVM 助手 | Idea 2 按量计费网关 | Idea 3 Spring 轻量监控 |
|---|--------|:-------------------:|:-------------------:|:----------------------:|
| 1 | USD / global pay | ✅ | ✅ | ✅ |
| 2 | High WTP | ✅ | ✅ | ⚠️ 偏低价 |
| 3 | AOV ≥ $49/mo 或 $99 OT | ✅ ($19–29/mo 可升档) | ✅ ($49/mo) | ⚠️ ($9/mo，靠 $49 买断补) |
| 4 | Low maintenance | ✅ | ⚠️ 多租户/流量 | ✅ |
| 5 | Not pure red ocean | ⚠️ 有 wedge | ❌ Stripe Billing/Kong 红海 | ⚠️ 监控品类 crowded |
| 6 | Founder advantage | ✅✅ Java/GraalVM | ✅ Java 后端 | ✅✅ Spring 生态 |
| 7 | Reachable buyers | ✅ r/java, Spring, serverless | ✅ indie hackers | ✅ solo Java 站长 |

**硬过滤结论：**

- **Idea 2** → **FAIL #5**（generic billing / API GW 红海，无清晰 distribution wedge）→ **Archive，除非垂直化到极窄场景**  
- **Idea 1 & 3** → 进入软打分（#3/#5 为 yellow，需 vertical wedge 验证）

---

## 软打分（0–5 × 8 维，max 40）

| Dimension | Idea 1 GraalVM | Idea 3 Spring 监控 | Notes |
|-----------|:--------------:|:------------------:|-------|
| Pain urgency | 4 | 3 | Native Image 失败阻塞发布 vs 监控偏「有了更好」 |
| Budget owner clarity | 4 | 4 | 都是 dev/CTO 刷卡 |
| Competition intensity | 3 | 2 | 均有 Uptime Kuma / Prometheus 等 |
| Switching cost | 3 | 2 | 手工改 config vs 已有免费监控 |
| Content / SEO surface | 5 | 3 | GraalVM 报错搜索意图强 |
| Build scope to v1 | 3 | 4 | AI+log 解析 vs 单 Jar 插件 |
| Support burden | 3 | 4 | Native Image 边缘 case 多 |
| Expansion path | 4 | 3 | CI 集成、团队模板 |
| **Total** | **29** | **25** | |

**决策（framework 阈值）：**

| Idea | Score | Action |
|------|-------|--------|
| **Idea 1 — GraalVM Native Image 助手** | **29** | ✅ **Enter Validation (Stage B)** — Week 2 优先 teardown + 访谈 |
| Idea 3 — Spring 轻量监控 | 25 | 🟡 Research 1 more week — 需更窄 wedge（如「Stripe webhook 失败专报」） |
| Idea 2 — 按量计费网关 | — | ❌ **Kill** — 硬过滤 FAIL |

---

## Top 1 选择

**Primary bet (Week 2–4):** **Idea 1 — GraalVM / Native Image 编译配置助手**

**Wedge 收窄（red-ocean escape）：**

- 非「通用 AI 编译平台」  
- 而是：**「Spring Boot 3.x + Cloud Run/Lambda 的 Native Image 报错 → reflect-config 生成」**

**Next actions:**

1. 完成 [`niche-graalvm-native-image-teardown.md`](niche-graalvm-native-image-teardown.md)  
2. 复制 [`../02-product-mvp/offer-one-pager-template.md`](../02-product-mvp/offer-one-pager-template.md) → `offer-graalvm-native-v1.md`  
3. 排 5 次访谈（Serverless Java / Spring Native 用户）  
4. CTO：48h spike — 见 [`../02-product-mvp/tech-spike-template.md`](../02-product-mvp/tech-spike-template.md)  

---

## 其他候选（沙盒 backlog）

| Idea | 备注 |
|------|------|
| Idea 3 垂直化 | 「仅监控 Stripe webhook + Actuator health」— 重新打分；执行单 → [`../02-product-mvp/stripe-webhook-alert-playbook.md`](../02-product-mvp/stripe-webhook-alert-playbook.md) |
| Idea 2 垂直化 | 仅服务「OpenAI-compatible proxy billing for indie」— 仍需谨慎 |
| **Idea 4 — AI 私人秘书（原始）** | 🟡 沙盒 — 通用 C 端 + 小程序 **预 Kill**；见 [`initial-brainstorming.md`](initial-brainstorming.md) Idea 4 |
| Idea 4-D1 | 独立开发者支持工单秘书 — 与 GraalVM 无协同，但 founder-fit 高，可单独 scorecard |
| Idea 4-D4 | Stripe/账单异常秘书 — 与 Idea 3 监控 **可合并** wedge，优先评估合并而非新开产品线 |
| Idea 4-B3 | 社群群摘要秘书 — 仅当有现成私域流量时再打分 |
| **Idea 5 — 录音 / 实时声音总结（原始）** | 🟡 沙盒 — 通用会议记录 **预 Kill**（Otter/飞书妙记红海）；见 [`initial-brainstorming.md`](initial-brainstorming.md) Idea 5 |
| Idea 5-C1 | 纯事后批处理（上传 → 总结）— MVP 成本最低，优先于实时 |
| Idea 5-D1 | 技术评审 / RFC 讨论 → ADR 草稿 — founder-fit 中，可单独 scorecard；Concierge 清单 → [`../02-product-mvp/adr-concierge-validation.md`](../02-product-mvp/adr-concierge-validation.md) |
| Idea 5-D2 | Incident 口述复盘整理 — 与 Idea 3/D3 **可合并** |
| Idea 5-B1 | 远程工程站会 → Linear 待办 — 与 Idea 4-A1 **同一 wedge**，勿双线开发 |
| Idea 5-C3 | 真实时字幕 — 工程重、竞品多，**延后** |
| **Idea 6 — 私人生活知识库（Idea 4 迭代）** | 🟡 沙盒 — 通用 C 端生活 OS **预 Kill**；叙事优于秘书但仍触硬过滤；见 [`initial-brainstorming.md`](initial-brainstorming.md) Idea 6 |
| Idea 6-B2 | 每周生活周报（自动聚合）— 叙事好、集成重，需单独验证付费 |
| Idea 6-B3 | 关系维护提醒 + 草稿消息 — 国内 C 端可试，与 Global 战略冲突 |
| Idea 6-E1 | 独立开发者工作/生活复盘 KB — 与 Idea 3/4 可合并，founder-fit 最高 |
| Idea 6-C1 | 语音 → 生活档案 — 与 Idea 5 事后批处理 **同一管道**，勿双线 |

---

*Review every Sunday. Kill early.*
