---
sidebar_position: 2
sidebar_label: Get Members
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

## Get Members

Retrieve all workspace members along with their roles and permissions.

### Endpoint

```text
/api/public/v1/workspace/{id}/members
```

### Query Parameters

| Parameter | Type   | Description                            |
| --------- | ------ | -------------------------------------- |
| page      | number | Page number (default: 1)               |
| limit     | number | Items per page (default: 50, max: 100) |
| role      | string | Filter by role ID                      |

### Response Example

```json
{
  "success": true,
  "members": [
    {
      "userId": 123456,
      "username": "john_doe",
      "displayName": "John Doe",
      "thumbnail": "https://example.com/avatar.png",
      "role": {
        "id": "clz1234abcd",
        "name": "Owner",
        "permissions": ["MANAGE_MEMBERS", "MANAGE_ROLES", "MANAGE_SESSIONS"]
      }
    }
  ],
  "total": 42,
  "page": 1,
  "limit": 50,
  "pages": 1
}
```