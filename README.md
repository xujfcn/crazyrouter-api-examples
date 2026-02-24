# 🌍 Crazyrouter API Examples (Multi-Language)

> API examples in Python, Node.js, Go, Rust, Java, and cURL — All using Crazyrouter.

[Crazyrouter](https://crazyrouter.com?ref=github) — One key, 300+ models, 45% cheaper.

## 💰 Price Comparison

| Model | Official (In/Out per 1M tokens) | Crazyrouter | Savings |
|-------|--------------------------------|-------------|---------|
| Claude Opus 4 | $15 / $75 | $8.25 / $41.25 | **45%** |
| GPT-4o | $2.50 / $10 | $1.38 / $5.50 | **45%** |
| Gemini 2.5 Pro | $1.25 / $10 | $0.69 / $5.50 | **45%** |

## 📋 Examples

### cURL
```bash
curl https://crazyrouter.com/v1/chat/completions \
  -H "Authorization: Bearer sk-your-key" \
  -H "Content-Type: application/json" \
  -d '{"model":"gpt-4o","messages":[{"role":"user","content":"Hello!"}]}'
```

### Python
```python
from openai import OpenAI

client = OpenAI(
    api_key="sk-your-key",
    base_url="https://crazyrouter.com/v1"
)

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Hello!"}]
)
print(response.choices[0].message.content)
```

### Node.js / TypeScript
```typescript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "sk-your-key",
  baseURL: "https://crazyrouter.com/v1",
});

const response = await client.chat.completions.create({
  model: "claude-sonnet-4-20250514",
  messages: [{ role: "user", content: "Hello!" }],
});
console.log(response.choices[0].message.content);
```

### Go
```go
package main

import (
    "context"
    "fmt"
    openai "github.com/sashabaranov/go-openai"
)

func main() {
    config := openai.DefaultConfig("sk-your-key")
    config.BaseURL = "https://crazyrouter.com/v1"
    client := openai.NewClientWithConfig(config)

    resp, _ := client.CreateChatCompletion(
        context.Background(),
        openai.ChatCompletionRequest{
            Model: "gpt-4o",
            Messages: []openai.ChatCompletionMessage{
                {Role: "user", Content: "Hello!"},
            },
        },
    )
    fmt.Println(resp.Choices[0].Message.Content)
}
```

### Java
```java
// Using okhttp3
OkHttpClient client = new OkHttpClient();
String json = "{\"model\":\"gpt-4o\",\"messages\":[{\"role\":\"user\",\"content\":\"Hello!\"}]}";

Request request = new Request.Builder()
    .url("https://crazyrouter.com/v1/chat/completions")
    .addHeader("Authorization", "Bearer sk-your-key")
    .addHeader("Content-Type", "application/json")
    .post(RequestBody.create(json, MediaType.parse("application/json")))
    .build();

Response response = client.newCall(request).execute();
System.out.println(response.body().string());
```

### Rust
```rust
// Using reqwest
let client = reqwest::Client::new();
let response = client
    .post("https://crazyrouter.com/v1/chat/completions")
    .header("Authorization", "Bearer sk-your-key")
    .json(&serde_json::json!({
        "model": "gpt-4o",
        "messages": [{"role": "user", "content": "Hello!"}]
    }))
    .send()
    .await?;
```

## 🔧 Streaming Example (Python)
```python
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Tell me a story"}],
    stream=True
)
for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

## 🔗 Links
- 🌐 [Crazyrouter](https://crazyrouter.com?ref=github)
- 📖 [API Docs](https://crazyrouter.com/docs)
- 💬 [Telegram](https://t.me/crzrouter)

## 📄 License
MIT

