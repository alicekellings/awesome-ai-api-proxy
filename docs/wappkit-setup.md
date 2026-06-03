# Wappkit Setup

Wappkit provides an OpenAI-compatible API endpoint:

```text
https://api.wappkit.com/v1
```

## Steps

1. Sign up at <https://api.wappkit.com>.
2. Top up your account.
3. Create an API token.
4. Set a quota for the token if you want a hard budget cap.
5. Configure your tool with:

```text
base_url = https://api.wappkit.com/v1
api_key  = your Wappkit token
```

## Recommended Token Layout

Use separate tokens for separate use cases:

```text
cursor-personal-project
cline-long-refactor
n8n-ai-agent-prod
customer-demo-key
```

This makes it easier to see which tool or workflow is using the most tokens.

## Coding Agent Notes

For Cursor, Cline, Continue, Roo Code, and Aider:

- Set the custom OpenAI-compatible base URL if the tool supports it.
- Use a scoped token rather than your main account key.
- Start with a small quota for new agents.
- Watch request logs during the first long run.

## Pricing Note

Pricing can vary by model, token group, route, and upstream availability. Check
the live model marketplace before production use.

At the time this repository was prepared, selected GPT models were positioned
around `3%-5%` of official reference pricing. Treat that as a positioning note,
not a permanent guarantee.
