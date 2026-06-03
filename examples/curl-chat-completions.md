# curl Chat Completions Example

Replace `YOUR_WAPPKIT_TOKEN` with a scoped token from Wappkit.

```bash
curl https://api.wappkit.com/v1/chat/completions \
  -H "Authorization: Bearer YOUR_WAPPKIT_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-5.4",
    "messages": [
      {
        "role": "user",
        "content": "Write a short checklist for controlling AI agent API cost."
      }
    ]
  }'
```

Check the response `usage` object to understand token consumption:

```json
{
  "usage": {
    "prompt_tokens": 42,
    "completion_tokens": 120,
    "total_tokens": 162
  }
}
```

Some models/providers may include additional token fields such as cache-read or
reasoning-related usage. Always inspect the actual response from your selected
route.
