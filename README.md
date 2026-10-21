# Red Team Model Router — API Examples

Quickstart snippets for [Red Team Model Router](https://unst33r.si), an OpenAI-compatible API for authorized red teaming work: per-token pricing, abliterated and frontier open models, tools/SSE support. Full model catalog and pricing: <https://unst33r.si/pricing>.

## Python (openai SDK)

```python
from openai import OpenAI

client = OpenAI(base_url="https://api.unst33r.si/v1", api_key="sk-...")

resp = client.chat.completions.create(
    model="dolphin-mixtral",   # any catalog model
    messages=[{"role": "user", "content": "Summarize MITRE ATT&CK T1555"}],
)
print(resp.choices[0].message.content)
```

## curl

```bash
curl https://api.unst33r.si/v1/chat/completions \
  -H "Authorization: Bearer $KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"dolphin-mixtral","messages":[{"role":"user","content":"ping"}]}'
```

## Where this fits

Use-cases these snippets were written for: [AI red teaming](https://unst33r.si/use-cases/ai-red-teaming) and [security agent teams](https://unst33r.si/use-cases/security-agents).

Authorized use only — see the acceptable-use policy on the site.
