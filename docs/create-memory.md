---
title: Add Memory
nav_order: 3
---

# Add a Memory

### **POST** `https://api.sentech.ai/fields/:fieldId/memories`

#### **Description**
Adds a new memory to a specified memory field.

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
curl -X POST "https://api.sentech.ai/fields/{fieldId}/memories" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
          "content": "Your memory content here",
          "timestamp": 1711122334,
          "relevance": 1.0,
          "decay_rate": 0.01,
          "salience": 1.0,
          "connections": ["memory-uuid-1", "memory-uuid-2"]
         }'
```

#### **Request Body**

```json
{
  "content": "Your memory content here",
  "timestamp": 1711122334,
  "relevance": 1.0,
  "decay_rate": 0.01,
  "salience": 1.0,
  "connections": ["memory-uuid-1", "memory-uuid-2"]
}
```

#### **Response**
##### **Success Response**
```json
{
  "message": "Memory added successfully",
  "memory_id": "xyz789"
}
```

##### **Error Responses**
**400 Bad Request**
```json
{
  "message": "Content is required"
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
