---
title: Query Memories
nav_order: 4
---

# Query Memories

### **POST** `https://api.sentech.ai/fields/:fieldId/memories/query`

#### **Description**

Queries stored memories within a specific memory field.

#### **Headers**

| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Path Parameters**

| Parameter | Type   | Required | Description                  |
|-----------|--------|----------|------------------------------|
| fieldId   | String | Yes      | Unique ID of the memory field|

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
  "results": [
    {
      "memory_id": "abc123",
      "content": "Relevant memory content here."
    }
  ]
}
```

#### **Error Codes**
- 400: Query text is required
- 404: User not found
- 500: Internal server error
```
