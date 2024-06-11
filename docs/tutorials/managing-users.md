# Managing Users

This tutorial will guide you through creating new users in the TunePile API, allowing you to manage access and permissions.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## Creating a New User

To create a new user, send a `POST` request to the `/api/v1/users` endpoint with the user's details.

### Example Code

```python
import requests
import json

# Replace with your API endpoint
url = '<API_ENDPOINT>/api/v1/users'
payload = {
    "username": "newuser",
    "password": "password123",
    "email": "newuser@example.com"
}

response = requests.post(url, json=payload)

if response.status_code == 201:
    print("User successfully created!")
else:
    print("Failed to create user:", response.status_code, response.text)
```

### Response

- **201 Created:** The user was successfully created.
- **400 Bad Request:** Invalid input data.
- **500 Internal Server Error:** An error occurred on the server.
