---
title: Chat Completions
nav_order: 4
---

# Chat Completions

### **POST** `https://api.sentech.ai/v1/chat/completions`

#### **Description**
Generates AI responses based on a given conversation context.

#### **Headers**

| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Request Body**

```json
{
  "model": "meta-llama/Meta-Llama-3.1-8B-Instruct",
  "messages": [
    { "role": "system", "content": "You are a helpful AI assistant." },
    { "role": "user", "content": "What is the capital of France?" }
  ],
  "temperature": 1.2,
  "top_p": 0.95,
  "top_k": 90,
  "frequency_penalty": 0.4,
  "presence_penalty": 0.7,
  "max_tokens": 150
}
```

#### **Response**
##### **Success Response**
```json
{
  "id": "chatcmpl-1711122334",
  "object": "chat.completion",
  "created": 1711122334,
  "model": "meta-llama/Meta-Llama-3.1-8B-Instruct",
  "usage": {
    "prompt_tokens": 50,
    "completion_tokens": 20,
    "total_tokens": 70
  },
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "The capital of France is Paris."
      }
    }
  ]
}
```

##### **Error Responses**
**400 Bad Request**
```json
{
  "message": "Messages must be a non-empty array."
}
```

**401 Unauthorized**
```json
{
  "message": "Invalid API key."
}
```

**500 Internal Server Error**
```json
{
  "message": "Internal server error",
  "error": "Error details"
}
```

### **cURL Example**
```sh
curl -X POST "https://api.sentech.ai/v1/chat/completions" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
          "model": "meta-llama/Meta-Llama-3.1-8B-Instruct",
          "messages": [
            { "role": "system", "content": "You are a helpful AI assistant." },
            { "role": "user", "content": "What is the capital of France?" }
          ],
          "temperature": 1.2,
          "top_p": 0.95,
          "top_k": 90,
          "frequency_penalty": 0.4,
          "presence_penalty": 0.7,
          "max_tokens": 150
         }'
```

