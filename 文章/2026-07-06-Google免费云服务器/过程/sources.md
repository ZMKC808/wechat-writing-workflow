---
title: Google Cloud 免费服务器来源清单
date: 2026-07-06
tags:
  - 来源
  - GoogleCloud
---

# 官方来源

- [Google Cloud Free cloud features](https://docs.cloud.google.com/free/docs/free-cloud-features)
  - 用途：确认 Free Trial、Always Free、Compute Engine 免费配额、区域、磁盘、出站流量、GPU/TPU限制。
- [Google Cloud VPC Network pricing](https://cloud.google.com/vpc/network-pricing)
  - 用途：确认 Standard Tier 200GiB/月免费项、Premium 默认、Standard 需显式选择。
- [Network Service Tiers overview](https://docs.cloud.google.com/network-tiers/docs/overview)
  - 用途：确认 Standard Tier 免费项解释。
- [Compute Engine](https://cloud.google.com/products/compute)
  - 用途：确认 Compute Engine 免费层概览。
- [Disk and image pricing](https://cloud.google.com/compute/disks-image-pricing)
  - 用途：确认快照/磁盘可能收费。

# 外部参考

- [Creating a free Google Cloud Compute Engine VM in Google Cloud](https://dt.in.th/GoogleCloudFreeTier)
  - 用途：对照 gcloud 命令与操作细节。
- [Dev.to: GCP Free Tier Guide](https://dev.to/jeaniscoding/how-to-host-your-side-projects-for-0-the-ultimate-gcp-free-tier-guide-3p07)
  - 用途：对照常见扣费坑：Balanced disk、backups、Ops Agent。
- [Reddit: E2 Micro not free as Google free tier claims](https://www.reddit.com/r/googlecloud/comments/p91j7l/e2_micro_not_free_as_google_free_tier_claims/)
  - 用途：社区踩坑，重点是磁盘类型。
- [quzei CDN block script](https://quzei.com/sh/cdn_block.sh)
  - 用途：用户补充的初始化脚本。已检查脚本内容：下载 `cdn_ips.txt`，创建 `ipset`，通过 `iptables` 拦截 Cloudflare / Fastly / Akamai 等 CDN IP 段。文章中作为进阶可选项，不作为新手必做步骤。

# 用户提供来源

- 小红书文字参考：创建 Google Cloud Compute Engine 免费 VM 的 6 个关键设置。
- 微信公众号参考链接：`https://mp.weixin.qq.com/s/CHeyCKgmBO_JYmItJuFiKQ`
  - 当前状态：`wechat-article-to-markdown` 已安装，但本次抓取失败，错误来自 Camoufox `Browser.setDefaultViewport` 参数兼容问题。后续可用浏览器人工打开或修复工具后重新归档。
