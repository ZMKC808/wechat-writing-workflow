---
title: Google这台免费云服务器，被我薅明白了
date: 2026-07-06
status: drafting
tags:
  - 公众号/文章生产
  - 云服务器
  - GoogleCloud
  - 白嫖指南
style_ref:
  - "[[AWS云服务器白嫖指南_200美金免费薅]]"
  - "[[_0搭服务器_甲骨文4核24G白嫖指南]]"
---

# 选题

写一篇 Google Cloud Always Free e2-micro 云服务器领取指南，延续之前 AWS / 甲骨文服务器白嫖指南的写法：直接、图文步骤、重点提示扣费坑，但不要一开头贬低配置。

# 核心卖点

- Google Cloud 有长期免费的 Compute Engine 配额。
- 配置不高：`e2-micro`，2 vCPU 共享核心，1GB 内存。
- 适合轻量任务：个人小站、脚本、监控、Bot、Linux 练习、轻量 Docker。
- 最大价值不是配置，而是稳定、控制台成熟、教程多、比甲骨文更不折腾。

# 必须讲清楚的边界

- 免费区域只有 `us-west1`、`us-central1`、`us-east1`。
- 免费机器类型只有 `e2-micro`，且是每月一台实例等量小时。
- 磁盘用 `Standard persistent disk`，保守写 10GB；官方上限是 30GB-month。
- 备份、快照、额外磁盘、GPU/TPU、负载均衡、Cloud NAT、静态保留 IP 等都可能收费。
- 网络：Compute Engine Always Free 官方出站流量是 1GB/月；Network Service Tier 选 Standard 后，VPC Standard Tier 有 200GiB/月免费项。文章里不能把它写成“Google Cloud 所有流量 200G 免费”。

# 图片现状

已有 4 张图，够写主体步骤：

- `images/01-region-us-central1.jpg`
- `images/02-e2-micro.jpg`
- `images/03-standard-persistent-disk.jpg`
- `images/04-standard-network-tier.jpg`

建议补图：

- Data Protection 里选择 `No backups`。
- 最终右侧 Monthly estimate / Billing 第二天核对页。
- 实例创建成功后的 VM 列表页。
