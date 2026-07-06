---
title: Google Cloud 免费服务器调研简报
date: 2026-07-06
status: researched
tags:
  - 资料收集
  - GoogleCloud
  - ComputeEngine
---

# 官方信息

## Google Cloud Free Tier

Google Cloud 官方 Free Tier 文档给出的 Compute Engine Always Free 口径：

- 每月 1 台非抢占式 `e2-micro` VM，区域限定在 `us-west1`、`us-central1`、`us-east1`。
- 30 GB-month `Standard persistent disk`。
- 每月 1GB 从北美到多数目的地的出站流量，不含中国和澳大利亚。
- GPU 和 TPU 不包含在免费范围。
- Free Tier 没有固定结束日期，但 Google 可以调整政策。

新账号还有 Free Trial：

- $300 试用金。
- 90 天有效。
- 需要绑定账单账号和信用卡。
- 试用期内超出 Always Free 的部分会先消耗试用金，不是直接免费。

## Network Service Tier

Google Cloud VPC 网络价格页显示：

- Premium Tier 是默认网络层。
- Standard Tier 需要显式选择。
- Standard Tier 有每月 200 GiB 免费用量，按账号和区域/项目维度统计，超过后按量计费。
- 文档同时提醒 Always Free usage limits 不适用于 Standard Tier，因此文章中要把“Compute Engine Always Free 的 1GB”与“Standard Tier 的 200GiB 免费项”分开讲。

# 用户给的中文参考

小红书参考口径基本可用，但需要修正表达：

- 区域选择：`us-central1 (Iowa)`、`us-east1 (South Carolina)`、`us-west1 (Oregon)`。
- Series 选 E2，machine type 选 `e2-micro`。
- Boot disk type 选 `Standard persistent disk`，10G。
- Data Protection 选 `No backups`。
- Networking 里 Network Service Tier 选 `Standard`。
- “200G 流量以内不计费”应写成：Standard Tier 有 200GiB/月免费项，自用轻量服务通常够；但官方 Compute Engine Always Free 的基础出站配额仍是 1GB/月，具体账单以 Billing 为准。

# 社区踩坑

- 很多人扣费不是因为 e2-micro 本身，而是默认磁盘选成 Balanced / SSD。
- 快照、备份、Ops Agent、额外磁盘会产生独立 SKU。
- 选错区域后即使是 e2-micro 也不算 Always Free。
- Premium Tier 默认开启，若出站流量较大，账单可能很快出现。
- 免费配额按账号/月统计，不适合开多台机器轮流跑。

# 写作角度

这篇不是吹 Google Cloud 配置多强，而是写成：

> 甲骨文配置香但注册和抢机折腾；AWS顺滑但本质是试用金和限期权益；Google Cloud 这台最弱，但按对配置后适合长期放一个轻量服务。

重点放在“别点错”，而不是“白嫖无脑开”。

# 主要来源

- [Google Cloud Free cloud features](https://docs.cloud.google.com/free/docs/free-cloud-features)
- [Google Cloud VPC Network pricing](https://cloud.google.com/vpc/network-pricing)
- [Network Service Tiers overview](https://docs.cloud.google.com/network-tiers/docs/overview)
- [Compute Engine product pricing summary](https://cloud.google.com/products/compute)
- [Creating a free Google Cloud Compute Engine VM](https://dt.in.th/GoogleCloudFreeTier)
