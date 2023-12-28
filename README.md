## 聊天记录总结

> 本项目作为[`wechat-gptbot`](https://github.com/iuiaoin/wechat-gptbot)插件，可以总结一段时间内的聊天记录。

### 安装

添加以下配置到插件源配置文件`plugins/source.json`:
```yaml
  "wechat_summary": {
    "repo": "https://github.com/al-one/wechat-gptbot-summary.git",
    "desc": "总结微信聊天记录"
  }
```

### 配置

添加以下配置到配置文件`config.json`:
```yaml
  "plugins": [{ "name": "wechat_summary", "command": ["总结聊天记录"] }]
```

完整配置示例:
```yaml
  "plugins": [
    {
      "name": "wechat_summary",
      "command": ["总结聊天记录", "聊天记录总结", "总结一下"],
      "prompt": "这是一份聊天记录，请总结成一份不超过500字的中文概述。...", # 可选
      "minlen": 5, # 最小聊天记录条数 int或dict，默认为3
      "maxlen": {  # 最大聊天记录条数 int或dict，默认为500
        "wx_userid": 100,     # 私聊
        "xxxx@chatroom": 200, # 群聊
        "*": 300
      }
    }
  ]
```
