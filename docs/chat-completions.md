---
title: AI Chat Completion
nav_order: 5
---

# AI Chat Completion

### **POST** `https://api.sentech.ai/v1/chat/completions`

#### **Description**
Sends messages to an AI model and retrieves a response.

#### **Headers**
| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Request Body**
```json
{
  "model": "meta-llama/Meta-Llama-3.1-8B-Instruct",
  "messages": [
    { "role": "user", "content": "Hello, how are you?" }
  ],
  "temperature": 1.0,
  "top_p": 0.95,
  "top_k": 90,
  "frequency_penalty": 0.4,
  "presence_penalty": 0.7,
  "max_tokens": 150
}
```
