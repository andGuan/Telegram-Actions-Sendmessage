目标: 通过 GitHub Actions 定时或触发向 Telegram 特定用户发送 “你好”
使用技术: Github Actions, Telegram Bot API, 
前提条件: 
    1.通过 BotFather 创建，获取 API Token
    2.目标用户的 chat_id
    3.避免泄露 Token 和 chat_id，需将它们存储在 GitHub 仓库的 Secrets 中
    4.
Workflows: .github/workflows/tele.yml
    1.触发条件：schedule：通过 cron 表达式定时触发（格式：分 时 日 月 周，UTC 时间）。
    2.通过 curl 发送 POST 请求到 Telegram Bot API 的 sendMessage 接口，参数包括：
    chat_id：目标用户的 ID（从 Secrets 读取）。
    text：消息内容（这里是 “你好”）。

