# ChatGPT Access Token 怎么获取？Session JSON 复制教程（2026）

**直接答案：**在浏览器里登录要充值的 ChatGPT 账号，在同一个浏览器的地址栏输入 `chatgpt.com/api/auth/session`，按 Ctrl/Cmd + A 全选、Ctrl/Cmd + C 复制整页内容。复制到的就是包含 accessToken 的 Session JSON，整段粘贴到卡密激活页即可，不用单独挑出 accessToken。

> 页面空白或只有 `{}` → 没登录，重新登录后再开。识别不到邮箱 → 关闭网页翻译、JSON 美化插件后重新复制。

[← 返回目录](../README.md)

## 四个容易混淆的东西

| 名称 | 长什么样 | 充值要不要 |
| --- | --- | --- |
| Session JSON | 以 `{` 开头、`}` 结尾的一整段文本，含 user、expires、accessToken | **要**，整段复制 |
| accessToken | Session JSON 里以 `eyJ` 开头的超长字段 | 不用单独挑，激活页自动提取 |
| ChatGPT 密码 / 验证码 | 你的登录密码、邮箱或短信验证码 | **不要**，正规充值不会索取 |
| API Key（`sk-` 开头） | platform.openai.com 生成的开发者密钥 | **不要**，与订阅无关 |

accessToken 会过期，退出登录也会让它失效。建议准备提交充值时再复制。

## 电脑端步骤

1. 打开 chatgpt.com，只登录本次要充值的账号。登过多个账号的，先全部退出，或用无痕窗口只登目标账号。
2. 关闭网页翻译、沉浸式翻译、JSON 格式化类插件。
3. 在同一窗口地址栏输入 `chatgpt.com/api/auth/session` 并回车。
4. 点击页面正文，Ctrl/Cmd + A 全选，Ctrl/Cmd + C 复制。不要用鼠标拖选。
5. 粘贴到卡密激活页，确认识别出的邮箱是目标账号后再提交。

## 手机端步骤

ChatGPT App 拿不到 Session JSON，必须用手机浏览器。

1. 用 Safari 或 Chrome 打开 chatgpt.com 并登录。被跳转到 App 时，长按链接选「在浏览器中打开」。
2. 在同一个标签页地址栏输入 `chatgpt.com/api/auth/session`。
3. 长按文字 → 全选 → 拷贝。
4. 先粘到备忘录检查首尾是否完整，再粘贴到激活页。

## 怎么判断复制完整

- 开头是英文 `{`，紧接英文 WARNING 提示。开头变成中文 = 被翻译过，需恢复原文重新复制。
- 结尾是 `}`，常常连续几个。只有一串 `eyJ...` 没有花括号 = 只复制了一个字段。
- 不要手动补括号或拼接，缺了就回原页面重新全选。

## 报错排查

| 现象 | 原因 | 处理 |
| --- | --- | --- |
| 页面空白或只有 `{}` | 未登录或登录过期 | 重新登录 chatgpt.com 后刷新 |
| 人机验证或 403 | 网络环境被风控 | 完成验证或换稳定节点 |
| 格式错误 / JSON 不完整 | 只复制了一部分 | 回原页面重新全选 |
| 识别不到邮箱 | 翻译或美化插件改了内容 | 关闭插件后重新复制原文 |
| 邮箱不是目标账号 | 浏览器登着另一个账号 | 退出所有账号，无痕窗口只登目标账号 |
| Token 无效 / Session 失效 | 复制后退出过登录或放置太久 | 重新获取一份立刻提交 |

## 安全边界

- Access Token 不是密码，不能改密码或邮箱，但有效期内可以以你的身份访问 ChatGPT。
- 只粘贴到自己订单对应的激活页，不要发到群聊、论坛或陌生人私信。
- 充值完成后可在「设置 → 安全」退出所有设备，旧 Token 随之失效，订阅不受影响。

## FAQ

**ChatGPT Access Token 在哪里看？**
登录后在同一浏览器打开 `chatgpt.com/api/auth/session`，JSON 里的 accessToken 字段就是。充值时复制整页即可。

**App 里能获取吗？**
不能，需要用浏览器登录 chatgpt.com 后打开 session 页面。

**Access Token 会过期吗？**
会，放置一段时间或退出登录后失效，提交前再复制。

**Access Token 和 API Key 是一回事吗？**
不是。API Key 用于程序调用、按用量计费；充值 Plus / Pro 只用 Session JSON。

---

完整图文版：[czgptai.com 博客 · ChatGPT Access Token 获取教程](https://www.czgptai.com/blog/chatgpt-access-token-huoqu-session-json-2026) ｜ 充值入口：[czgptai.com](https://www.czgptai.com/)
