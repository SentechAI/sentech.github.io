---
title: Create Memory Field
nav_order: 2
---

# Create a Memory Field

### **POST** `https://api.sentech.ai/fields/create-memory-field`

#### **Description**

Creates a new memory field for storing AI-generated memories.

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
##### **Success Response**
```json
{
  "message": "Memory field created successfully",
  "field_id": "abc123"
}
```

##### **Error Responses**
**400 Bad Request**
```json
{
  "message": "Field name is required"
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

### **cURL Example**
```sh
curl -X POST "https://api.sentech.ai/fields/create-memory-field" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
          "name": "New Memory Field"
         }'
```

#### **Implementation Details**
- The API requires authentication via an API key in the `Authorization` header.
- The request body must include a `name` field, otherwise, a `400 Bad Request` response is returned.

### **Rate Limiting**
- If the user exceeds their query limit, a `429 Too Many Requests` response is returned with a message suggesting an upgrade.

For further information, contact support at `support@sentech.ai`.

