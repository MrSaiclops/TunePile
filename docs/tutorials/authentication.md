
# Authentication

This tutorial will guide you through the authentication process for the TunePile API, ensuring secure access to the service.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## User Authentication

To authenticate a user, send a `POST` request to the `/api/v1/auth/login` endpoint with the user's credentials.

### Example Code

```python
import requests
import json

# Replace with your API endpoint
url = '<API_ENDPOINT>/api/v1/auth/login'
credentials = {
    "username": "existinguser",
    "password": "password123"
}

response = requests.post(url, json=credentials)

if response.status_code == 200:
    token = response.json().get('token')
    print("Authentication successful! Token:", token)
else:
    print("Authentication failed:", response.status_code, response.text)
```

### Response

- **200 OK:** The authentication was successful.
- **401 Unauthorized:** Invalid credentials.
- **500 Internal Server Error:** An error occurred on the server.
