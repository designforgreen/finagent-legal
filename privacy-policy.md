# FinAgent 扩展 · 隐私政策

**生效日期:** 2026-04-20
**最近更新:** 2026-04-20

---

## 一句话概括

FinAgent 扩展仅读取你在**微信读书、雪球、微博**这三个网站上**你自己的登录 session cookies**,加密发送给你指定的 FinAgent 服务,用于代你抓取你本人关注的内容。不读取任何其他数据,不发送给任何第三方。

## 1. 我们读取什么

扩展只读取以下三个域名下的登录 session cookies:

| 域名 | 用途 | 具体 cookie 名 |
|---|---|---|
| `weread.qq.com`(微信读书) | 读取微信公众号订阅 | `wr_vid`, `wr_skey`, `wr_rt` |
| `xueqiu.com`(雪球) | 读取雪球账号订阅 | `xq_a_token`, `xqat`, `u` |
| `weibo.com`(微博) | 读取微博账号订阅 | `SUB`, `SUBP`, `ALF` |

**我们不读取**:
- 浏览历史
- 书签
- 其他网站的 cookie
- 表单输入
- 保存的密码
- 扩展、设备或硬件信息

## 2. 为什么读取

帮你把**自己的**登录身份同步给 FinAgent Lite 后端,让后端以你本人身份代你抓取你关注的公众号 / 雪球号 / 微博号内容。这种"BYOK"(Bring Your Own Key)模式避免了系统账号抓取造成的封禁风险,也让数据处理更符合平台服务条款。

## 3. 数据如何传输

- 仅发送到你在扩展设置里指定的 FinAgent 服务(默认 `https://finagent.together-laos.shop`)
- 通过 HTTPS 加密传输
- **不发送给**任何第三方、广告网络、分析服务

## 4. 数据如何存储

**扩展本地**:
- 只在 `chrome.storage.local` 里保存一个短期 refresh_token(7 天过期)
- 不在扩展里缓存 cookies 原始值

**FinAgent 后端**:
- Cookies 用 AES-256-GCM 加密后存 MySQL 数据库
- 加密密钥(`CREDENTIALS_ENCRYPTION_KEY`)存在独立环境变量,不随数据库备份
- 每个用户的凭证严格按 `user_id` 隔离,绝不跨用户混用

## 5. 你的权利

随时你都可以:

- **解绑某个平台**:在扩展 popup 或 FinAgent 网页端点"解绑",后端立即物理删除该凭证
- **撤销整个扩展授权**:在 `chrome://extensions/` 里移除扩展,本地数据清空;也可以在 FinAgent 网页里"撤销扩展绑定"同时清后端 refresh_token
- **数据导出**:邮件联系下方地址请求导出你的全部数据
- **完全删除账号**:邮件联系下方地址,48 小时内物理删除

## 6. 我们不做的事

- ❌ 不卖你的数据
- ❌ 不把数据用于广告或跨网追踪
- ❌ 不读取除上述三个域外任何网站的 cookie
- ❌ 不在日志、错误报告(如 Sentry)里记录 cookie 原始值
- ❌ 不让你的数据用于训练 AI 模型(FinAgent 对抓取内容的 AI 处理仅限生成你自己能看到的摘要)

## 7. 未成年人

FinAgent 服务不面向 13 岁以下未成年人。如果我们意外收集到未成年人数据,会在核实后立即删除。

## 8. 变更

本隐私政策可能更新,重大变更会在扩展弹窗内通知你。政策 URL 和更新历史可以在:

<https://github.com/designforgreen/finagent-lite/blob/master/docs/legal/privacy-policy.md>

查看完整提交历史。

## 9. 联系方式

- GitHub Issues: <https://github.com/designforgreen/finagent-lite/issues>
- Email: jameswangchen1127@gmail.com

有任何隐私相关问题或请求,48 小时内回复。

---

_本政策遵循 Chrome Web Store 开发者计划政策、GDPR 原则、以及中国《个人信息保护法》的合理约定。_
