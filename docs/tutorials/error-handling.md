# Error Handling

This tutorial will guide you through handling common errors when interacting with the TunePile API, helping you debug and resolve issues efficiently.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## Handling Common Errors

To handle common errors, check the status code of your API response and implement appropriate error messages.

### Example Code

```python
import requests

# Replace with your API endpoint and the actual ID of the tune you want to retrieve
url = '<API_ENDPOINT>/api/v1/tunes/9999'  # Assume this ID does not exist

response = requests.get(url)

if response.status_code == 200:
    tune = response.json()
    print(f"Song Title: {tune['song_title']} - Link: {tune['link']}")
elif response.status_code == 404:
    print("Tune not found.")
elif response.status_code == 500:
    print("Internal server error. Please try again later.")
else:
    print("Failed to retrieve tune:", response.status_code, response.text)
```

### Response Codes

- **200 OK:** The request was successful.
- **404 Not Found:** The requested resource was not found.
- **500 Internal Server Error:** An error occurred on the server.
