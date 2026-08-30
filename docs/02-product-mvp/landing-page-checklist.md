# Landing Page 检查清单

**用途：** 从 Offer one-pager 到可公开 URL，支持 Stage A/B Traffic + Validation  
**Last updated:** 2026-08-28

> 没有价格的 Landing = 验证剧场。  
> Landing without price = validation theater.

---

## 发布前检查（全部勾选才可分享 UTM 链接）

### 内容与 Offer 对齐

- [ ] 标题 = Offer 一句话承诺（非功能列表）  
- [ ] 副标题说明 **谁** + **痛点** + **结果**  
- [ ] **价格可见**（或「$XX/mo — Pre-sale open」）  
- [ ] 单一 Primary CTA（Buy / Join waitlist / Book demo 三选一）  
- [ ] 「不包含 / 不适合谁」一段（过滤错误客户）  
- [ ] 社会证明：若有则真实（logo / 引用 / 数字）；**无则不放假证明**  
- [ ] FAQ ≥ 3：定价、退款、交付时间、支持方式  

### 转化与追踪

- [ ] CTA 链到 Stripe Payment Link / Lemon Squeezy / Tally waitlist（带 WTP 字段）  
- [ ] UTM 参数习惯：`?utm_source=x&utm_medium=bio&utm_campaign=niche-v1`  
- [ ] 简单 analytics（Plausible / Umami / GA — 选一个即可）  
- [ ] 成功页：说明 **48h 内** access + 收集 email  

### 信任与合规（全球 solo 最小集）

- [ ] Footer：Terms / Privacy / Refund policy 链接（模板 OK）  
- [ ] 联系邮箱可见（support@ 或 hello@）  
- [ ] 英文拼写与语法过一遍（Grammarly / AI 辅助）  

### 技术（CTO ≤ 4h 原则）

- [ ] HTTPS  
- [ ] 移动端可读  
- [ ] 首屏 < 3s（静态站 / 单页即可）  
- [ ] 无 broken CTA  

---

## 推荐页面结构（单页）

```text
[Hero: 结果导向标题 + 价格 + CTA]
[Problem: 3 bullets 痛点]
[Solution: One Killer Feature 演示 GIF / 截图]
[How it works: 3 steps]
[Pricing: 单 SKU 主推]
[FAQ]
[Footer: legal + contact]
```

**禁止 v1：** 多语言、博客、文档站、登录注册系统（除非 CTA 本身需要）。

---

## 发布后 7 天 KPI

| 指标 | 目标（早期） | 实际 |
|------|--------------|------|
| Qualified visits | ≥ 20 | |
| Waitlist + WTP | ≥ 10 | |
| Paid intent | ≥ 2 | |
| 访谈来自 landing | ≥ 3 | |

未达标 → 改 **offer/渠道**，不是改配色。

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`offer-one-pager-template.md`](offer-one-pager-template.md) | 文案源 |
| [`../03-growth-and-automation/distribution-channels.md`](../03-growth-and-automation/distribution-channels.md) | 引流节奏 |
| [`../00-constraints/runway-and-living-wage.md`](../00-constraints/runway-and-living-wage.md) | 合规 checklist |
