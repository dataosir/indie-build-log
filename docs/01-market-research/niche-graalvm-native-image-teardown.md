# Niche Teardown — GraalVM / Spring Native Image (Java Serverless)

**Status:** Draft v1 — Week 2 deliverable (F2)  
**Related scorecard:** [`idea-scorecard-2026-08-28.md`](idea-scorecard-2026-08-28.md)  
**Last updated:** 2026-08-28

> Teardown 目的：确认 **价格带、竞品槽点、分销入口** — 不是写 PRD。  
> Goal: price band, competitor gaps, and distribution hooks — not a PRD.

---

## 1. Niche 定义（收窄后）

| 字段 | 内容 |
|------|------|
| **Micro-niche** | Spring Boot 3.x 团队把服务编译为 GraalVM Native Image 部署到 **AWS Lambda / Cloud Run** |
| **Buyer** | Staff/Principal engineer、初创 CTO（2–20 人） |
| **Pain** | Native Image 构建失败（reflection/resource/JNI），反复手工维护 `reflect-config.json`，阻塞 serverless 上线 |
| **Outcome** | 从失败 log → 可用配置 + 可重复构建脚本，**小时级 → 分钟级** |
| **Wedge** | 专注 **Spring Boot + 常见第三方库** 元数据，而非通用 Native Image GUI |

---

## 2. 竞品与替代（待核实 URL — 访谈时补截图）

| 名称 | 类型 | 定价（公开） | 强项 | 槽点 / 机会 |
|------|------|--------------|------|-------------|
| **Spring Native / AOT 文档** | 官方 | 免费 | 权威 | 不解决第三方库长尾反射 |
| **GraalVM Reachability Metadata** | 官方 tooling | 免费 | 底层正确 | 学习曲线陡，报错不友好 |
| **Native Build Tools (Gradle/Maven plugin)** | 开源 | 免费 | 集成 | 仍要人工补 metadata |
| **通用 CI 编译服务** | SaaS |  varies | 托管构建 | 贵、非 Spring 专用 |
| **ChatGPT / 通用 AI** | 替代 | $20/mo | 快 | 无项目上下文、幻觉配置 |
| **DIY** | 替代 | 工程师时薪 | 可控 | 重复劳动、不可复用 |

**差异化假设（待访谈验证）：**

1. 上传 **CI log** 即可得 **可 commit 的 config 片段**（非聊天建议）  
2. 内置 **Spring Boot 3 常见依赖** 模板库（团队可共享）  
3. CLI 本地免费限次 + 云端深度分析 $19–29/mo  

---

## 3. 定价景观

| 层级 | 市场参考 | 本 Offer 草案 |
|------|----------|---------------|
| 开源/DIY | $0 + 时间 | CLI 本地分析免费 N 次/月 |
| Prosumer | $9–29/mo dev tools | **$19/mo** 或 **$29/mo** 云分析 + 模板库 |
| Team | $49–99/mo | Phase 2：共享模板、seat |

**ROI 锚点：** 若工程师 $50/h，一次 Native Image 调试 4h = $200 → $29/mo 无压力。

---

## 4. 分销入口（48h 内可触达）

| 渠道 | 具体位置 | 动作 |
|------|----------|------|
| **Reddit** | r/java, r/springboot, r/aws, r/googlecloud | 回答 Native Image 报错帖，附 checklist |
| **X/Twitter** | #SpringBoot #GraalVM #NativeImage | BIP 短帖 + 失败 log  anonymized 案例 |
| **GitHub** | spring-projects, graalvm, 本 BIP repo | Issues/discussions 帮忙，不 spam |
| **HN** | Show 前需真实 demo | Phase 2 |
| **SEO** | 长尾：`native image spring boot reflection error` | Landing FAQ 对齐 |

---

## 5. 风险

| 风险 | 严重度 | 缓解 |
|------|--------|------|
| Spring/GraalVM 官方继续自动化 | 中 | 垂直第三方库长尾 + 团队模板 |
| 「又一个 AI wrapper」 | 中 | 卖 **可 commit 的 artifact**，不卖聊天 |
| Support 爆炸（每项目不同） | 中 | 限 Scope：仅 Spring Boot 3 + Maven/Gradle |
| 市场偏小 | 低–中 | 高 ARPU + 扩 CI 集成 |

---

## 6. 访谈问题（CMO 用）

1. 你现在 Native Image 构建频率？最近一次失败原因？  
2. 你花多少时间在 reflect-config / resource-config 上？  
3. 你现在付过什么工具钱解决构建/部署？  
4. 若工具从 log 生成 80% 正确配置，你愿意付 $__/mo 吗？  
5. 你更想要 CLI、GitHub Action、还是网页上传 log？  

---

## 7. Teardown 完成定义（F2）

- [ ] ≥ 3 竞品定价 **截图或链接** 存档  
- [ ] ≥ 5 次访谈引用写入 [`offer-graalvm-native-v1.md`](../02-product-mvp/offer-one-pager-template.md) 副本  
- [ ] Landing 关键词列表 10 条  
- [ ] CEO：Go / Pivot / Kill 签字  

---

## 关联

| 文档 | 用途 |
|------|------|
| [`offer-one-pager-template.md`](../02-product-mvp/offer-one-pager-template.md) | Offer v1 |
| [`../03-growth-and-automation/distribution-channels.md`](../03-growth-and-automation/distribution-channels.md) | 渠道节奏 |

---

*Competitor prices change — verify before launch.*
