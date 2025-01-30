---
title: Sentech API Documentation
nav_order: 1
---

# Sentech API Documentation

## Authentication
All API endpoints require authentication via an API key. Pass the API key in the `Authorization` header as follows:

```
Authorization: Bearer YOUR_API_KEY
```

---

## Create a Memory

### **POST** `/fields/:fieldId/memories`

#### **Description**
Adds a new memory to a specified memory field.

#### **Headers**
| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Path Parameters**
| Parameter | Type   | Required | Description              |
|-----------|--------|----------|--------------------------|
| fieldId   | String | Yes      | Unique ID of the memory field |

#### **Request Body**
```json
{
  "content": "Your memory content here"
}
```

#### **Response**
```json
{
  "message": "Memory added successfully",
  "data": { ... }
}
```

#### **Error Codes**
- 400: Content is required
- 404: User not found
- 500: Internal server error

---

## Query Memories

### **POST** `/fields/:fieldId/memories/query`

#### **Description**
Queries memories stored within a specified field.

#### **Headers**
| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Path Parameters**
| Parameter | Type   | Required | Description              |
|-----------|--------|----------|--------------------------|
| fieldId   | String | Yes      | Unique ID of the memory field |

#### **Request Body**
```json
{
  "query": "Your search query",
  "top_k": 5
}
```

#### **Response**
```json
{
  "results": [ ... ]
}
```

#### **Error Codes**
- 400: Query text is required
- 404: User not found
- 500: Internal server error

---

## AI Chat Completion

### **POST** `/v1/chat/completions`

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

#### **Response**
```json
{
  "id": "chatcmpl-123456",
  "object": "chat.completion",
  "created": 1234567890,
  "model": "meta-llama/Meta-Llama-3.1-8B-Instruct",
  "usage": { ... },
  "choices": [ { "message": { "content": "Hello, I am an AI assistant." } } ]
}
```

#### **Error Codes**
- 400: Messages must be a non-empty array
- 400: Unsupported model
- 400: Insufficient balance
- 401: Invalid API key
- 500: Internal server error

---

## Get Supported Models

### **GET** `/supported-models`

#### **Description**
Retrieves a list of supported AI models.

#### **Response**
```json
{
  "models": [
    { "model_name": "meta-llama/Meta-Llama-3.1-8B-Instruct", "price": 0.15 }
  ]
}
```

#### **Error Codes**
- 500: Internal server error

---

## Create a Memory Field

### **POST** `/fields/create-memory-field`

#### **Description**
Creates a new memory field for the authenticated user.

#### **Headers**
| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Request Body**
```json
{
  "name": "New Memory Field"
}
```

#### **Response**
```json
{
  "message": "Memory field created successfully",
  "field_id": "123e4567-e89b-12d3-a456-426614174000"
}
```

#### **Error Codes**
- 400: Field name is required
- 404: User not found
- 500: Internal server error
