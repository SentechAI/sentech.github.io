---
title: Query Memories
nav_order: 4
---

# Query Memories

### **POST** `/fields/:fieldId/memories/query`

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
