# TunePile API Quick Start Guide

Welcome to the TunePile API Quick Start Guide. This document will help you get started with the basic operations you can perform using the TunePile API, including creating, reading, updating, and deleting tunes and notes.

## Prerequisites

Before you begin, you need to have:
- Python installed on your machine (version 3.x recommended).
- `requests` library installed. You can install it using the following command:
  
  ```bash
  pip install requests
  ```

## Setup

1. **Get the API Endpoint:**
   Replace `<API_ENDPOINT>` with the actual endpoint provided by TunePile.

2. **Set up your project environment:**
   Create a directory for your project and navigate to it using your terminal.

   ```bash
   mkdir tunepile-api-quickstart
   cd tunepile-api-quickstart
   ```

## Basic Operations

### 1. Creating a New Tune

You can create a new tune by sending a `POST` request to the `/api/v1/tunes` endpoint.

```python
import requests
import json

url = '<API_ENDPOINT>/api/v1/tunes'
payload = {
    "song_title": "New Song",
    "lyric_writer": "New Writer",
    "music_writer": "New Composer",
    "link": "http://example.com/newsong"
}

response = requests.post(url, json=payload)

if response.status_code == 201:
    print("Tune successfully created!")
else:
    print("Failed to create tune:", response.status_code, response.text)
```

### 2. Retrieving a List of Tunes

To get a list of all tunes, send a `GET` request to the `/api/v1/tunes` endpoint.

```python
url = '<API_ENDPOINT>/api/v1/tunes'

response = requests.get(url)

if response.status_code == 200:
    tunes = response.json()
    for tune in tunes:
        print(f"Song Title: {tune['song_title']} - Link: {tune['link']}")
else:
    print("Failed to retrieve tunes:", response.status_code, response.text)
```

### 3. Updating an Existing Tune

To update a tune, send a `PUT` request to the `/api/v1/tunes/{id}` endpoint with the tune ID.

```python
tune_id = 1  # replace with the actual ID of the tune you want to update
url = f'<API_ENDPOINT>/api/v1/tunes/{tune_id}'
payload = {
    "song_title": "Updated Song",
    "lyric_writer": "Updated Writer",
    "music_writer": "Updated Composer",
    "link": "http://example.com/updatedsong"
}

response = requests.put(url, json=payload)

if response.status_code == 200:
    print("Tune successfully updated!")
else:
    print("Failed to update tune:", response.status_code, response.text)
```

### 4. Deleting a Tune

To delete a tune, send a `DELETE` request to the `/api/v1/tunes/{id}` endpoint with the tune ID.

```python
tune_id = 1  # replace with the actual ID of the tune you want to delete
url = f'<API_ENDPOINT>/api/v1/tunes/{tune_id}'

response = requests.delete(url)

if response.status_code == 204:
    print("Tune successfully deleted!")
else:
    print("Failed to delete tune:", response.status_code, response.text)
```

## Conclusion

This Quick Start guide provides you with the essential information to perform basic CRUD operations using the TunePile API. Feel free to explore more advanced features and further customize your interaction with the API as needed.

