---
title: Sentech API Documentation
nav_order: 1
---

# Sentech API Documentation

Welcome to the Sentech API Documentation. Below are the available endpoints:

- [Create a Memory Field](create-memory-field.md)
- [Add a Memory](add-memory.md)
- [Query Memories](query-memories.md)
- [Chat Completions](chat-completions.md)
- [Get Supported Models](supported-models.md)

## Authentication

All API endpoints require authentication via an API key. Pass the API key in the `Authorization` header as follows:

```sh
Authorization: Bearer YOUR_API_KEY
```

## Memory Fields

Memory Fields serve as containers for storing AI-generated knowledge, or knowledge in general.. Each field is designed to hold related pieces of information that can be retrieved, updated, and connected dynamically over time. Memories in a field are ranked by **salience**, **relevance**, and **decay rate**, ensuring the most significant information is easily accessible while less relevant data naturally fades over time.

### Technical Details
- **Salience**: Measures the importance of a memory within the field.
- **Relevance**: Determines how well a memory matches queries.
- **Decay Rate**: Applies gradual relevance decay to older memories.
- **Connections**: Establish relationships between memories for more meaningful recall.

## Roadmap

We are actively developing new features to enhance the API, including:

- **Fine-Tuning Salience & Relevance**: Endpoints to adjust memory importance manually.
- **Dynamic Memory Clustering**: Automated reclustering of memories within fields.
- **Custom Relationship Management**: Fine-grained control over memory connections.

## Rate Limiting

To ensure fair usage, the API enforces rate limits based on subscription tiers:

| Tier/Plan    | Memory Field Queries per Month | Memories Added per Month |
|---------|------------------|-------------------|
| Free    | 1,000            | 500               |
| Basic   | 10,000           | 5,000             |
| Standard| 10,000           | 5,000             |
| Premium | 50,000           | 50,000            |

If you exceed your plan's limit, consider upgrading your subscription.

---
title: Pricing Plans
nav_order: 6
---

# Pricing Plans

## **Flexible and Scalable Pricing**
Designed for startups and enterprises, Sentech offers pricing plans based on account balance. To maintain a tier, you must sustain the required minimum balance.

### **Plan Overview**

| Tier/Plan  | Memory Field Queries per Month | Memories Added per Month |
|------------|------------------------------|-------------------------|
| Free       | 1,000                        | 500                     |
| Basic      | 10,000                        | 5,000                   |
| Standard   | 10,000                        | 5,000                   |
| Premium    | 50,000                        | 50,000                  |

---

## **Memory Field Pricing**

### **Free Tier** *(Balance: $0 - $5.00)*
- **One Free Memory Field**
- **Memory Field Creation:** FREE
- **Memory Usage:** $0.01 per memory addition
- **Query Usage:** $0.01 per query
- **Additional Field:** $3.00 per month
- **Memories Storage:** $0.025 per memory per month
- **Storage:** $3/GB per month

### **Basic Tier** *(Balance: $5.00 - $10.00)*
- **One Free Memory Field**
- **Memory Field Creation:** FREE
- **Memory Usage:** $0.005 per memory addition
- **Query Usage:** $0.005 per query
- **Additional Field:** $2.00 per month
- **Memories Storage:** $0.02 per memory per month
- **Storage:** $2/GB per month

### **Standard Tier** *(Balance: $10.00 - $100.00)*
- **One Free Memory Field**
- **Memory Field Creation:** FREE
- **Memory Usage:** $0.001 per memory addition
- **Query Usage:** $0.001 per query
- **Additional Field:** $1.00 per month
- **Memories Storage:** $0.005 per memory per month
- **Storage:** $1.5/GB per month

### **Premium Tier** *(Balance: $100+)*
- **One Free Memory Field**
- **Memory Field Creation:** FREE
- **Memory Usage:** $0.00075 per memory addition
- **Query Usage:** $0.00075 per query
- **Additional Field:** $1.00 per month
- **Memories Storage:** $0.001 per memory per month
- **Storage:** $1/GB per month

---

*Inference pricing is negotiable for partners. For invoices or further details, contact:*
📩 **service@sentech.ai**

---

## Community & Support

If you need support, join our community:
- **Discord**: [https://discord.gg/tVXVK7vyFE](https://discord.gg/tVXVK7vyFE)
- **Telegram**: [https://t.me/SentechAI](https://t.me/SentechAI)

