# How To Choose An AI API Proxy

AI API proxy services can look similar from the outside. The real differences
show up when you connect coding agents, automation workflows, or a SaaS product.

## 1. Endpoint Compatibility

Look for an OpenAI-compatible endpoint:

```text
https://example.com/v1
```

This matters because many tools already support the OpenAI API shape. If a
provider is compatible, you can usually change only `base_url` and `api_key`.

## 2. Scoped Tokens

Avoid one unlimited key for every tool.

Prefer:

```text
one project  -> one token
one workflow -> one token
one customer -> one token
one agent run -> one token
```

This makes debugging, abuse control, and cost attribution much easier.

## 3. Hard Quotas

Coding agents and workflow agents can loop. A hard quota turns a bad loop into a
small failed run instead of a surprise bill.

Minimum useful controls:

- Per-token quota
- Clear remaining balance
- Error response when quota is exhausted

## 4. Request Logs

Good logs should show:

- Request time
- Model
- API token or project
- Prompt/input tokens
- Completion/output tokens
- Cache-read tokens, if available
- Status code / error

Without request-level logs, you can only guess why usage increased.

## 5. Pricing Clarity

Prefer services that show input, output, and cache-read prices per 1M tokens.

Be careful with unclear multipliers. A multiplier may be calculated against an
official reference price, an internal balance unit, a group ratio, or another
provider's rate.

## 6. Routing And Fallback

Routing helps when:

- One upstream has no balance
- One model route is slow
- A cheaper route is good enough for routine work
- A stronger route is needed only for hard tasks

For agentic coding, a common setup is:

```text
routine edits -> cheaper strong model
hard tasks    -> stronger model
quota         -> hard cap per token/project
logs          -> every request
```

## 7. Region And Compliance Notes

Before production use, check:

- Supported countries/regions
- Payment method
- Terms of service
- Data handling notes
- Whether the service is allowed for your target users

For Wappkit specifically, service access from mainland China is not provided.
