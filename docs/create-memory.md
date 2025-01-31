---
title: Create Memory
nav_order: 3
---

# Create a Memory

### **POST** `https://api.sentech.ai/fields/:fieldId/memories`

#### **Description**

Adds a new memory to a specified memory field.

#### **Headers**

| Key           | Type   | Required | Description                |
|---------------|--------|----------|----------------------------|
| Authorization | String | Yes      | API key for authentication |

#### **Path Parameters**

| Parameter | Type   | Required | Description                  |
|-----------|--------|----------|------------------------------|
| fieldId   | String | Yes      | Unique ID of the memory field|

#### **Request Body**

```json
{
  "content": "Your memory content here"
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

### **cURL Example**
```sh
curl -X POST "https://api.sentech.ai/fields/{fieldId}/memories" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
          "content": "Your memory content here"
         }'
```

#### **Implementation Details**
- The API requires authentication via an API key in the `Authorization` header.
- The request body must include a `content` field, otherwise, a `400 Bad Request` response is returned.

### **Rate Limiting**
- Users have different query and memory limits based on their subscription tiers:
  - **Free:** 1,000 queries, 500 memories
  - **Basic:** 10,000 queries, 5,000 memories
  - **Standard:** 10,000 queries, 5,000 memories
  - **Premium:** 50,000 queries, 50,000 memories
- If the user exceeds their query or memory limit, a `429 Too Many Requests` response is returned with a message suggesting an upgrade.


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

For further information, contact support at `support@sentech.ai`.


