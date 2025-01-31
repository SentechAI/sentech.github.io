---
title: Query Memories
nav_order: 4
---

# Query Memories

### **POST** `https://api.sentech.ai/fields/:fieldId/memories/query`

#### **Description**
Retrieves relevant memories from a specified memory field using AI-powered search.

#### **Headers**

| Key           | Type   | Required | Description                |
|--------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Path Parameters**

| Parameter | Type   | Required | Description                  |
|-----------|--------|----------|------------------------------|
| fieldId   | String | Yes      | Unique ID of the memory field|

### **cURL Example**
```sh
curl -X POST "https://api.sentech.ai/fields/{fieldId}/memories/query" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
          "query": "What memories do I have about AI?",
          "top_k": 10,
          "depth_k": 3
         }'
```

#### **Request Body**

```json
{
  "query": "What memories do I have about AI?",
  "top_k": 10,
  "depth_k": 3
}
```

#### **Response**
##### **Success Response**
```json
{
  "query": "What memories do I have about AI?",
  "results": [
    {
      "uuid": "memory-1",
      "content": "AI is revolutionizing the world of technology.",
      "timestamp": 1711122334,
      "relevance": 0.9,
      "similarity": 0.95
    },
    {
      "uuid": "memory-2",
      "content": "Machine learning is a subset of AI.",
      "timestamp": 1711122444,
      "relevance": 0.85,
      "similarity": 0.92
    }
  ]
}
```

##### **Error Responses**
**400 Bad Request**
```json
{
  "message": "Query text is required"
}
```

**404 Not Found**
```json
{
  "message": "User not found"
}
```

**429 Too Many Requests**
```json
{
  "message": "Rate limit exceeded. Upgrade your plan for more queries."
}
```

**500 Internal Server Error**
```json
{
  "message": "Internal server error",
  "error": "Error details"
}
```
