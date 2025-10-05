---
sidebar_position: 4
sidebar_label: Get User Activity
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

## Get User Activity

Retrieve detailed activity for a specific user.

### Endpoint

```text
/api/public/v1/workspace/{id}/user/{userid}/activity
```

### Query Parameters

| Parameter | Type     | Description                                       |
| --------- | -------- | ------------------------------------------------- |
| startDate | ISO 8601 | Filter by start date (e.g., 2024-01-01T00:00:00Z) |
| endDate   | ISO 8601 | Filter by end date (e.g., 2024-01-31T23:59:59Z)   |
| page      | number   | Page number (default: 1)                          |
| limit     | number   | Items per page (default: 50, max: 100)            |

### Response Example

```json
{
  "success": true,
  "user": {
    "userId": 123456,
    "username": "john_doe",
    "displayName": "John Doe",
    "thumbnail": "https://example.com/avatar.png"
  },
  "activity": {
    "totalSessions": 42,
    "totalDuration": 151200,
    "averageDuration": 3600,
    "totalMessages": 1024,
    "sessions": [
      {
        "id": "clz1234abcd",
        "startTime": "2024-01-01T00:00:00Z",
        "endTime": "2024-01-01T01:00:00Z",
        "duration": 3600,
        "messages": 42
      }
    ]
  },
  "page": 1,
  "limit": 50,
  "pages": 1
}
```
