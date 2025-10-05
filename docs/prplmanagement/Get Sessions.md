---
sidebar_position: 5
sidebar_label: Get Sessions
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

## Get Sessions

Retrieve upcoming or past sessions with optional filtering parameters.

### Endpoint

```text
/api/public/v1/workspace/{id}/sessions
```

### Query Parameters

| Parameter | Type     | Description                                 |
| --------- | -------- | ------------------------------------------- |
| upcoming  | boolean  | Get upcoming sessions (default: true)       |
| date      | ISO 8601 | Filter by date (e.g., 2024-01-01T00:00:00Z) |
| type      | string   | Filter by session type ID                   |
| host      | number   | Filter by host user ID                      |
| page      | number   | Page number (default: 1)                    |
| limit     | number   | Items per page (default: 50, max: 100)      |

### Response Example

```json
{
  "success": true,
  "sessions": [
    {
      "id": "clz1234abcd",
      "title": "Weekly Team Meeting",
      "description": "Regular team sync-up",
      "startTime": "2024-01-01T00:00:00Z",
      "endTime": "2024-01-01T01:00:00Z",
      "type": {
        "id": "clz5678efgh",
        "name": "Meeting",
        "color": "#3498db"
      },
      "host": {
        "userId": 123456,
        "username": "john_doe",
        "displayName": "John Doe",
        "thumbnail": "https://example.com/avatar.png"
      },
      "participants": [
        {
          "userId": 789012,
          "username": "jane_smith",
          "displayName": "Jane Smith",
          "thumbnail": "https://example.com/avatar2.png"
        }
      ],
      "maxParticipants": 10,
      "currentParticipants": 1
    }
  ],
  "total": 25,
  "page": 1,
  "limit": 50,
  "pages": 1
}
```