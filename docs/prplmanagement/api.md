---
sidebar_position: 1
sidebar_label: API Intro
sidebar_class_name: prplManagement
---

# prplManagement | API

:::info

Always keep your API key private!

:::

### <font color="#C21807">Getting your API key</font>

Navigate to your workspace settings, and navigate to the Public API subsection.
From there generate an API key, and store it. You won't be able to view it again!

### <font color="#C21807">Preparing your request</font>

All API requests **must** carry an Authorization header.

```
Authorization: Bearer your_api_key_here
```

:::danger[API Rate Limits]

API requests are limited to **100** request per minute per API key. Exceeding this limit will result in a **429 Too Many Requests** response

:::