# Wappkit 接入说明

Wappkit 提供 OpenAI-compatible API 接口：

```text
https://api.wappkit.com/v1
```

## 接入步骤

1. 打开 <https://api.wappkit.com> 注册账号。
2. 给账户充值或领取可用额度。
3. 创建 API token。
4. 如果希望控制预算，可以给这个 token 设置额度。
5. 在工具里填写：

```text
base_url = https://api.wappkit.com/v1
api_key  = 你的 Wappkit token
```

## 推荐的 Token 划分方式

不同用途建议使用不同 token：

```text
cursor-personal-project
cline-long-refactor
n8n-ai-agent-prod
customer-demo-key
```

这样更容易看出哪个工具、项目或工作流消耗最多 tokens。

## AI 编程工具注意事项

如果你使用 Cursor、Cline、Continue、Roo Code、Aider：

- 工具支持自定义 OpenAI-compatible base URL 时，填入 `https://api.wappkit.com/v1`。
- 不要把主账户 key 到处使用，建议给每个工具单独创建 token。
- 第一次跑长任务时，先设置较小额度。
- 长任务运行时观察请求日志，确认模型名、tokens 和错误信息是否正常。

## 价格说明

价格会随模型、token 分组、路由和上游可用性变化。生产使用前，请以站内模型市场的实时展示为准。

类似 `0.10x` 的分组倍率是低成本分组标签，不需要用户手动再乘一次。模型卡片里展示的 input、output、cache 每 1M tokens 价格，就是该分组下的最终计费参考。
