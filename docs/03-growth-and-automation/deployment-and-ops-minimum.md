# Deployment & Ops Minimum — 最小部署与运维

**Audience:** CTO + COO  
**Goal:** Phase 1 用 **单 VM + 静态/轻后端** 跑通 Landing、Webhook、MVP；无 K8s  
**Last updated:** 2026-08-28

> 首笔付费之前，运维的目标是「别挂」，不是「能扩容」。  
> Before first revenue, ops means *stay up* — not *scale out*.

---

## 1. 推荐拓扑（Phase 1）

```text
[User] → [Cloudflare DNS] → [Hetzner CX22 ~€4/mo]
                              ├─ Caddy/Nginx (HTTPS)
                              ├─ Landing (静态 or Astro)
                              └─ Spring Boot / Node API (可选)
[Stripe] ──webhook──► https://api.yourdomain.com/webhooks/stripe
```

**替代：** Landing 放 Vercel/Cloudflare Pages（免费），仅 API 在 Hetzner。

---

## 2. 上线 Checklist

### 2.1 域名与 HTTPS

- [ ] 域名购买（Namecheap / Cloudflare Registrar）  
- [ ] DNS A 记录 → VM IP  
- [ ] Caddy 自动 Let's Encrypt **或** Cloudflare proxy SSL  

### 2.2 服务器（Hetzner 示例）

- [ ] Ubuntu LTS，SSH key only，禁用 password login  
- [ ] 非 root 部署用户 + firewall（22, 80, 443）  
- [ ] 自动安全更新（unattended-upgrades）  

### 2.3 应用

- [ ] Landing 部署（`rsync` / `git pull` 即可，无 CI 要求）  
- [ ] 健康检查 endpoint：`GET /health` → 200  
- [ ] 环境变量 via `.env`（**不入 git**）  

### 2.4 Stripe Webhook（最小）

- [ ] Dashboard 创建 webhook URL  
- [ ] 监听至少：`checkout.session.completed`  
- [ ] Webhook signing secret 配在 server  
- [ ] 验签失败 → 4xx，记录 log  
- [ ] 成功 → 写 Notion/Airtable/邮件「待发货」队列（手动 OK）  

**Week-1 可替代：** 无 webhook，每日人工看 Stripe Dashboard → 仍须在 M1 前自动化。

---

## 3. 监控与报警（solo 极简）

| 层级 | 工具 | 成本 |
|------|------|------|
| Uptime | [UptimeRobot](https://uptimerobot.com/) 或 Hetrix | 免费档 |
| Logs | `journalctl` + 偶尔 grep | $0 |
| Errors | 邮件/Telegram when `/health` fails | $0 |
| APM | **Phase 1 不做** | — |

**报警渠道：** Telegram Bot 或 Email — 与 Idea 3 监控产品无关，先用免费外部 ping。

---

## 4. 备份与恢复

| 数据 | 策略 |
|------|------|
| 代码 | GitHub（本 repo + 产品 repo） |
| 用户/订单 | Stripe 为 source of truth；本地 CSV 每周导出 |
| DB（若有） | SQLite 文件日备到对象存储 **或** 托管 Postgres 自动备份 |
| 服务器 | Infrastructure as 笔记：重建步骤写在本文件 §2 |

**RTO 目标：** Phase 1 允许 **4h 内** 手工重建 VM。

---

## 5. 发布流程（故意简陋）

```text
本地测试 → git tag v0.x → ssh deploy@vm "cd app && git pull && systemctl restart app"
```

- [ ] 回滚 = `git checkout` 上一 tag + restart  
- [ ] 首 10 个客户前：**不做** 蓝绿 / K8s  

---

## 6. 成本快照（记入 Runway）

| 项 | 约 $/mo |
|----|---------|
| Hetzner CX22 | ~5 |
| 域名 | ~1（摊销） |
| UptimeRobot | 0 |
| **合计 infra** | **~6** |

见 [`../00-constraints/runway-and-living-wage.md`](../00-constraints/runway-and-living-wage.md)。

---

## 7. Stage E 才做的扩展

- CI/CD（GitHub Actions）  
- 多环境 staging  
- 集中日志（Loki / Datadog）  
- 自动扩容  

**Gate：** M2（$100 MRR 或 $500 累计）再逐项加。

---

## 关联文档

| 文档 | 关系 |
|------|------|
| [`../../roles/CTO-chief-technology-officer.md`](../../roles/CTO-chief-technology-officer.md) | 部署铁律 |
| [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md) | Stripe 最小栈 |
| [`ai-operating-stack.md`](ai-operating-stack.md) | 工具成本 |

---

*Manual deploy is a feature until customers pay.*
