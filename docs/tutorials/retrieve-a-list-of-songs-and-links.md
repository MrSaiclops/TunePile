# TunePile API Tutorial: List of Songs and Links

Welcome to the TunePile API service tutorial! This guide will help you fetch a list of songs and their corresponding links using the TunePile API.

## Example JSON Database

Here's a sample JSON database from TunePile:

```json
{
  "tunes": [
    {
      "song_title": "Willow Weeps",
      "lyric_writer": "Weird Summer",
      "music_writer": "Bob Kimball",
      "link": "https://open.spotify.com/track/2Q8KiCGXpBriTBvsUfEGZj?si=aaefedb294db43fc",
      "id": 1
    },
    {
      "song_title": "Move My Car",
      "lyric_writer": "BrowBeaters",
      "music_writer": "BrowBeaters",
      "link": "https://drive.google.com/file/d/0B6GXm1GcjzDHNG51N0o0MVJnV0k/view?usp=drive_link&resourcekey=0-CAqUq5rIFObWEOUj1q7xcg",
      "id": 2
    },
    {
      "song_title": "Broken Bones",
      "lyric_writer": "Kevin Henry",
      "music_writer": "Kevin Henry",
      "link": "https://drive.google.com/file/d/1ztIc5S7rKPiODomZAyF6aD407UTcD1q1/view?usp=drive_link",
      "id": 3
    }
  ],
 "notes": [
    {
      "note_name": "Mid-tempo rocker, jangle pop, well-recorded.",
      "version": "Final LP",
      "tune_id": 1      
    },
    {
      "note_name": "Scratch version of early song. May be usable.",
      "version": "Scratchpad",
      "tune_id": 2      
    },
    {
      "note_name": "Rough early draft for comments only.",
      "version": "Reference tune",
      "tune_id": 3      
    }
  ]
}
```

## Steps to Fetch List of Songs

### 1. Setup

First, you need to set up your environment to make API requests. For this tutorial, we'll use Python and the `requests` library:

```bash
pip install requests
```

### 2. Make an API Call

Here is how to make an API call to fetch the list of songs:

```python
import requests

# Replace with the actual endpoint if available
url = 'https://api.tunepile.com/v1/tunes'

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print(f"Failed to fetch data: {response.status_code}")
```

### 3. Parse JSON Response

You can parse the JSON response to get the list of songs and their links:

```python
tunes = [
    {
        "song_title": "Willow Weeps",
        "lyric_writer": "Weird Summer",
        "music_writer": "Bob Kimball",
        "link": "https://open.spotify.com/track/2Q8KiCGXpBriTBvsUfEGZj?si=aaefedb294db43fc",
        "id": 1
    },
    {
        "song_title": "Move My Car",
        "lyric_writer": "BrowBeaters",
        "music_writer": "BrowBeaters",
        "link": "https://drive.google.com/file/d/0B6GXm1GcjzDHNG51N0o0MVJnV0k/view?usp=drive_link&resourcekey=0-CAqUq5rIFObWEOUj1q7xcg",
        "id": 2
    },
    {
        "song_title": "Broken Bones",
        "lyric_writer": "Kevin Henry",
        "music_writer": "Kevin Henry",
        "link": "https://drive.google.com/file/d/1ztIc5S7rKPiODomZAyF6aD407UTcD1q1/view?usp=drive_link",
        "id": 3
    }
]

# Extracting song titles and links
for tune in tunes:
    print(f"Song Title: {tune['song_title']}")
    print(f"Link: {tune['link']}\n")
```

### 4. Complete Example

Here is a complete example combining all steps:

```python
import requests

# Replace with the actual endpoint if available
url = 'https://api.tunepile.com/v1/tunes'

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    tunes = data['tunes']
    
    # Extracting song titles and links
    for tune in tunes:
        print(f"Song Title: {tune['song_title']}")
        print(f"Link: {tune['link']}\n")
else:
    print(f"Failed to fetch data: {response.status_code}")
```

## Conclusion

You've successfully fetched the list of songs and their links using the TunePile API. You can now extend this script to fetch additional details or format the output as desired.