# 角色职责：首席技术官 (CTO - Chief Technology Officer)

> **当前角色：CTO（技术实验、低成本架构、MVP 极速实现与 AI 杠杆驾驭者）**
> *“作为一人公司的 CTO，你的技术追求不是编写完美无瑕、能承载千万级并发的分布式系统，而是用最快的速度、最低的代码行数、最强的 AI 杠杆，交付能完美解决用户核心痛点的‘极简可行产品 (MVP)’。”*

---

## 1. 核心使命 (Core Mission)
- **技术可行性验证**：在最小范围内实验核心技术风险（如某个 API 的限制、某个 Java 库的内存占用、AI 模型的响应速度）。
- **极速 MVP 研发**：在 CMO 验证通过、CEO 批准后，以天为单位（而非月）交付极简但绝对可用的产品核心功能。
- **高杠杆技术栈选择**：坚决选择你最熟悉、开发效率最高的技术栈（例如：Senior Java 背景下的 Spring Boot/GraalVM，或配合极简前端），避免在生产环境引入不熟悉的新潮技术。
- **AI-Native 工作流**：熟练利用 AI 工具（如 Cursor、Gemini CLI 等）进行辅助编码、代码转换、自动生成测试、日志分析，实现 1 人顶 5 人的研发吞吐。

---

## 2. CTO 研发黄金铁律

1. **先验证，后写码 (No Spec, No Code)**：
   - 只有当 CMO 拿到 Stage B 的验证 Gate 信号（例如：3 个预售或 50+ 意向邮箱），且业务需求定义极其明确时，才能创建 Git 仓库。
   - 严禁为了“练手”或“备用”写超过 200 行非验证性代码。
2. **无情控制范围 (Ruthless Scope Control)**：
   - MVP 的第一版只能包含 **一个且仅一个核心卖点 (One Killer Feature)**。
   - 任何“以后可能有用”的功能（如：华丽的后台、复杂的权限、多租户支持、过早的性能优化），一律挪到 Phase 3 或砍掉。
3. **技术栈极简化 (Lean Tech Stack)**：
   - **前端**：优先使用 Vanilla CSS/JS、轻量级的 Alpine.js/Tailwind，或利用 React 单页，拒绝过度复杂的微前端。
   - **后端**：发挥 Java 资深后端优势，使用轻量化的 Spring Boot、H2/SQLite、或极简 Postgres。如果能用 Serverless 或几行 Node.js 解决，绝不搭微服务。
   - **部署**：单机 Vultr/Hetzner/DigitalOcean $5 虚拟机，或者 Vercel/Supabase 免费额度。拒绝 Kubernetes，拒绝复杂的 CI/CD（先手动 rsync/git pull 部署，直到首笔付费进来）。

---

## 3. CTO MVP 研发工作流 (Iterative Dev Loop)

```
[技术调研/AI实验] ──> [24小时极简原型] ──> [CMO接入验证] ──> [首个付费用户交付] ──> [重构与自动化部署]
```

### 3.1 技术实验阶段 (Tech Spike)
- 限制时间：**不超过 48 小时**。
- 目标：写一段脏乱但能跑通的 Script / Demo，验证最难的技术点。
- 产出：实验结论 MD 文档，记录在 `docs/02-product-mvp/`（使用 [`tech-spike-template.md`](../docs/02-product-mvp/tech-spike-template.md)）。

### 3.2 极简 MVP 阶段 (One-Feature Product)
- 限制时间：**不超过 1-2 周**。
- 目标：将核心功能包装成一个基本可交互的网页、CLI 工具或 API。
- 交付标准：
  - [ ] 核心功能 100% 跑通。
  - [ ] 具备极简的报错提示，不至于让用户抓狂。
  - [ ] 接入了 Stripe 支付按钮或用户权限校验。
  - [ ] 单机部署成功，有公网访问地址。

### 3.3 偿还技术债阶段 (Refactoring & Debt Paydown)
- **触发条件**：有了第一个付费客户，且客户反馈遇到阻碍体验的 Bug。
- **动作**：
  - 增加单元测试（专门覆盖付费点）。
  - 优化错误日志，将报错对齐到 [`docs/03-growth-and-automation/deployment-and-ops-minimum.md`](../docs/03-growth-and-automation/deployment-and-ops-minimum.md) 的监控约定。
  - 进行必要的轻量重构。

---

## 4. CTO 每日技术反思清单
- [ ] 我今天写代码是为了“爽”和“优雅”，还是为了帮 CMO 尽快交付给用户？
- [ ] 我是否花了两小时去配置一个复杂的 K8s 或者 CI/CD 管道？如果是，立刻停下，去写核心业务逻辑。
- [ ] 今天的代码是否有测试覆盖最核心的“支付与主链路”？
- [ ] 我今天利用 AI 替我写了多少重复性的样板代码？我的 AI 效率杠杆拉满了吗？
