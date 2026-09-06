# Offer One-Pager — GraalVM Native Config Assistant

**版本：** v1（草稿）  
**日期：** 2026-09-06  
**Funnel 阶段：** [x] Validation  [ ] Pricing  [ ] Monetization  
**来源：** 从 [`offer-one-pager-template.md`](offer-one-pager-template.md) 复制；内容对齐 [`niche-graalvm-native-image-teardown.md`](../01-market-research/niche-graalvm-native-image-teardown.md)

---

### 1. 一句话 Offer（Elevator Pitch）

> 帮助 **把 Spring Boot 3 服务编译为 Native Image 部署到 AWS Lambda / Google Cloud Run 的 Staff 工程师与初创 CTO**，在 **一次 CI 构建周期内** 从失败 log 得到 **可 commit 的 reflect-config / resource-config 片段**，而无需 **手工翻 GraalVM 文档或反复问 ChatGPT**。

---

### 2. 买家画像（ICP）

| 字段 | 内容 |
|------|------|
| **Primary buyer** | Staff / Principal Engineer、2–20 人初创 CTO |
| **User** | 日常跑 Native Image 构建的 Java 后端 |
| **Company size** | 2–20 人技术团队，或 solo indie 上 serverless |
| **Geography / language** | Global, English-first |
| **Trigger moment** | CI 红了一周；要上 Lambda/Cloud Run；reflect-config 手工维护失控 |
| **Current spend** | 工程师 $50–150/h × 4–8h/次失败；或 $20/mo ChatGPT（无项目上下文） |

---

### 3. 痛点与现状（Problem）

**核心痛点（1 句）：**  
Spring Boot 3 Native Image 构建因 reflection/resource/JNI 失败，团队反复手工维护 `reflect-config.json`，阻塞 serverless 上线数天。

**今天他们怎么凑合（Status quo）：**  
- [x] 电子表格 / 脚本  
- [x] 贵价 incumbent：通用 CI 编译服务（贵、非 Spring 专用）  
- [x] 完全手工：翻 GraalVM 文档 + ChatGPT 猜配置  

**不解决的代价（量化）：**  
一次失败 ≈ 4h × $75/h = $300；一周阻塞 ≈ $1,500+ 机会成本 + 发布延期。

**访谈引用（≥ 2 条，带来源）：**  
1. “________________” — 来源：________（待访谈）  
2. “________________” — 来源：________（待访谈）  

---

### 4. 承诺结果（Outcome / Promise）

| 类型 | 承诺 |
|------|------|
| **Primary outcome** | 上传 CI 失败 log → 得到可 commit 的 config 片段 + 构建通过说明 |
| **Time to value** | 首次价值 ≤ **15 分钟**（concierge）；产品化后 ≤ 5 分钟 |
| **Scope boundary** | **不**承诺：非 Spring Boot 栈、生产监控、无限轮次支持、全库迁移 |

**One Killer Feature（仅一个）：**  
**CI log → commit-ready reflect-config / resource-config**（非聊天建议）

---

### 5. 方案形态（How we deliver）

| 维度 | v1 选择 |
|------|---------|
| 形态 | [x] SaaS  [x] CLI  [ ] API  [x] Done-for-you（现金轨）  [x] 混合 |
| 交付方式 | CLI 本地限次 + 云端深度分析；咨询见 [`services-offer-graalvm.md`](services-offer-graalvm.md) |
| 支持渠道 | Email / async |
| SLA | 48h 响应；access ≤ 24–48h |

---

### 6. 定价（Pricing）

| SKU | 价格 (USD) | 包含 | 不包含 |
|-----|------------|------|--------|
| **CLI Free** | $0 | 本地分析 N 次/月 | 云端深度分析、模板库 |
| **Paid（主推）** | **$29/mo** | 无限云分析 + Spring Boot 3 常见依赖模板库 | Team seat、CI 集成 |
| **Quick Fix（现金轨）** | **$2,500** 一次性 | 48–72h 交付 + 1 轮修订 | 见 services-offer-graalvm SKU A |

**定价锚点（ROI 一句话）：**  
若为用户节省 4h/月 × $75/h = $300 → 收 $29/mo 合理。

**支付：** Stripe Payment Link — 链接：________（待开通）

**双 CTA（Landing）：**

| CTA | 受众 | 价格 |
|-----|------|------|
| Start / Pre-order SaaS | 愿自助 | $29/mo |
| Book Fix Call | 要结果、预算 $2k+ | $2,500+ |

---

### 7. 竞争与楔子（Wedge）

| 竞品 / 替代 | 他们的价 | 我们的差异（1 句） |
|-------------|----------|-------------------|
| Spring Native / GraalVM 官方文档 | 免费 | 不解决第三方库长尾反射；我们给 **可 commit artifact** |
| ChatGPT / 通用 AI | $20/mo | 无项目上下文、幻觉配置；我们解析 **真实 CI log** |
| DIY 手工维护 | 工程师时薪 | 不可复用；我们内置 **Spring Boot 3 依赖模板库** |

**为什么是我们 / 为什么现在：**  
Serverless Java 采用加速，Native Image 仍是上线瓶颈；专注 Spring Boot + Lambda/Cloud Run 垂直场景，而非通用 Native Image GUI。

---

### 8. 验证计划（Next 2 weeks）

| 动作 | 目标数字 | 截止 |
|------|----------|------|
| 访谈 / 深聊 | ≥ **5** 次 | W2 结束 |
| Landing + 价格公开 | Live URL | W3 |
| Waitlist / Pre-sale | ≥ **10** emails **或** ≥ **1** 付费意向 | W4 |
| 渠道 | r/java, r/springboot, Spring Discussions, X | 持续 |

**Validation Gate（Stage B）：**  
- [ ] 3+ 书面 pre-commit @ $29/mo  
- [ ] 或 1+ USD 已收（concierge 也算）  
- [ ] 或 50+ waitlist 且 ≥40% 愿付 $29+/mo  

---

### 9. 风险与 Kill 条件

| 风险 | 缓解 | Kill if |
|------|------|---------|
| Spring/GraalVM 官方继续自动化 | 垂直第三方库长尾 + 团队模板 | 官方覆盖 80% 痛点 |
| 「又一个 AI wrapper」 | 卖 artifact 不卖聊天 | 访谈无人愿付 $19+/mo |
| Support 爆炸 | 限 Scope：仅 Spring Boot 3 | 2 周无 money language |
| 市场偏小 | 高 ARPU + 现金轨并行 | Day 60 仍 0 付费意向 |

---

### 10. CEO 签字

- [ ] 价格已写死在此页  
- [ ] CTO 确认 v1 可在 ≤ 2 周内交付（concierge 或 thin MVP）  
- [ ] 本周 CMO 时间 ≥ CTO 时间（若仍 $0 revenue）

**Decision / 备注：**  
v1 草稿完成 2026-09-06；待 5 次访谈后迭代 v2。现金轨与 SaaS 共用 ICP，Landing 双 CTA。

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`services-offer-graalvm.md`](services-offer-graalvm.md) | 现金轨 $2.5k+ SKU |
| [`niche-graalvm-native-image-teardown.md`](../01-market-research/niche-graalvm-native-image-teardown.md) | 竞品与访谈问题 |
| [`landing-page-checklist.md`](landing-page-checklist.md) | 从 offer 到页面 |
| [`../04-indie-log/outreach-log.md`](../04-indie-log/outreach-log.md) | 外联 / 访谈记录 |
