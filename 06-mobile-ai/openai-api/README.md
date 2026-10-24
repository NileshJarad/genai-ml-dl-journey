# OpenAI API for Mobile

## Overview

OpenAI API provides access to state-of-the-art language models (GPT-4, GPT-4o, GPT-3.5 Turbo) for integration into mobile applications. Key features include:

- Text generation and chat completion
- Function calling
- Structured output
- Vision capabilities
- Embeddings generation

## Models

| Model | Context | Best For |
|-------|---------|----------|
| GPT-4o | 128K | Best overall performance |
| GPT-4o Mini | 128K | Cost-effective, fast |
| GPT-4 Turbo | 128K | Complex reasoning |
| GPT-3.5 Turbo | 16K | Simple tasks, cost-optimized |

## API Usage

### Basic Chat Completion
```python
from openai import OpenAI

client = OpenAI(api_key=os.environ["OPENAI_API_KEY"])

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Hello!"}
    ]
)
```

### Function Calling
```python
tools = [{
    "type": "function",
    "function": {
        "name": "get_weather",
        "description": "Get current weather",
        "parameters": {
            "type": "object",
            "properties": {
                "location": {"type": "string"}
            },
            "required": ["location"]
        }
    }
}]

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "What's the weather in NYC?"}],
    tools=tools
)
```

### Structured Output (JSON Mode)
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Extract info as JSON"}],
    response_format={"type": "json_object"}
)
```

### Vision (Image Understanding)
```python
import base64

with open("image.jpg", "rb") as f:
    image_data = base64.b64encode(f.read()).decode()

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{
        "role": "user",
        "content": [
            {"type": "text", "text": "Describe this image"},
            {"type": "image_url", "image_url": {"url": f"data:image/jpeg;base64,{image_data}"}}
        ]
    }]
)
```

### Embeddings
```python
response = client.embeddings.create(
    model="text-embedding-3-small",
    input="Your text here"
)
embedding = response.data[0].embedding
```

## Mobile Integration

### iOS (Swift)
```swift
import Foundation

let url = URL(string: "https://api.openai.com/v1/chat/completions")!
var request = URLRequest(url: url)
request.httpMethod = "POST"
request.setValue("Bearer \(apiKey)", forHTTPHeaderField: "Authorization")
request.setValue("application/json", forHTTPHeaderField: "Content-Type")

let body = [
    "model": "gpt-4o",
    "messages": [["role": "user", "content": "Hello"]]
]
request.httpBody = try JSONSerialization.data(withJSONObject: body)
```

### Android (Kotlin)
```kotlin
val client = OkHttpClient()
val json = JSONObject().apply {
    put("model", "gpt-4o")
    put("messages", JSONArray().put(
        JSONObject().put("role", "user").put("content", "Hello")
    ))
}

val request = Request.Builder()
    .url("https://api.openai.com/v1/chat/completions")
    .addHeader("Authorization", "Bearer $apiKey")
    .addHeader("Content-Type", "application/json")
    .post(json.toString().toRequestBody())
    .build()
```

## Best Practices for Mobile

1. **Security**
   - Never hardcode API keys
   - Use backend proxy for key management
   - Implement rate limiting

2. **Performance**
   - Stream responses for better UX
   - Cache frequent responses
   - Use smaller models for simple tasks

3. **Cost Management**
   - Monitor token usage
   - Set budget alerts
   - Use appropriate model tier

4. **Offline Handling**
   - Cache previous responses
   - Provide fallback responses
   - Graceful degradation

5. **Error Handling**
   - Retry with exponential backoff
   - Handle rate limits (429)
   - User-friendly error messages

## Related Libraries

- `openai-python` - Official Python SDK
- `openai-node` - Official Node.js SDK
- Community SDKs for Swift, Kotlin, Dart
- `tiktoken` - Token counting