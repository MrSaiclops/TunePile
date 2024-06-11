# Pagination of Tunes

This tutorial will show you how to paginate through a list of tunes from the TunePile API to improve performance and user experience.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## Pagination of Tunes

To paginate through the list of tunes, send a `GET` request to the `/api/v1/tunes` endpoint with `page` and `limit` query parameters.

### Example Code

```python
import requests

# Replace with your API endpoint
url = '<API_ENDPOINT>/api/v1/tunes'
page = 1
limit = 10  # Number of records per page

response = requests.get(f"{url}?page={page}&limit={limit}")

if response.status_code == 200:
    paginated_tunes = response.json()
    for tune in paginated_tunes:
        print(f"Song Title: {tune['song_title']} - Link: {tune['link']}")
else:
    print("Failed to retrieve paginated tunes:", response.status_code, response.text)
```

### Response

- **200 OK:** The request was successful.
- **400 Bad Request:** Invalid pagination parameters.
- **500 Internal Server Error:** An error occurred on the server.
