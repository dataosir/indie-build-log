# Idea Intake SOP — 新点子四角色评审流程

**Audience:** 创始人 + AI 秘书（goose）  
**触发：** 你抛出一个新商业/产品点子  
**产出：** 可行性结论、优缺点、衍生方案、落盘位置  
**关联：** [`business-framework.md`](business-framework.md) · [`initial-brainstorming.md`](initial-brainstorming.md) · [`../INDEX.md`](../INDEX.md)

---

## 1. 你给秘书的输入（复制改字即可）

```markdown
新点子：<一句话描述>

背景（可选）：
- 来源 / 灵感：
- 想解决谁的什么问题：
- 和现有主线（GraalVM）关系：
- 时间预算（如每周 ≤4h）：
```

**秘书收到后自动执行 §2–§5**，无需你再指定角色。

---

## 2. 四角色圆桌（固定顺序，不可跳过）

每个角色只答自己该答的；最后由 **CEO 综合拍板**。

### Round 1 — CMO（市场与买家）

| 检查项 | 输出 |
|--------|------|
| 买家是谁？预算在谁卡里？ | ICP 一句话 |
| 竞品 / 替代品（≥3） | 表格：名称、定价、槽点 |
| 分发渠道可达吗？ | 红/黄/绿 |
| 合规 / 平台政策 | 有无硬 Kill 项 |
| 与 Global USD 战略契合度 | ✅ / ⚠️ / ❌ |

**CMO 一句话：** 「谁会付钱、在哪遇到他们、最大竞品 wedge 是什么。」

### Round 2 — CTO（技术与 MVP）

| 检查项 | 输出 |
|--------|------|
| v1 最小范围（One Killer Feature） | ≤3 条 bullet |
| 技术风险点 | 需否 Tech Spike（引用 [`tech-spike-template.md`](../02-product-mvp/tech-spike-template.md)） |
| 预估构建时间 | 小时 / 天 |
| 与创始人技术栈协同 | ✅ / ⚠️ / ❌ |
| Stage B 之前是否该写代码 | **默认：否** |

**CTO 一句话：** 「多快能用手工 Concierge 验证，多快才值得开 repo。」

### Round 3 — COO（维护与落盘）

| 检查项 | 输出 |
|--------|------|
| 持续维护负担 | 低 / 中 / 高 |
| 支持 / 合规 / 内容审核成本 | 估算 |
| 应写入哪个文件 | 见 §4 落盘规则 |
| 是否需更新 [`INDEX.md`](../INDEX.md) | 是 / 否 |

**COO 一句话：** 「这是一次性实验还是长期运营负债。」

### Round 4 — CEO（战略拍板）

| 检查项 | 输出 |
|--------|------|
| 硬过滤 7 项（[`business-framework.md`](business-framework.md) §4） | PASS / FAIL + 逐项 |
| 软打分 8 维（0–5） | 总分 /40 |
| 与 Primary bet 时间冲突 | 是否挤占 Week 2–4 Validation |
| **最终裁决** | 见 §3 状态机 |

**CEO 一句话：** Kill / 沙盒观察 / 进 Scorecard / 进 Validation / 兴趣轨限量。

---

## 3. 状态机（点子的一生）

```
[你抛点子]
    ↓
[四角色评审] ──→ 输出：优缺点 + 衍生树 + 裁决
    ↓
┌───────────────────────────────────────────────────┐
│ Kill          │ 记录 Kill 原因，不花时间           │
│ 沙盒 Sandbox  │ 写入 brainstorming，每周 ≤4h 可摸  │
│ Scorecard     │ 单独打分表或并入 scorecard         │
│ Validation    │ 进 ICP playbook 7 天 + Concierge     │
│ 兴趣轨        │ 与主线并行，有收入上限预期           │
│ 衍生 Backlog  │ 挂在父 Idea 拓展树，标签 🟡/✅/❌   │
└───────────────────────────────────────────────────┘
```

| 状态 | 含义 | 下一步 |
|------|------|--------|
| **Kill** | 硬过滤 ≥2 项 FAIL 或软分 <20 | 只在 brainstorming 留档 + Kill 原因 |
| **沙盒** | 有趣但未验证，或合规/战略黄灯 | 拓展树 + 可选 8h Concierge |
| **Scorecard** | 硬过滤全过，值得与 Top 1 比 | 写入/更新 `idea-scorecard-*.md` |
| **Validation** | Scorecard ≥25 且 CEO 批时间 | `icp-discovery-playbook.md` + ADR |
| **兴趣轨** | 非 USD 主业但可练手/现金流 | 限量时间，不进 Primary bet |
| **衍生 Backlog** | 从父点子拆出，暂不独立验证 | 拓展树表格，标 `来源 Idea N-x` |

---

## 4. 落盘规则（写到哪里）

| 产出物 | 路径 | 何时写 |
|--------|------|--------|
| 新 Idea 主记录 | [`initial-brainstorming.md`](initial-brainstorming.md) | 每个新点子一个 `## Idea N` |
| 拓展树 / 衍生点子 | 同上，父 Idea 下 `### 拓展树` | 评审时同步拆 |
| 深度调研（竞品、合规） | `niche-<slug>-teardown.md` | 进 Validation 或沙盒需留存 |
| 正式打分 | `idea-scorecard-YYYY-MM-DD.md` | 进 Scorecard 时 |
| 架构决策 | `docs/02-product-mvp/adr-*.md` | 决定 Concierge / 技术路线时 |
| CEO 重大裁决 | `roles/CEO-chief-executive-officer.md` §2.2 决策日志 | Kill Primary 级冲突时 |
| **目录同步** | [`docs/INDEX.md`](../INDEX.md) | **任何新文件同一轮必更新** |

### Idea 编号规则

- 全局递增：`Idea 10`, `Idea 11`, …
- 衍生点子**不抢新编号**，挂在父 Idea 拓展树（如 `Idea 4-B3` → 长大后再升格为 `Idea 8`）
- 升格时：拓展树留链接，新 Idea 头标注 `来源：Idea N-x`

---

## 5. 评审输出模板（秘书每次按此结构回复）

秘书对用户可见的回复应包含以下章节（可简写，但不可缺）：

```markdown
## 点子拆解
（用户原话 → 分层表格：题材 / 载体 / 场景 / 买家）

## 四角色摘要
| 角色 | 结论 | 关键一句 |
|------|------|----------|
| CMO | … | … |
| CTO | … | … |
| COO | … | … |
| CEO | … | … |

## 优缺点
### 优点（≤5）
### 缺点 / 风险（≤5，含合规）

## 硬过滤 + 软打分
（表格，引用 business-framework）

## 衍生方案与拓展树
（表格：子点子 / 买家 / 契合度 / 建议状态）

## 裁决与建议下一步
- 状态：Kill | 沙盒 | Scorecard | Validation | 兴趣轨
- 若验证：Concierge 剧本（≤8h）
- 时间预算建议

## 已落盘
- [ ] initial-brainstorming.md → Idea N
- [ ] INDEX.md 已更新
- [ ] （其他文件）
```

---

## 6. 衍生点子：哪些要记录、哪些不用

| 类型 | 记录？ | 放哪 | 标签 |
|------|--------|------|------|
| 同题材换场景（如「睡前→通勤」） | ✅ | 父 Idea 拓展树 §场景 | 🟡 |
| 换买家（听众→创作者） | ✅ | 拓展树 §买家 / 可升格新 Idea | 🟡→✅ |
| 合规安全变体（架空 IP 替换名著） | ✅ | 拓展树 §合规 + 备注 | 🟡 |
| 与现有 Idea 重复 | ✅ 合并 | 标注 `→ 见 Idea N` | 🔗 |
| 明显拍脑门、无买家 | ❌ 不单独记 | 评审正文提一句即可 | — |
| 6 个月内不会做但有价值 | ✅ | 拓展树 + INDEX 点子表备注 | 📦 Backlog |

---

## 7. 与现有流程的衔接

```
新点子
  → idea-intake-sop（本文件）四角色评审
  → initial-brainstorming 沙盒
  → [可选] icp-discovery-playbook 7 天
  → idea-scorecard 打分
  → [Gate] business-framework Stage B
  → product-mvp / concierge / tech-spike
  → indie-log 周报存档
```

**铁律（来自 CEO / CTO）：**

- Stage B 未过 → **不开产品 repo**
- 沙盒点子 → 每周 ≤4h，不得挤占 Primary bet Validation
- 硬过滤 FAIL → **不进入 Scorecard**，除非垂直化后重新评审

---

## 8. COO 收尾检查清单

每次点子评审结束后，秘书自检：

- [ ] `initial-brainstorming.md` 已写入/更新 Idea N
- [ ] 拓展树已拆，衍生点子有状态标签
- [ ] [`docs/INDEX.md`](../INDEX.md) 点子索引行已更新
- [ ] 若新建文件 → INDEX 对应分区已加行
- [ ] 若 Kill Primary 级方向 → CEO 决策日志已记
- [ ] 用户回复含 §5 完整结构

---

*抛点子 → 四角色吵完 → 落盘 → 更新目录。不要只在聊天里想清楚。*
