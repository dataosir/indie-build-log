# Offer One-Pager 模板

**用途：** Stage B/C 之前，用一页纸说清「卖给谁、卖什么、多少钱」——给访谈、Landing、Pre-sale 共用  
**Owner:** CMO + CEO 起草，CTO 审技术可行性  
**Last updated:** 2026-08-28

> 若一页纸说不清，说明 niche 还没收窄。  
> If it doesn't fit one page, the niche isn't narrow enough.

---

## 使用说明

1. 复制本文件为 `offer-<niche-slug>-v1.md`  
2. 在 **≥ 10 次访谈** 过程中迭代，版本号 v1 → v2  
3. Landing 页文案应能从此页 **直接映射**（见 [`landing-page-checklist.md`](landing-page-checklist.md)）  
4. 定价数字必须出现在此页——无价格 = 假验证

---

## Offer One-Pager — `<产品工作名>`

**版本：** v1  
**日期：** YYYY-MM-DD  
**Funnel 阶段：** [ ] Validation  [ ] Pricing  [ ] Monetization

---

### 1. 一句话 Offer（Elevator Pitch）

> 帮助 **[目标买家]** 在 **[时间范围]** 内 **[可量化结果]**，而无需 **[他们今天最恨的替代方案]**。

示例结构（勿照抄）：  
*Help Java teams shipping to Cloud Run cut Native Image build failures from hours to minutes—without hand-editing reflect-config.json.*

---

### 2. 买家画像（ICP）

| 字段 | 内容 |
|------|------|
| **Primary buyer** | 职位 / 角色（谁刷卡） |
| **User** | 日常使用者（若不同） |
| **Company size** | 如：1–20 人初创、solo indie |
| **Geography / language** | Global, English-first |
| **Trigger moment** | 什么事件让他们现在就要找解决方案 |
| **Current spend** | 他们今天为类似问题付 $____/mo 或 ____h/周 |

---

### 3. 痛点与现状（Problem）

**核心痛点（1 句）：**  
_____________________________________________________________

**今天他们怎么凑合（Status quo）：**  
- [ ] 电子表格 / 脚本  
- [ ] 贵价 incumbent：________  
- [ ] 完全手工：________  

**不解决的代价（量化）：**  
_____________________________________________________________

**访谈引用（≥ 2 条，带来源）：**  
1. “________________” — 来源：________  
2. “________________” — 来源：________  

---

### 4. 承诺结果（Outcome / Promise）

| 类型 | 承诺 |
|------|------|
| **Primary outcome** | 用户得到的可感知结果 |
| **Time to value** | 首次价值 ≤ ____ 分钟 / 小时 |
| **Scope boundary** | **不**承诺什么（降 support 负荷） |

**One Killer Feature（仅一个）：**  
_____________________________________________________________

---

### 5. 方案形态（How we deliver）

| 维度 | v1 选择 |
|------|---------|
| 形态 | [ ] SaaS  [ ] CLI  [ ] API  [ ] Done-for-you  [ ] 混合 |
| 交付方式 | 注册 / 下载 / 邮件发 license / 手动 onboarding |
| 支持渠道 | Email / Discord / 无实时 |
| SLA | 48h 响应；access ≤ 24–48h |

---

### 6. 定价（Pricing）

| SKU | 价格 (USD) | 包含 | 不包含 |
|-----|------------|------|--------|
| **Paid（唯一主推）** | $____/mo **或** $____ 一次性 | | |
| Free / preview（若有） | $0 | 限次 / 只读 | 核心 outcome |

**定价锚点（ROI 一句话）：**  
若为用户节省 ____h/月 × $____/h → 收 $____ 合理。

**支付：** Stripe Payment Link / Lemon Squeezy — 链接：________

---

### 7. 竞争与楔子（Wedge）

| 竞品 / 替代 | 他们的价 | 我们的差异（1 句） |
|-------------|----------|-------------------|
| | | |
| DIY | 时间成本 | |

**为什么是我们 / 为什么现在：**  
_____________________________________________________________

---

### 8. 验证计划（Next 2 weeks）

| 动作 | 目标数字 | 截止 |
|------|----------|------|
| 访谈 / 深聊 | ≥ __ 次 | |
| Landing + 价格公开 | Live URL | |
| Waitlist / Pre-sale | ≥ __ emails **或** ≥ __ 付费意向 | |
| 渠道 | Reddit / X / PH / 其他：________ | |

**Validation Gate（Stage B）：**  
- [ ] 3+ 书面 pre-commit @ 标价  
- [ ] 或 1+ USD 已收（concierge 也算）  
- [ ] 或 50+ waitlist 且 ≥40% 愿付 $29+/mo  

---

### 9. 风险与 Kill 条件

| 风险 | 缓解 | Kill if |
|------|------|---------|
| | | 2 周无 money language |
| | | 硬过滤 FAIL（见 scorecard） |

---

### 10. CEO 签字

- [ ] 价格已写死在此页  
- [ ] CTO 确认 v1 可在 ≤ 2 周内交付（concierge 或 thin MVP）  
- [ ] 本周 CMO 时间 ≥ CTO 时间（若仍 $0 revenue）

**Decision / 备注：**  
_____________________________________________________________

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`../01-market-research/business-framework.md`](../01-market-research/business-framework.md) | Funnel gates |
| [`monetization-strategy.md`](monetization-strategy.md) | 定价带与 Stripe |
| [`landing-page-checklist.md`](landing-page-checklist.md) | 从 offer 到页面 |
| [`tech-spike-template.md`](tech-spike-template.md) | CTO 48h 技术验证 |
