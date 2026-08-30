# Runway & Living Wage — 生存数学与 Phase 2 锚点

**Audience:** CEO（一人公司创始人）  
**Purpose:** 把「拿到 $1」和「能靠这个生活」之间的缺口量化，避免 Day 90 验证成功却仍焦虑  
**Last updated:** 2026-08-28

> 首笔美金证明方向可行；生活 MRR 证明方向可持续。  
> First dollar proves the funnel. Living MRR proves the company.

---

## 1. 为什么需要这张表

90 天路线图的主指标是 **≥ $1 USD**——这是正确的「打破 hobby 心理」门槛。  
但若你的真实目标是 **不坐班、面向全球、靠产品生活**，必须在 Day 1 就知道：

- 你还能撑多久（Runway）
- 「生活」需要多少 MRR（Living Wage Target）
- 从 $1 → 生活 MRR 需要多少客户、什么 ARPU

**CEO 每周日审计：** 更新本节数字，写入 weekly scorecard。

---

## 2. Runway 表（填写你的真实数字）

| 项目 | 金额 (USD/CNY) | 备注 |
|------|----------------|------|
| **可用现金** | ________ | 储蓄 + 可立即动用的资产，不含不可流动部分 |
| **月固定 burn** | ________ | 房租、保险、家庭必要支出、最低生活 |
| **月可变 burn** | ________ | SaaS 工具、域名、API、云主机（见下方工具预算） |
| **月总 burn** | ________ | 固定 + 可变 |
| **Runway（月）** | ________ | 可用现金 ÷ 月总 burn |
| **Runway 截止日期** | YYYY-MM-DD | 今天 + Runway 月数；低于 6 个月 → 加速验证或接短期咨询 |

### 2.1 默认工具预算参考（Stage A–D）

| 类别 | 典型范围 / 月 | 说明 |
|------|---------------|------|
| 云主机 (Hetzner/DO) | $5–20 | 单 VM 足够 Phase 1 |
| 域名 + 邮件 | $2–10 | |
| AI 工具 (Cursor 等) | $20–40 | 见 [`../03-growth-and-automation/ai-operating-stack.md`](../03-growth-and-automation/ai-operating-stack.md) |
| Stripe / MoR 手续费 | 按收入 | ~2.9% + $0.30 / 笔 |
| 预留 API COGS | $0–50 | 产品有 AI/API 调用后再填 |

**铁律：** Stage A/B 未过 Validation Gate 前，**新增 recurring 订阅需 CEO 签字**（Decision Log 一行即可）。

---

## 3. Living Wage Target（生活 MRR 粗算）

先定 **税后/到手** 月需求（按你所在地区与生活方式填写）：

| 场景 | 月到手目标 | 说明 |
|------|------------|------|
| 极简生活 | $ ________ | 单人、低城市成本 |
| 舒适生活 | $ ________ | 含缓冲、保险、旅行 |
| **当前选定目标** | **$ ________** | CEO 选定一个数字作为 Phase 2 North Star |

### 3.1 客户数反推（选主 SKU 价格后填）

公式：**所需付费客户数 ≈ 生活 MRR 目标 ÷ 月 ARPU（或年化 ÷ 12）**

| 月 ARPU | 生活 $2k/mo 需客户 | 生活 $3k/mo 需客户 | 生活 $5k/mo 需客户 |
|---------|-------------------|-------------------|-------------------|
| $19/mo | ~105 | ~158 | ~263 |
| $29/mo | ~69 | ~104 | ~172 |
| $49/mo | ~41 | ~61 | ~102 |
| $79/mo | ~25 | ~38 | ~63 |
| $99/mo | ~20 | ~30 | ~51 |

**偏好：** 本公司的默认价格带见 [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md)——**$49–$79/mo 或 $99+ 一次性** 更利于 solo _support 负荷。

### 3.2 从 $1 到 Living MRR 的现实路径（Phase 2 预览）

| 阶段 | 时间框 | 主指标 | 典型动作 |
|------|--------|--------|----------|
| **P0** | Day 1–90 | ≥ $1 USD | 当前 90-day roadmap |
| **P1** | Day 91–180 | $100–500 MRR | 同一 niche 加深、annual plan、2–5 个付费客户复购/转介绍 |
| **P2** | Day 181–365 | 生活 MRR 的 25–50% | 第二 SKU / 提价 / 轻量 SEO 复利 |
| **P3** | Year 2+ | ≥ Living Wage Target | 自动化 ops ≤20% 时间；考虑是否接咨询或第二产品 |

**Kill / pivot 与 Runway 联动：**

- Runway **< 4 个月** 且 Day 60 仍 $0 → 并行 **services wedge**（Java/GraalVM 咨询包）换时间，不无限延长同一 zombie product — 执行单见 [`../02-product-mvp/services-offer-graalvm.md`](../02-product-mvp/services-offer-graalvm.md)  
- Runway **≥ 9 个月** → 可更耐心做 SEO / 内容复利，但仍须 weekly commercial KPI

---

## 4. 全球收款与合规轻量 Checklist

面向 **Global-first、USD、solo** 的最小路径。详细定价策略见 [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md)。

### 4.1 收款 rails 选型

| 方案 | 何时选 | 优点 | 注意 |
|------|--------|------|------|
| **Stripe** | 你能处理基础税务/主体 | 灵活、开发者友好 | VAT/销售税需自行关注或后期加 Stripe Tax |
| **Lemon Squeezy** | 想少碰 VAT/MoR | Merchant of Record | 费率更高，定制账单弱 |
| **Paddle** | B2B SaaS、需发票体系 | MoR + 订阅成熟 | 审核与集成略重 |

**Phase 1 默认：** Stripe Payment Link **或** Lemon Squeezy（若不想 Day 1 研究 VAT）。

### 4.2 主体与税务（非法律建议 — 仅 checklist）

- [ ] 确认 Stripe/MoR **支持你的国籍 + 收款国** 组合  
- [ ] 选定收款主体：**个人** vs **LLC/有限公司**（收入上来后再优化，不必 Day 1 完美）  
- [ ] 记录 **收入币种、结算周期、手续费** 在 COO 台账  
- [ ] Landing 页链接：**Terms**、**Privacy**、**Refund Policy**（可用模板 + 律师 review 当 MRR > $1k）  
- [ ] 客户支持 SLA：**48h 内响应**（已在 monetization 文档对齐）  
- [ ] 时区：公开写明 **async-first**，关键窗口 overlap US/EU  evening  

### 4.3 外链资源（不必自建长文）

| 主题 | 用途 |
|------|------|
| [Stripe Atlas / 官方 docs](https://stripe.com/docs) | 账户与 Checkout |
| [Lemon Squeezy docs](https://docs.lemonsqueezy.com/) | MoR 快速上线 |
| Indie Hackers / r/SaaS 税务讨论 | 主体选型 peer 经验 |

---

## 5. CEO 每周 Runway 审计（30 秒）

复制到周日 scorecard：

```markdown
### Runway snapshot
- 可用现金：__
- 月 burn：__
- Runway 剩余（月）：__
- 生活 MRR 目标：$__/mo
- 当前 MRR：$__
- 距生活目标还差：__ 个 @$__/mo 客户
- 本周新增 recurring 工具：Y/N — 若 Y，金额：__
```

---

## 6. 关联文档

| 文档 | 关系 |
|------|------|
| [`../../roles/CEO-chief-executive-officer.md`](../../roles/CEO-chief-executive-officer.md) | 每周 Runway 审计流程 |
| [`../04-indie-log/roadmap-and-milestones.md`](../04-indie-log/roadmap-and-milestones.md) | Day 1–90 主指标 |
| [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md) | 定价与 Stripe 最小栈 |
| [`../03-growth-and-automation/deployment-and-ops-minimum.md`](../03-growth-and-automation/deployment-and-ops-minimum.md) | 基础设施成本 |

---

*Numbers over narratives. 先填表，再谈战略。*
