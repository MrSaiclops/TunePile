# Adding Multiple Tunes in Bulk

This tutorial will guide you through adding multiple tunes to the TunePile API in a single request, saving time and reducing the number of API calls.

## Prerequisites

- Python installed (version 3.x recommended).
- Requests library installed:
  ```bash
  pip install requests
  ```

## Adding Multiple Tunes in Bulk

To add multiple tunes, send a `POST` request to the `/api/v1/tunes/bulk` endpoint with an array of tune objects.

### Example Code

```python
import requests
import json

# Replace with your API endpoint
url = '<API_ENDPOINT>/api/v1/tunes/bulk'
payload = [
    {
        "song_title": "Song One",
        "lyric_writer": "Writer One",
        "music_writer": "Composer One",
        "link": "http://example.com/song1"
    },
    {
        "song_title": "Song Two",
        "lyric_writer": "Writer Two",
        "music_writer": "Composer Two",
        "link": "http://example.com/song2"
    }
]

response = requests.post(url, json=payload)

if response.status_code == 201:
    print("Tunes successfully created in bulk!")
else:
    print("Failed to create tunes in bulk:", response.status_code, response.text)
```

### Response

- **201 Created:** The tunes were successfully created.
- **400 Bad Request:** Invalid input data.
- **500 Internal Server Error:** An error occurred on the server.
