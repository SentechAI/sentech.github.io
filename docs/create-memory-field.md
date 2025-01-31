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
- The rate-limiting middleware checks the user’s query usage against their subscription tier and enforces limits.
- The API interacts with an external service (`EMF_API_URL`) to create the memory field and stores the result in the database.

#### **Backend Code Summary**
- The endpoint verifies the API key and applies rate limits.
- The user is validated before proceeding.
- The system makes a request to an external API to create a memory field.
- The memory field is saved in the database with an initial `memory_count` of `0`.
- Errors are handled gracefully, returning appropriate HTTP status codes and messages.

### **Rate Limiting**
- The rate limit is determined by the user’s subscription tier.
- If the user exceeds their query limit, a `429 Too Many Requests` response is returned with a message suggesting an upgrade.

For further information, contact support at `support@sentech.ai`.

