---
sidebar_position: 5
sidebar_label: Get Session Types
sidebar_class_name: prplManagement
---

# prplManagement | API

:::info
Always keep your API key private!
:::

### <font color="#C21807">Preparing your request</font>

All API requests **must** include an Authorization header:

```http
Authorization: Bearer your_api_key_here
````

:::danger API Rate Limits
API requests are limited to **100 requests per minute** per API key. Exceeding this limit will return a **429 Too Many Requests** response.
:::

### <font color="#C21807">Request</font>

## Get Session Types

Retrieve all session types with their configurations.

### Endpoint

```text
/api/public/v1/workspace/{id}/session-types
```

### Response Example

```json
{
  "success": true,
  "types": [
    {
      "id": "clz5678efgh",
      "name": "Meeting",
      "description": "Regular team meetings",
      "color": "#3498db",
      "requiresApproval": false,
      "maxParticipants": 10,
      "allowSelfSignup": true
    }
  ]
}
```
