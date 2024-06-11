# Filtering and Searching Tunes

This tutorial will guide you through the process of filtering and searching for specific tunes in the TunePile API based on various criteria such as `song_title`, `lyric_writer`, and `music_writer`.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## Filtering and Searching Tunes

To filter and search for tunes, send a `GET` request to the `/api/v1/tunes` endpoint with the desired query parameters.

### Example Code

```python
import requests

# Replace with your API endpoint
url = '<API_ENDPOINT>/api/v1/tunes'
query_params = {
    "song_title": "Willow Weeps"  # Specify other parameters as needed
}

response = requests.get(url, params=query_params)

if response.status_code == 200:
    tunes = response.json()
    for tune in tunes:
        print(f"Song Title: {tune['song_title']} - Link: {tune['link']}")
else:
    print("Failed to retrieve tunes:", response.status_code, response.text)
```

### Response

- **200 OK:** The request was successful.
- **400 Bad Request:** Invalid query parameters.
- **500 Internal Server Error:** An error occurred on the server.
