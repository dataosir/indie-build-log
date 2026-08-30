# AI Operating Stack — 一人公司 AI 杠杆 Playbook

**Audience:** 全员「帽子」— 尤其 CEO（分工）、CTO（编码）、CMO（文案调研）  
**Principle:** AI 是杠杆，不是产品故事本身；API COGS 必须有 margin 红线  
**Last updated:** 2026-08-28

> 你是雇佣了 AI 的 CEO，不是替 AI 打工的数据标注员。  
> You're a CEO with AI staff — not a labeler for your own margin leak.

---

## 1. 设计原则

| 原则 | 实践 |
|------|------|
| **Human decides, AI drafts** | 战略、定价、Kill 决策 — 人做；调研汇总、初稿、样板代码 — AI 做 |
| **Margin first** | 任何 AI-heavy SKU：单价必须覆盖 **预估 COGS × 3** 起步 |
| **No AI as moat alone** | 卖点是 outcome + domain wedge，不是「powered by GPT」 |
| **Templates on disk** | 可复用 prompt 放本 repo 或 `prompts/`（勿提交 secrets） |
| **Stage-aware** | Stage A/B：AI 偏 research/copy；Stage C+：AI 偏 delivery/support |

---

## 2. 默认工具栈（2026-08 版，按角色）

### CEO / 战略

| 任务 | 工具 | 频率 |
|------|------|------|
| 决策备忘录、漏斗对齐 | Cursor Agent / Claude / Gemini | 按需 |
| Runway 粗算、表格 | 表格 + AI 填公式说明 | 每周 |
| BIP 长文润色 | AI 起草 → 人改口吻 | 每周 |

### CMO / 增长

| 任务 | 工具 | 频率 |
|------|------|------|
| 竞品 teardown 初稿 | AI + 人工核实价格 URL | 每个 niche |
| Landing / 推文 / Reddit 回复 | AI 多版本 → 人选 1 版 | 每日 |
| 访谈问题清单 | AI 生成 → CEO 删至 ≤10 问 | 每个 niche |
| 用户引用整理 | 访谈笔记 → AI 结构化 | 每次访谈后 |

### CTO / 交付

| 任务 | 工具 | 频率 |
|------|------|------|
| Spike / MVP 编码 | **Cursor**（主 IDE） | 每日（限 Stage 内额度） |
| 单元测试、样板、重构 | AI 生成 + 人审 security | 每 PR |
| Log 分析、GraalVM 报错解析 | AI + 专用 prompt | Spike 期 |
| Code review | AI 第一轮 → 人看支付/ auth 路径 | 每次合并前 |

### COO / 运营

| 任务 | 工具 | 频率 |
|------|------|------|
| SOP 维护、checklist | AI 从日志提炼 | 每周 |
| 客服邮件初稿 | AI + 宏模板 | 有客户后 |
| 发票 / 订阅对账 | Stripe Dashboard；AI 仅解释异常 | 每周 |

---

## 3. API COGS 与 Margin 红线

### 3.1 估算模板（每个含 AI 的 SKU 必填）

| 项 | 值 |
|----|-----|
| 平均每用户每月 API 调用 | ____ |
| 单次调用成本（USD） | ____ |
| **月 COGS / 用户** | ____ |
| 售价 / 用户 / 月 | ____ |
| **Gross margin** | ____% （目标 ≥ 70%） |

### 3.2 红线

| 规则 | 动作 |
|------|------|
| Margin < 50% 且无法提价 | 改 SKU 或减 AI 调用（缓存、规则引擎、本地小模型） |
| 免费档消耗 AI | **禁止**（免费只做静态 preview） |
| 未设 usage cap | 上线前必须设 per-user / global daily cap |
| API key 在客户端 | **禁止** — 仅 server-side |

### 3.3 降 COGS 手段（按优先级）

1. 规则 + 正则解决 80% Case，AI 只处理长尾  
2. 缓存相同 log hash 的分析结果  
3. 更小 / 更便宜模型做分类，大模型做最终一步  
4. Batch 非实时任务  

---

## 4. 人机分工矩阵

| 任务 | 人 | AI | 不可委托 |
|------|:--:|:--:|----------|
| Kill / pivot 决策 | ✓ | | ✓ |
| 定价数字 | ✓ | 建议 | ✓ |
| 用户访谈 live | ✓ | | ✓ |
| 公开 BIP 叙事口吻 | ✓ | 草稿 | 最终发布人 |
| 支付 / webhook / auth | 审 | 样板 | 安全路径 |
| 竞品价格核实 | ✓ | 搜 | 以官网为准 |
| 批量文案 variant | 选 | ✓ | |
| 样板 CRUD / 测试 | 审 | ✓ | |

---

## 5. Prompt / 模板落盘约定

| 类型 | 建议路径 | 示例 |
|------|----------|------|
| 访谈提纲 | `docs/01-market-research/prompts/` | `interview-graalvm.md` |
| Landing 文案 | 与 offer 同目录 | 从 one-pager 生成 |
| Log 分析 | `docs/02-product-mvp/prompts/` | `native-image-error-parse.md` |
| 客服宏 | `docs/03-growth-and-automation/prompts/` | `support-access-grant.md` |

**版本：** prompt 文件头注明 `Last verified: YYYY-MM-DD` 与适用模型。

---

## 6. 订阅预算（COO 台账）

| 工具 | 约 $/mo | Stage |
|------|---------|-------|
| Cursor Pro | ~20 | A+ |
| 域名 + 邮件 | ~5 | A+ |
| Plausible 等 analytics | 0–9 | B+ |
| OpenAI / Anthropic API | 按量 | 仅 C+ 且 SKU 需要 |
| Lemon Squeezy | 按交易 | 若选 MoR |

新增工具 → CEO Decision Log 一行。

---

## 7. Weekly AI 审计（周日 5 分钟）

```markdown
### AI ops
- 本周 AI 工具订阅 + API 总支出：$__
- 是否超过 runway 预算：Y/N
- 是否有任务本可脚本化却仍手工：__
- Prompt 模板是否更新：Y/N
```

---

## 关联文档

| 文档 | 关系 |
|------|------|
| [`../../roles/CTO-chief-technology-officer.md`](../../roles/CTO-chief-technology-officer.md) | AI-Native 研发 |
| [`../../daily_sop.md`](../../daily_sop.md) | 每日帽子循环 |
| [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md) | M3 unit economics |
| [`../00-constraints/runway-and-living-wage.md`](../00-constraints/runway-and-living-wage.md) | 工具 burn |

---

*AI compresses time; it does not replace money language from buyers.*
