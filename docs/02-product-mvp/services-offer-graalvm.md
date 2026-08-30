# GraalVM Native Image — 咨询包执行单（现金轨）

**用途：** 现金轨 — 在 SaaS 自动化之前，用 **高单价交付** 换 runway 与验证素材  
**与 SaaS 关系：** 同一 ICP、同一痛点；咨询 = Concierge，SaaS = 重复步骤的产品化  
**前置：** 无 Gate 要求；Runway **< 6 个月** 或 CEO 书面批准「加速现金」时 **立刻启动**  
**时间盒：** 首单签约 2–4 周；单次交付 2–5 个工作日  
**Last updated:** 2026-08-30

> 不卖「AI 聊天」，卖 **可 commit 的 Native Image 配置 + 可重复构建**。  
> 不卖时间，卖 **结果** —— 用固定价 SKU，不用「按小时」报价（除非 Retainer）。

---

## 0. 启动前快筛（5 个 Yes 才开现金轨）

- [ ] 能在 48h 内触达 ≥5 个「Spring Boot 3 + Native Image 失败」的工程师 / CTO  
- [ ] 能交付：**reflect-config / resource-config 片段 + 构建通过说明**（非仅口头建议）  
- [ ] Stripe / 银行可收 **USD**（Invoice 或 Wire；国内客户可单独开 CNY 通道，不默认）  
- [ ] 书面承诺：**咨询时间 ≤ 总工时的 50%**（另一半留给 SaaS 验证 / 产品化）  
- [ ] 已填 [`runway-and-living-wage.md`](../00-constraints/runway-and-living-wage.md) 的 Runway 数字  

**任一 No → 先补能力或 ICP，再卖。**

---

## 1. 定位与 ICP（买家，不是用户）

### 1.1 一句话 Offer

```text
For: Staff engineers / CTOs shipping Spring Boot 3 to AWS Lambda or Google Cloud Run
Pain: Native Image build fails on reflection/JNI/resources — blocks serverless launch for days
Outcome: Working native build + commit-ready config in 48–96h — not another ChatGPT guess
Price: From $2,500 fixed (Quick Fix) — not hourly consulting
NOT for: Greenfield apps with zero Native Image attempt, or teams wanting full managed SRE
```

### 1.2 ICP 画布（复制填写）

| 字段 | 内容 |
|------|------|
| **谁刷卡** | Staff / Principal Eng、2–20 人初创 CTO |
| **触发时刻** | CI 红了一周；生产要上 Lambda/Cloud Run；reflect-config 手工维护失控 |
| **已在付什么** | 工程师时薪 $50–150/h；偶尔外包；$20/mo ChatGPT（不够用） |
| **愿付区间** | **$2.5k–$8k/项目** 或 **$3k–$6k/mo** Retainer |
| **在哪出现** | r/java、r/springboot、Spring GitHub Discussions、HN、LinkedIn、前同事网络 |

### 1.3 与 SaaS Landing 的双漏斗

同一 Landing 页挂 **两个 CTA**（见 [`landing-page-checklist.md`](landing-page-checklist.md)）：

| CTA | 受众 | 价格 | 交付 |
|-----|------|------|------|
| **Buy SaaS / Pre-order** | 愿自助、预算 <$100/mo | $19–29/mo | 工具 / 手工 onboarding |
| **Book Fix Call / Get Quote** | 要结果、预算 $2k+ | $2.5k+ | 本执行单 |

**规则：** 咨询客户 = SaaS 的 **种子用户 + 案例来源**；交付后问一句：「若 80% 步骤自动化，愿付 $__/mo 吗？」

---

## 2. SKU 与定价（固定价，三档）

直到 **第 3 单咨询** 完成前，**只推一档主推**（建议 Quick Fix），避免选择疲劳。

### SKU A — Native Image Quick Fix（主推）

| 项 | 内容 |
|----|------|
| **价格** | **$2,500 USD** 固定价（一次性 Invoice） |
| **时效** | 签约后 **48–72h** 交付首版；含 **1 轮** 修订（7 天内） |
| **输入** | 失败 CI log + `pom.xml`/`build.gradle` + 目标平台（Lambda / Cloud Run） |
| **输出** | ① 可 commit 的 `reflect-config.json` / `resource-config.json` 片段 ② 构建命令与文档 ③ 15min 交接 Loom |
| **不含** | 生产监控、全库迁移、非 Spring 栈、无限轮次支持 |

**ROI 锚点：** 4h 调试 × $75/h = $300/次失败；一周失败 = $1,500+ → $2,500 合理。

### SKU B — Serverless Migration Audit

| 项 | 内容 |
|----|------|
| **价格** | **$5,000–$8,000 USD**（按模块数报价；默认 $6,500） |
| **时效** | **5–10 个工作日** |
| **输入** | 1–3 个 Spring Boot 服务、当前部署方式、SLO 要求 |
| **输出** | ① Native 可行性评估 ② 分阶段迁移路线图 ③ 风险清单（冷启动、内存、构建时间）④ 1 个试点服务的 Quick Fix 配置 |
| **不含** | 全团队培训、长期 on-call、非 Java 服务 |

### SKU C — Fractional Native Image Lead（Retainer）

| 项 | 内容 |
|----|------|
| **价格** | **$4,000–$6,000 USD/月**（每月上限 **20h**，超出按 $250/h 或升级档） |
| **时效** | 按月续约；**4 周 notice** 取消 |
| **适合** | 持续把 monolith 拆到 serverless、多服务 Native 化的团队 |
| **输出** | 每周同步、CI 门禁建议、新依赖的 metadata 审查 |
| **不含** | 24/7 on-call、生产事故第一时间响应 |

### 定价决策表（CEO 勾选主推）

- [ ] **主推 SKU A** — 最快成交、最短交付、最适合攒案例  
- [ ] 主推 SKU B — 仅当有 ≥2 个「整包迁移」访谈信号  
- [ ] 主推 SKU C — 仅当有 1 个明确 Retainer 意向  

**收款方式：** Stripe Invoice（推荐）→ 50% 开工前 / 50% 交付验收；或 100% 预付给 **-10%** 早鸟（可选）。

---

## 3. 交付范围（Scope）— 写进合同 / SOW

### 3.1 包含（In scope）

- [ ] Spring Boot **3.x** + Maven 或 Gradle  
- [ ] 目标：**AWS Lambda** 或 **Google Cloud Run**（二选一 per 项目）  
- [ ] GraalVM Native Image / Spring AOT 相关 metadata  
- [ ] 脱敏后可作案例 study（需客户书面同意）  

### 3.2 不包含（Out of scope）— 必须书面排除

- [ ] 非 JVM 语言、非 Spring 框架  
- [ ] 生产环境 on-call、SLA 保证 uptime  
- [ ] 安全渗透、合规认证  
- [ ] 无限次「又加一个依赖」迭代（超出 1 轮修订 → 新 SOW 或 SKU C）  
- [ ] 代写业务代码、功能开发  

### 3.3 交付物清单模板

```markdown
## Delivery — [Client] — [Date]

### Environment
- Spring Boot: ___
- GraalVM: ___
- Target: Lambda / Cloud Run
- Build tool: Maven / Gradle

### Artifacts
- [ ] reflect-config.json (snippet or full)
- [ ] resource-config.json (if needed)
- [ ] native-maven-plugin / gradle config diff
- [ ] README: build & deploy steps

### Verification
- [ ] Local or CI native build PASS (screenshot / log excerpt)
- [ ] Client sign-off email

### SaaS seed (internal)
- Repeated steps for productization: ___
- WTP for automated tool: $___/mo Y/N
```

---

## 4. Week 1–2 — 获客执行（可勾选）

### Day 1：资产就绪

- [ ] 一页 **Services** 区块上线（可与 SaaS 同域 `/services` 或同页下半屏）  
- [ ] Calendly **20min Discovery** 链接（免费，用于资格筛选）  
- [ ] Stripe Invoice 模板（SKU A = $2,500）  
- [ ] 准备 **1 份脱敏样本**：失败 log → 配置片段（可来自 spike，见 [`tech-spike-template.md`](tech-spike-template.md)）  
- [ ] 英文邮件签名加一行：`Native Image stuck? Fixed-price rescue — [link]`

### Day 2–3：社区侦察（每天 2h）

**Reddit / GitHub 搜索词（收藏 10 帖）：**

| 平台 | 搜索词 |
|------|--------|
| Reddit | `native image spring boot`, `reflect-config`, `graalvm build failed` |
| GitHub | `native-image` + `spring-boot` in Issues |
| Google | `site:stackoverflow.com graalvm spring boot reflection` |

**回复原则：** 先给 **可操作的 3 步排查**，最后一句软 CTA（不 spam）：

```text
If you're still blocked after trying the above, I do fixed-price Native Image rescues
for Spring Boot → Lambda/Cloud Run (48–72h, commit-ready configs). DM or [calendly link].
```

- [ ] 完成 **10 条** 高质量回复（无复制粘贴）  
- [ ] 记录帖链到 `docs/04-indie-log/daily-logs/`  

### Day 4–5：外联（15 人）

| 渠道 | 人数 | 动作 |
|------|------|------|
| 前同事 / 猎头 | 5 | 私信「接 Native Image / Spring serverless 短期项目」 |
| LinkedIn | 5 | CTO / Staff Eng，连接后不发长文，只问「你们上 Native 了吗」 |
| Indie Hackers / HN Ask | 1 帖 | 「Who paid to fix GraalVM Native Image builds?」 — 调研帖，非硬广 |

- [ ] 发出 **15 条** 外联  
- [ ] 预约 ≥ **3 场** Discovery Call  

### Day 6–14：Discovery → Close

**Discovery Call 脚本（20min）：**

| # | 问题 | 记录 |
|---|------|------|
| Q1 | 上次 Native build 失败是什么时候？卡多久？ | |
| Q2 | 目标平台？Spring Boot 版本？ | |
| Q3 | 现在谁在处理？大概花了多少工程师时间？ | |
| Q4 | 若 **72h 内** 拿到可 commit 配置 + 构建通过，值 $2,500 吗？ | |
| Q5 | 决策谁拍板？能本周签合同吗？ | |

**关单话术（Q4 为 Yes 后）：**

```text
I'll send a one-page SOW: fixed $2,500, 50% upfront, deliverables listed.
If we don't get a passing native build in scope, you don't pay the second 50%.
```

- [ ] 完成 ≥ **5 场** Discovery  
- [ ] 发出 ≥ **2 份** SOW / Invoice  
- [ ] **首单签约** 或记录 Kill 原因  

### Week 2 Gate（CEO 判定）

| 指标 | 通过线 | 实际 |
|------|--------|------|
| Discovery Call | ≥5 | |
| 承认「阻塞发布」痛点 | ≥3 | |
| SOW / Invoice 发出 | ≥2 | |
| **签约 / 到款** | ≥1 **或** ≥2 书面「发 Invoice 就付」 | |

**结论（勾选一项）：**

- [ ] **Go** — 交付首单；重复步骤记入 SaaS backlog  
- [ ] **Pivot** — 改价格（$1,999 试验）/ 改 wedge（仅 Cloud Run）/ 改渠道  
- [ ] **Pause** — 2 周零 money language → 回 [`icp-discovery-playbook.md`](../01-market-research/icp-discovery-playbook.md) 重审 ICP  

---

## 5. 招募话术库（复制即用）

### 5.1 Reddit 回复结尾（英文）

```text
Full disclosure: I'm an indie engineer specializing in Spring Boot → Native Image
for Lambda/Cloud Run. Happy to help more in thread; also offer fixed-price rescues if needed.
```

### 5.2 LinkedIn 连接请求（英文）

```text
Hi [Name] — saw you're on Spring Boot / serverless. I'm researching where Native Image
builds hurt most. Open to a 15min swap of war stories? No pitch.
```

### 5.3 前同事 / 猎头（中文）

```text
我最近在独立做 Spring Boot / GraalVM Native Image 方向，接固定价排障和 Serverless 迁移评估。
如果你有团队卡 Native 编译、或者朋友公司要上 Lambda/Cloud Run，可以介绍，成单有介绍费（10%）。
```

### 5.4 Discovery 跟进邮件（英文）

```text
Subject: SOW — Native Image Quick Fix — [Company]

Hi [Name],

As discussed: fixed USD 2,500 for:
• Commit-ready reflect/resource config for [service]
• Passing native build on [Lambda/Cloud Run]
• 1 revision round within 7 days
• 15min handoff recording

Timeline: 48–72h after 50% deposit.
Invoice: [Stripe link]

Out of scope: [link to section 3.2]

Reply "approved" and I'll start on receipt.

[Your name]
```

### 5.5 交付后 — SaaS 转化（英文）

```text
If we automated steps 2–4 of what I did manually, would $29/mo be a no-brainer
for your team? (Y/N — helps me prioritize the tool roadmap.)
```

---

## 6. 与 SaaS 产品化衔接

```text
咨询交付 1–3 单
  → 记录重复步骤（解析 log、匹配模板、生成 config）
  → 写入 SaaS MVP backlog（Idea 1 GraalVM 助手）
  → 咨询客户优先 beta + annual 折扣
  → 案例 study（脱敏）放 Landing「Proof」
```

| 咨询中的重复步骤 | SaaS 功能 |
|------------------|-----------|
| 从 log 提取 missing class/method | Log parser |
| 匹配 Spring Boot 3 常见依赖模板 | Template library |
| 生成 config 片段 | Export / PR bot（Phase 2） |
| 交接 Loom | 文档 → 自助 onboarding |

**铁律：** 未在咨询里手工做过 ≥2 次的步骤，**不进 SaaS v1**。

---

## 7. 风险、退款与 Kill

| 风险 | 缓解 |
|------|------|
| Scope creep | SOW 写死 §3.2；加依赖 = 新 SOW |
| 构建仍失败（边缘库） | 合同：「best effort within scope」；第二档 50% 与结果挂钩 |
| 客户要「包上线」 | 引导 SKU B 或 Retainer，不做 $2.5k 全包 |
| 卖时间陷入小时计费 | **只卖 SKU**；小时数仅内部估算 |

**退款：** 首版交付后若 **in-scope** 仍无法 native build，**第二笔 50% 不收**；已做工作不退第一笔 50%（SOW 写清）。

**Kill 现金轨（回纯 SaaS）若：** Runway ≥ 9 个月 **且** SaaS MRR ≥ $500 **且** 咨询占用 >50% 时间。

---

## 8. 本周时间分配（与 SaaS 并行）

| 占比 | 活动 |
|------|------|
| **50%** | 现金轨：回复、外联、Discovery、交付 |
| **30%** | SaaS：访谈、spike、Landing |
| **15%** | 产品化：记录重复步骤 |
| **5%** | 新点子脑暴 — **零** |

Runway **< 4 个月** → 现金轨升至 **70%**（见 runway 文档）。

---

## 9. 关联文档

| 文档 | 用途 |
|------|------|
| [`monetization-strategy.md`](monetization-strategy.md) §3.5 | Concierge → Product |
| [`niche-graalvm-native-image-teardown.md`](../01-market-research/niche-graalvm-native-image-teardown.md) | ICP、竞品、定价带 |
| [`icp-discovery-playbook.md`](../01-market-research/icp-discovery-playbook.md) | 访谈与 Gate（Q1–Q7 一致） |
| [`landing-page-checklist.md`](landing-page-checklist.md) | 双 CTA Landing |
| [`runway-and-living-wage.md`](../00-constraints/runway-and-living-wage.md) | 何时拉满现金轨 |
| [`offer-one-pager-template.md`](offer-one-pager-template.md) | SaaS offer 副本 |

---

## 10. 快速参考卡

```text
ICP:     Spring Boot 3 CTO / Staff Eng，Native Image 阻塞 serverless
主推:    SKU A — $2,500 / 48–72h / commit-ready config
渠道:    r/java + Spring Discussions + 前同事
本周:    10 回复 + 15 外联 + 5 Discovery
通过线:  ≥1 签约 或 ≥2「发 Invoice 就付」
下一步:  交付 → 记重复步骤 → SaaS beta 邀请
```

---

*咨询赚 runway；SaaS 赚复利。同一买家，两条漏斗。*
