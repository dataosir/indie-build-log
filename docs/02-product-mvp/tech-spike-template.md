# Tech Spike 记录模板

**用途：** CTO 在 **48 小时内** 验证最大技术风险，不写产品级代码  
**产出位置：** `docs/02-product-mvp/spikes/spike-<slug>-YYYY-MM-DD.md`  
**Last updated:** 2026-08-28

> Spike 回答「能不能做」，不回答「做得漂不漂亮」。  
> Spikes answer *can we*, not *should we polish*.

---

## 前置条件（必须满足才开 Spike）

- [ ] Offer one-pager 已有 v1（或 CEO 书面批准「仅为 de-risk 调研」）  
- [ ] 硬过滤 + scorecard ≥ 28 **或** CEO 豁免理由已记入 Decision Log  
- [ ] 时间盒：**≤ 48 小时**（闹钟设好）

---

## Spike — `<技术问题标题>`

**日期：** YYYY-MM-DD  
**Owner:** CTO  
**关联 Offer：** [`offer-___-v1.md`](offer-one-pager-template.md)  
**时间盒：** 开始 ____ → 截止 ____（max 48h）

---

### 1. 要回答的核心问题（1–3 条）

1. _____________________________________________________________  
2. _____________________________________________________________  

**成功标准（可观测）：**  
- [ ] 例如：在 M1 Mac 上 Native Image 构建 Spring Boot 3.x demo ≤ 8 分钟  
- [ ] 例如：从报错 log 提取 reflect class 名单准确率 ≥ 80% on sample set  

---

### 2. 假设与约束

| 假设 | 若失败则 |
|------|----------|
| | pivot / kill |
| 技术栈 | Spring Boot ___ / GraalVM ___ / 其他 |
| 部署目标 | 单机 / Cloud Run / 纯 CLI |
| AI 依赖（若有） | 模型：____  预估成本/次：____ |

---

### 3. 实验步骤（极简）

| Step | 动作 | 结果 |
|------|------|------|
| 1 | | |
| 2 | | |
| 3 | | |

**Artifacts：**  repo 链接 / gist / 本地路径（勿提交 secrets）

---

### 4. 结果摘要

**结论：** [ ] Go  [ ] Pivot  [ ] Kill  

| 指标 | 目标 | 实际 |
|------|------|------|
| | | |

**关键发现（3 条以内）：**  
1.  
2.  
3.  

**录屏 / 截图 / log 片段：**  
_____________________________________________________________

---

### 5. 对 Offer / MVP 的影响

| 维度 | 建议 |
|------|------|
| One Killer Feature 是否仍成立 | Y/N — 说明 |
| 预估 MVP 工期 | __ 天（仍须 ≤ 2 周 v1） |
| COGS / 基础设施 | $__/mo 或 $__/1000 requests |
| Support 风险 | 低 / 中 / 高 — 原因 |

---

### 6. 下一步（CEO / CMO / CTO）

- [ ] **CMO：** 继续访谈，话术调整：________  
- [ ] **CTO：** 进入 24h 原型 / 暂停编码  
- [ ] **CEO：** Decision Log 记录：________  

---

## Spike 反模式（禁止）

- 引入 K8s、完整 CI、多租户 auth「顺便做一下」  
- 超过 200 行非 spike 代码却不交付 learnings  
- 无结论地「再研究一周」

---

## 关联文档

| 文档 | 用途 |
|------|------|
| [`../../roles/CTO-chief-technology-officer.md`](../../roles/CTO-chief-technology-officer.md) | CTO 铁律与时间盒 |
| [`offer-one-pager-template.md`](offer-one-pager-template.md) | 业务边界 |
| [`../03-growth-and-automation/ai-operating-stack.md`](../03-growth-and-automation/ai-operating-stack.md) | AI 实验工具 |
