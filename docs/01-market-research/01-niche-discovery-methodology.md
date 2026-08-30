# 利基探索与定位方法论 (Niche Discovery & Positioning Methodology)

> **当前帽子：CMO / CEO**
> *“大公司在寻找市场，而独立创始人是在寻找‘生态缝隙’。缝隙太小，大厂不屑于进入；缝隙极痛，客户愿意用信用卡投票。”*

本指南旨在为一人公司的市场调研（Market Research）提供一套标准化、可复制的作业程序（Playbook）。即便你现在还没有明确的产品想法，也可以通过这套方法论在 1-2 周内筛选出 3 个高胜率的 Niche。

---

## 1. 寻找利基的四大黄金水源 (Where to Look)

作为 Senior Java / Backend 背景的 Founder，你的主场应该在 **开发者、技术主管、系统运维和数据工程** 等专业和 prosumer 赛道（即 Developer-adjacent Niche）。

### 渠道 A：Reddit 痛点采矿法 (Reddit Pain Mining)
Reddit 是全球最活跃的真实痛点发源地。用户在这里不加修饰地抱怨各种工具的难用之处。
- **目标 Subreddits**：`r/java`, `r/springboot`, `r/selfhosted`, `r/aws`, `r/solopreneur`, `r/saas`。
- **常用搜索关键词**（在 Sub 内检索）：
  - `How do you guys solve...` (你们怎么解决...)
  - `Is there an alternative to...` (有什么替代品...)
  - `X is too expensive` (X 太贵了)
  - `X is frustrating` / `X sucks` (X 让人沮丧 / 太垃圾了)
  - `Is anyone else experiencing...` (有人也遇到过...吗)

### 渠道 B：竞品“差评”截流法 (Competitor Bad Reviews)
找到该赛道的头部或腰部产品，专门研究用户的抱怨，在痛点处建立你的 **Wedge（切入切片）**。
- **目标平台**：G2.com, Capterra, AlternativeTo, Trustpilot。
- **操作动作**：
  1. 搜集竞品的 1 星至 3 星差评。
  2. 归纳吐槽最多的点，通常是：
     - *“价格突然翻倍（Pricing shock）”* -> 机会：推出定价更透明、更适合中小团队的替代版。
     - *“功能太重、UI 太复杂，我只需要其中一个核心功能”* -> 机会：做极简版、单功能单兵工具（One-Feature SaaS）。
     - *“客服响应太慢，配置复杂”* -> 机会：提供开箱即用、带极速技术支持的利基服务。

### 渠道 C：GitHub “非完美”开源项目商业化 (Commercializing Open Source Pain)
很多优秀的开源工具能解决问题，但对非技术或半技术用户来说有“最后一公里”的门槛。
- **寻找目标**：
  - 在 GitHub Trending 寻找那些 Star 增长快但没有商业化/云端托管版本的开源工具。
  - 寻找那些配置极度繁琐，需要拉 Docker、配环境、写 YAML 的工具。
- **机会点**：
  - **Cloud Hosting / Managed SaaS**：提供 1-Click 托管和高可用备份。
  - **GUI / Companion Tool**：为纯 CLI（命令行）的优秀开源工具配一个精致、简单易用的 UI。
  - **API-fy**：将复杂的开源本地库包装成一个高可用的 API 接口（按量计费）。

### 渠道 D：生态系统插件法 (Ecosystem Micro-Apps)
寄生在巨大的生态帝国上，通过提供高价值插件或微型应用生存。
- **目标生态**：
  - IntelliJ IDEA 插件市场 (JetBrains Marketplace)
  - AWS Marketplace / Cloudflare Workers Ecosystem
  - Vercel Integration Marketplace
  - Chrome Extension Store
- **机会点**：大平台的某些痛点需要专门的第三方工具进行微调。例如：一个针对 Java 微服务在 Serverless 架构（如 AWS Lambda）下冷启动问题的极简预热工具。

---

## 2. Niche 筛选与漏斗过滤 (The Filtering Process)

每当你记录下一个潜在 Niche，必须带入 `docs/01-market-research/business-framework.md` 里的 **Micro-Niche Scorecard** 进行强行打分。

### 核心过滤问题（CEO 与 CMO 双重拷问）：
1. **这是“感冒药 (Nice-to-have)”还是“止痛药 (Must-have)”？**
   - 用户不用你的工具，今天是不是就会损失金钱、浪费大量时间、或者面临安全/合规风险？如果是，这就是止痛药。
2. **目标受众是否拥有信用卡，且有自主采购权？**
   - 如果受众是“大厂里的基层 Java 程序员”，他即使喜欢，也无法决定公司的采购。
   - 如果受众是“自由职业者”、“外包工作室主管”或“初创公司 CTO”，他们掏信用卡的链路极短，这是绝佳受众。
3. **竞品是否正在赚钱？**
   - 没竞品的赛道大多是伪需求。有 3-5 个活得很润的小竞品，说明市场已被教育，需求真实存在，你只需在定位上做微调。

---

## 3. 市场调研落地执行表 (Execution Plan)

- [ ] **第 1 步：建立 Brainstorming 库**：在 `initial-brainstorming.md` 写入 3 个以上原始点子。
- [ ] **第 2 步：模板克隆与打分**：从 `niche-research-template.md` 克隆并填写调研报告，筛选出得分最高的 1 个 Niche。
- [ ] **第 3 步：寻找 10 个种子用户（不吹嘘，只倾听）**：
  - 在 Reddit 或 X 发私信或发帖：“我注意到很多人在 Java 开发中遇到 [痛点]，我也深受其害。我想做一个极简的解决方案。我想和遇到同样问题的朋友聊聊（5分钟），作为感谢，我愿意免费为您提供 [其他后端帮助] 或解答。”
- [ ] **第 4 步：定案 (Go/No-Go)**：
  - 如果打分通过，且至少有 3 个潜在客户确认了该痛点，**立刻切换到 Phase 1 (Foundation)**：起草 Offer 文案，进入 `docs/02-product-mvp/`。
