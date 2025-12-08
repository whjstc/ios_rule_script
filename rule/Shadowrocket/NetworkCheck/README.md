# Network Check & Diagnostics

![GitHub last commit](https://img.shields.io/github/last-commit/whjstc/ios_rule_script?path=rule%2FShadowrocket%2FNetworkCheck%2FNetworkCheck.list&label=updated)

## 简介

**NetworkCheck** 是一个汇集了网络诊断工具域名的分流规则集。

它包含了互联网上最常用的：
*   **IP 查询网站** (如 ip.sb)
*   **网速测试服务** (如 Speedtest, Fast.com)
*   **隐私泄漏检测** (如 WebRTC Leak, DNS Leak)
*   **指纹浏览器检测** (如 BrowserScan)

## 适用场景

使用此规则集，你可以灵活地控制这些诊断工具的流量走向，从而实现：

1.  **检测节点 IP**：将此规则集指向「代理节点」，打开 `ip.sb` 即可查看该节点的出口 IP。
2.  **检测真实 IP**：将此规则集指向「直连/Direct」，即可查看运营商分配给你的真实 IP。
3.  **节点测速**：将规则指向特定节点，使用 Speedtest 测试该节点的真实带宽表现。
4.  **防止 DNS 泄露**：在访问 DNS 检测网站时，确保流量经过代理，验证 Shadowrocket 的 DNS 设置是否生效。

## 包含内容

*   **Connectivity**: Vultr, IPv6 测试
*   **SpeedTest**: Speedtest.net, Fast.com, Cloudflare Speed
*   **IP Check**: IP-API, Whoer, IPIP, IP.sb
*   **Security**: BrowserLeaks, DNSLeakTest, IP Score

## 使用配置指南 (Shadowrocket)

1.  **添加规则**：
    *   类型：`RULE-SET`
    *   策略：建议创建一个名为 `🔍 Network Test` 或 `📲 Final` 的策略组，或者直接指向你想要测试的节点（如 `Proxy`）。
    *   URL：使用下方的订阅链接。

2.  **策略建议**：
    *   如果你想看**代理后**的伪装效果，请选择 `Proxy`。
    *   如果你想看**本地网络**的真实信息，请选择 `Direct`。

## 订阅链接

**GitHub Raw (推荐):**

```url
https://raw.githubusercontent.com/whjstc/ios_rule_script/master/rule/Shadowrocket/NetworkCheck/NetworkCheck.list
