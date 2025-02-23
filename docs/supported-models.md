---
title: Supported Models
nav_order: 6
---

# Supported Models

### **GET** `https://api.sentech.ai/supported-models`

#### **Description**
Retrieves a list of supported AI models available for use.

### **cURL Example**
```sh
curl -X GET "https://api.sentech.ai/supported-models"
```

#### **Response**
##### **Success Response**
```json
{
  "models": [
    {
      "model_name": "meta-llama/Meta-Llama-3.1-8B-Instruct",
      "price": 0.15
    },
    {
      "model_name": "meta-llama/Meta-Llama-3.3-70B-Instruct",
      "price": 0.6
    }
  ]
}
```

##### **Error Responses**

**500 Internal Server Error**
```json
{
  "message": "Internal server error",
  "error": "Error details"
}
```
