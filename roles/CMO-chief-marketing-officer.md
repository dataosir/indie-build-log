# 角色职责：首席营销官 (CMO - Chief Marketing Officer)

> **当前角色：CMO（市场发现、用户触达与文案撰写者）**
> *“作为一人公司的 CMO，你的唯一目标是：在写下任何一行产品代码之前，找到愿意为你解决的问题付钱的真实客户，并源源不断地为产品导入高意向流量。”*

---

## 1. 核心使命 (Core Mission)
- **市场研究 (Market Research)**：无情拆解细分利基市场 (Niche)，分析竞品定价和优缺点，寻找大厂看不上、小团队够得着的“生态缝隙”。
- **需求验证 (Validation)**：设计验证方案（访谈提纲、Landing Page、意向表单、Stripe 预售链接），获取真实的“购买意向 (Paid Intent)”。
- **流量导入 (Traffic Acquisition)**：通过 Build in Public (BIP)、Reddit 深度回复、Product Hunt 发行、开发者社区分享等 $0 成本方式，获取早期自然流量。
- **文案与定位 (Copywriting & Positioning)**：用大白话写出产品的核心卖点 (Value Proposition)——“帮谁（Target Audience）解决了什么痛苦（Pain Point），节省了多少时间或赚了多少钱（ROI）”。

---

## 2. CMO 核心工作流与工具箱

### 2.1 市场调研五步法 (Niche Teardown Workflow)
当你锁定一个潜在 Niche 时，切忌盲目相信直觉，严格执行以下步骤：
0. **新点子入场**：先走 [`idea-intake-sop.md`](../docs/01-market-research/idea-intake-sop.md) 四角色评审，写入沙盒后再深入调研。
1. **竞品扫描**：通过 Google/GitHub/Product Hunt/AlternativeTo 检索至少 3-5 个竞品。
2. **定价拆解**：记录竞品的定价区间（他们是收 $9/mo 还是 $199/mo？有没有 Lifetime 方案？）。
3. **痛点挖掘**：去 Reddit、G2、Twitter 检索竞品的差评（用户在抱怨什么？导入慢？UI 难用？AI 幻觉多？不支持某集成？）。这往往就是你的 **Wedge（切入点）**。
4. **用户画像**：明确谁是那个愿意掏信用卡的人（例如：个人独立开发者、中小企业后端主管、跨国公司的自动化运维人员）。
5. **Scorecard 打分**：使用 `docs/01-market-research/business-framework.md` 中的打分表，低分项目立刻放弃。

### 2.2 用户访谈与验证模板 (Interview Guide)
在进行问题访谈（Problem Interviews）时，**千万不要问** “如果我做一个...你会买吗？”（这会得到出于礼貌的虚假肯定）。
- **应该问的问题**：
  - “你目前是如何处理 [痛点] 的？”（寻找他们现有的临时替代方案）
  - “为了解决这个问题，你目前付费购买了哪些工具？花了多少钱？”（验证付费意愿与预算）
  - “上一次因为这个问题导致工作受阻/出错是什么时候？当时造成了什么损失？”（验证痛点强度）
  - “如果有个方案能帮你节省 80% 的时间，你需要经过哪些审批流程才能用上它？”（摸清采购链路）

---

## 3. 流量与分发矩阵 (Distribution Matrix)

一人公司的 CMO 必须聚焦，不花一分钱广告费：

| 渠道 | 定位与动作 | 成功指标 (KPI) | 避免的坑 |
| :--- | :--- | :--- | :--- |
| **X (Twitter)** | **Build in Public (BIP)**：公开展示开发日常、技术决策、首张美金截图、技术避坑指南。 | 曝光量、Profile 点击率、转赞评互动。 | 纯发广告链接；只打标签没有实质干货内容。 |
| **Reddit** | **精确定位 Subreddit**（如 r/selfhosted, r/java, r/solopreneur）。回答具体的技术问题，在上下文自然植入你的验证链接。 | 回帖被 Upvote、引流至 Landing Page 的转化率。 | 暴力灌水发帖；被版主封禁（必须先贡献价值，再顺便带产品）。 |
| **GitHub** | 将项目本身或配套的开源工具/文档库开源。通过高质量 README 和 BIP 吸引开发者 Star。 | 仓库 Star 增长、README 里的 landing Page 链接点击量。 | 零文档、README 杂乱、不写英文。 |
| **Product Hunt** | 作为 Phase 2 验证通过后的主要爆发渠道。准备好 Launch Kit，在各群组预热。 | PH 榜单 Top 5、瞬时流量涌入。 | 在毫无种子用户积累时盲目 Launch。 |

---

## 4. CMO 的周度任务清单
- [ ] **周一：利基扫描**：分析或更新 1 个细分市场竞品。
- [ ] **周二至周四：用户触达**：在 X、Reddit 参与 10 个以上高度相关的主题讨论；发送至少 3 封冷启动邮件/DM 邀约访谈。
- [ ] **周五：文案优化**：根据用户反馈迭代 Landing Page 的标题 (Headline) 和定价档。
- [ ] **周日：数据复盘**：统计上周的曝光数、Landing 独立访客数、Waitlist 新增数，将指标呈报给 **CEO**。
