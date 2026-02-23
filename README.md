# 🌍 Crazyrouter API Examples (Multi-Language)

> API examples in Python, Node.js, Go, Rust, Java, and cURL.

[Crazyrouter](https://crazyrouter.com?ref=github) — One key, 300+ models, 45% cheaper.

## cURL
```bash
curl https://crazyrouter.com/v1/chat/completions \
  -H "Authorization: Bearer sk-your-key" \
  -H "Content-Type: application/json" \
  -d '{"model":"gpt-4o","messages":[{"role":"user","content":"Hello"}]}'
```

## Python
```python
from openai import OpenAI
client = OpenAI(api_key="sk-your-key", base_url="https://crazyrouter.com/v1")
r = client.chat.completions.create(model="gpt-4o", messages=[{"role":"user","content":"Hello"}])
print(r.choices[0].message.content)
```

## Node.js
```javascript
import OpenAI from 'openai';
const client = new OpenAI({ apiKey: 'sk-your-key', baseURL: 'https://crazyrouter.com/v1' });
const r = await client.chat.completions.create({ model: 'gpt-4o', messages: [{ role: 'user', content: 'Hello' }] });
console.log(r.choices[0].message.content);
```

## Go
```go
// Use github.com/sashabaranov/go-openai
config := openai.DefaultConfig("sk-your-key")
config.BaseURL = "https://crazyrouter.com/v1"
client := openai.NewClientWithConfig(config)
```

## 🔗 [Crazyrouter](https://crazyrouter.com?ref=github) | [Telegram](https://t.me/crzrouter)
## 📄 License: MIT
