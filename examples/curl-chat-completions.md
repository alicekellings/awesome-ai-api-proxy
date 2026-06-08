# curl Chat Completions 调用示例

把 `YOUR_WAPPKIT_TOKEN` 替换成你在 Wappkit 创建的独立 token。

```bash
curl https://api.wappkit.com/v1/chat/completions \
  -H "Authorization: Bearer YOUR_WAPPKIT_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-5.4",
    "messages": [
      {
        "role": "user",
        "content": "写一个控制 AI agent API 成本的简短清单。"
      }
    ]
  }'
```

查看响应里的 `usage` 对象，可以了解这次请求的 token 消耗：

```json
{
  "usage": {
    "prompt_tokens": 42,
    "completion_tokens": 120,
    "total_tokens": 162
  }
}
```

不同模型或路线可能会返回额外字段，例如 cache-read 或 reasoning 相关用量。实际计费和日志请以你选择的模型路线返回结果为准。
