---
title: Create Memory
nav_order: 3
---

# Create a Memory

### **POST** `https://api.sentechl.ai/fields/:fieldId/memories`

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
