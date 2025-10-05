---
sidebar_position: 1
sidebar_label: Get Information
sidebar_class_name: prplManagement
---

# prplManagement | API

:::info
Always keep your API key private!
:::

### <font color="#C21807">Preparing your request</font>

All API requests **must** carry an Authorization header:

```http
Authorization: Bearer your_api_key_here
````

:::danger API Rate Limits
API requests are limited to **100 requests per minute** per API key. Exceeding this limit will result in a **429 Too Many Requests** response.
:::

### <font color="#C21807">Request</font>

## Get Information

Get workspace information including name, description, and member count.

### Endpoint

```text
/api/public/v1/workspace/{id}/info
```

### Response Example

```json
{
  "success": true,
  "workspace": {
    "groupId": 14144149,
    "name": "My Workspace",
    "description": "Workspace description",
    "logo": "https://example.com/logo.png",
    "memberCount": 42,
    "roles": [
      {
        "id": "clz1234abcd",
        "name": "Owner",
        "permissions": ["MANAGE_MEMBERS", "MANAGE_ROLES", "MANAGE_SESSIONS"]
      }
    ]
  }
}
```
