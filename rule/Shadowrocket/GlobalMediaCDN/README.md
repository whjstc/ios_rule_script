# GlobalMedia CDN Acceleration

![GitHub last commit](https://img.shields.io/github/last-commit/whjstc/ios_rule_script?path=rule%2FShadowrocket%2FGlobalMediaCDN%2FGlobalMediaCDN.list&label=updated)

## 简介

**GlobalMedia CDN Acceleration** 是一个专为追求极致流媒体体验的高阶用户设计的 Shadowrocket 分流规则集。

**核心理念：控制流与数据流分离**

*   **控制流 (API/主站)**：负责身份验证、地区判定（如 YouTube Premium 美区权益、推荐算法）。
*   **数据流 (CDN)**：负责视频缓冲、图片加载，流量巨大。

本规则集**仅包含**主流海外媒体（YouTube, Twitter, Netflix, Facebook 等）的 **CDN 静态资源域名**。

## 适用场景

*   **美国身份 + 香港速度**：希望 YouTube 保持美区内容（首页推荐、排行榜），但视频流量走香港/新加坡等低延迟、大带宽节点以实现 4K/8K 秒开。
*   **节省优质流量**：如果你有昂贵的原生 IP 节点（流量少），可以将本规则指向廉价的的大流量节点。

## 包含内容

目前涵盖以下平台的 CDN 域名：
- YouTube (`googlevideo.com`, `gvt1.com` 等)
- Twitter/X (`twimg.com`, `video.twimg.com`)
- Facebook & Instagram (`fbcdn.net` 等)
- Twitch (`ttvnw.net`)
- Reddit, Pinterest, Snapchat 等静态资源

> **注意**：已移除 TikTok 和 AmazonAWS 相关域名以防止风控和误伤。

## 使用配置指南 (Shadowrocket)

为了使本规则生效，请务必在 Shadowrocket 中按照以下顺序配置分流：

1.  **策略组准备**：
    *   创建策略组 `🇺🇸 US-Identity` (选择美国/原生节点)
    *   创建策略组 `🇭🇰 HK-Speed` (选择香港/高速节点)

2.  **分流规则顺序 (从上到下)**：

    *   **第一条 (主站保身份)**：
        *   匹配：`DOMAIN-SUFFIX` -> `youtube.com` / `twitter.com` 等主站域名
        *   策略：指向 👉 `🇺🇸 US-Identity`
    
    *   **第二条 (CDN 提速 - 本规则)**：
        *   类型：`RULE-SET`
        *   链接：使用下方的 RAW 链接
        *   策略：指向 👉 `🇭🇰 HK-Speed`
    
    *   **第三条 (兜底)**：
        *   匹配：`FINAL`
        *   策略：指向 `🇺🇸 US-Identity`

## 订阅链接

**Shadowrocket / Clash / Quantumult X:**

```url
https://raw.githubusercontent.com/whjstc/ios_rule_script/master/rule/Shadowrocket/GlobalMediaCDN/GlobalMediaCDN.list
