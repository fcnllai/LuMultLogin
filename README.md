## 🚀 Lunes Host 多账号自动登录续期（GitHub Actions）

这是一个基于 GitHub Actions 的多账号自动化脚本，用于定时登录自动续期[Lunes Host](https://betadash.lunes.host/) 应用。

模拟人工登录模式，在原脚本基础上优化了第2账号登录方式，防止黑号。
NODE_LINK代理链接支持多行，空行直连，第1行账号1，第2行账号2，仅1行两账号共用，超过2行的直接忽略。

⚠️ 有cf盾,太垃圾的机房节点可能过不了，建议用稍微干净点的节点 

━━━━━━━━━━━━━━━━━━━━━━

🔐 Secrets 配置说明(在原作基础上增加第2账号的保活支持，优化了签到方式防黑号)

| Secret 名称         | 是否必填 | 说明                                              |
|---------------------|----------|---------------------------------------------------|
| LUNES_EMAIL     | ✅ 必填  | lunes 登录邮箱1🇺🇸                                 |
| LUNES_PASSWORD  | ✅ 必填  | lunes 登录密码1                                   | 
| LUNES_EMAIL1     | ❌ 可选  | lunes 登录邮箱2🇩🇪                                |
| LUNES_PASSWORD1  | ❌ 可选   | lunes 登录密码2                                  | 
| NODE_LINK       | ❌ 可选  | 代理链接，如 vless:// vmess:// tuic:// hysteria2:// anttls:// socks5://|
| TG_BOT_TOKEN    | ❌ 可选  | Telegram Bot Token（用于发送通知）                     |
| TG_CHAT_ID      | ❌ 可选  | Telegram Chat ID（接收通知的用户或群组 ID）              |

━━━━━━━━━━━━━━━━━━━━━━
### 代理格式（确认在v2rayN里使用正常的节点）

`NODE_LINK` 支持以下任意一种代理协议的完整分享链接（不配置则直连）：

- **VLESS**：`vless://uuid@server:port?security=reality&sni=...&type=ws&...`
- **VMess**：`vmess://base64encoded...`
- **Trojan**：`trojan://password@server:port?sni=...&type=ws&...`
- **tuic**：`tuic://uuid:password@server:port...`
- **anytls**：`anytls://uuid@server:port...`
- **hysteria2**：`hysteria2://base64@server:port...`
- **SOCKS5**：`socks5://user:pass@server:port` 或 `socks://user:pass@server:port`

### 注意事项
- 尽量添加一个干净的节点，以免过不了cf盾
