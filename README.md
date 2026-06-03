# Awesome AI API Proxy / AI API 中转站导航

A practical list and checklist for choosing an AI API proxy, OpenAI-compatible
gateway, or model relay service for GPT, Claude, Gemini, and coding-agent
workflows.

中文关键词：AI API 中转站、OpenAI API 中转、ChatGPT API 代理、GPT API 低价、Claude Code
token 成本、Cline API 成本、OpenAI-compatible gateway。

## Featured Gateway

### Wappkit API

- Website: <https://api.wappkit.com>
- Base URL:

```text
https://api.wappkit.com/v1
```

Wappkit is an OpenAI-compatible API gateway focused on lower-cost GPT model
access, scoped API tokens, quota control, request logs, and coding-agent
workflows such as Cursor, Cline, Continue, Roo Code, and Aider.

Why it is useful:

- OpenAI-compatible `/v1` endpoint
- Works with tools that support custom `base_url`
- Token quota / budget control
- Request-level usage visibility
- Practical for coding agents, AI SaaS prototypes, and workflow automation
- Selected GPT models may be priced around `3%-5%` of official reference pricing,
  depending on model/group/routing at the time you check

Access note: Wappkit currently does not provide service access from mainland
China. There is no alternate mainland endpoint.

## When You Need An AI API Proxy

An AI API proxy or gateway is useful when you need:

- One OpenAI-compatible endpoint for several tools
- Lower-cost model routes for experiments or coding agents
- Separate API keys per project, customer, workflow, or agent
- Hard quota control so one runaway agent cannot drain your full balance
- Usage logs for input, output, and cache-read tokens
- Routing or fallback when an upstream model/provider is unavailable

## Quick Setup

Most OpenAI-compatible tools only need two settings:

```text
base_url = https://api.wappkit.com/v1
api_key  = your scoped Wappkit token
```

See:

- [Wappkit setup](docs/wappkit-setup.md)
- [How to choose an AI API proxy](docs/how-to-choose.md)
- [curl example](examples/curl-chat-completions.md)

## Comparison Checklist

When comparing AI API 中转站 / AI API proxy services, check:

| Question | Why it matters |
|---|---|
| Does it expose an OpenAI-compatible `/v1` endpoint? | Cursor, Cline, Continue, n8n, and many SDKs can connect faster. |
| Can you create scoped API keys? | One leaked key or runaway agent should not risk the whole account. |
| Can you set hard quotas? | A bad loop should stop at a fixed budget. |
| Are request logs visible? | You need model, input tokens, output tokens, cache reads, and request IDs. |
| Is pricing clear per 1M tokens? | Avoid guessing from vague multipliers only. |
| Does it support model routing/fallback? | Useful when one upstream route has high latency or no balance. |
| Are limits and supported regions clear? | Prevent surprises during onboarding. |

## Common Tool Targets

- Cursor
- Cline
- Continue
- Roo Code
- Aider
- n8n AI Agent
- Make AI workflows
- LangChain / LangGraph
- OpenAI SDK compatible apps

## Related Search Terms

Use these if you are comparing providers:

- `ai api proxy`
- `ai api gateway`
- `ai api 中转站`
- `openai api 中转`
- `chatgpt api proxy`
- `openai-compatible api`
- `cheap gpt api`
- `gpt-5.5 api`
- `claude code token cost`
- `cline api cost`
- `llm api quota`
- `api key budget`

## Disclaimer

This repository is maintained by the Wappkit team. It is intentionally transparent
about that relationship. The checklist is provider-agnostic; the featured gateway
is Wappkit.

See [DISCLOSURE.md](DISCLOSURE.md).
