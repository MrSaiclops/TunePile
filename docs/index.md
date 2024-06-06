# TunePile API Reference

Welcome to the TunePile API Reference. This documentation provides detailed information about the available API endpoints and how to perform CRUD operations on TunePile's resources.

## Table of Contents

1. [Create](#create)
2. [Read](#read)
3. [Update](#update)
4. [Delete](#delete)
5. [Tutorials](#tutorials)

## Create

### Create a New Tune

**Endpoint:** `/api/v1/tunes`

**Method:** `POST`

**Description:** Create a new tune in the TunePile database.

**Request Body:**

```json
{
  "song_title": "string",
  "lyric_writer": "string",
  "music_writer": "string",
  "link": "string"
}
```

**Response:**

- **201 Created:** Tune successfully created.
- **400 Bad Request:** Invalid input data.

### Create a New Note

**Endpoint:** `/api/v1/notes`

**Method:** `POST`

**Description:** Create a new note associated with a specific tune.

**Request Body:**

```json
{
  "note_name": "string",
  "version": "string",
  "tune_id": "integer"
}
```

**Response:**

- **201 Created:** Note successfully created.
- **400 Bad Request:** Invalid input data.

## Read

### Retrieve a List of Tunes

**Endpoint:** `/api/v1/tunes`

**Method:** `GET`

**Description:** Retrieve a list of all tunes in the database.

**Response:**

- **200 OK:** Successfully retrieved list of tunes.
- **500 Internal Server Error:** Error retrieving data.

### Retrieve a Specific Tune

**Endpoint:** `/api/v1/tunes/{id}`

**Method:** `GET`

**Description:** Retrieve details of a specific tune by ID.

**Response:**

- **200 OK:** Successfully retrieved tune details.
- **404 Not Found:** Tune not found.

### Retrieve a List of Notes

**Endpoint:** `/api/v1/notes`

**Method:** `GET`

**Description:** Retrieve a list of all notes in the database.

**Response:**

- **200 OK:** Successfully retrieved list of notes.
- **500 Internal Server Error:** Error retrieving data.

### Retrieve a Specific Note

**Endpoint:** `/api/v1/notes/{id}`

**Method:** `GET`

**Description:** Retrieve details of a specific note by ID.

**Response:**

- **200 OK:** Successfully retrieved note details.
- **404 Not Found:** Note not found.

## Update

### Update a Tune

**Endpoint:** `/api/v1/tunes/{id}`

**Method:** `PUT`

**Description:** Update details of an existing tune.

**Request Body:**

```json
{
  "song_title": "string",
  "lyric_writer": "string",
  "music_writer": "string",
  "link": "string"
}
```

**Response:**

- **200 OK:** Tune successfully updated.
- **400 Bad Request:** Invalid input data.
- **404 Not Found:** Tune not found.

### Update a Note

**Endpoint:** `/api/v1/notes/{id}`

**Method:** `PUT`

**Description:** Update details of an existing note.

**Request Body:**

```json
{
  "note_name": "string",
  "version": "string",
  "tune_id": "integer"
}
```

**Response:**

- **200 OK:** Note successfully updated.
- **400 Bad Request:** Invalid input data.
- **404 Not Found:** Note not found.

## Delete

### Delete a Tune

**Endpoint:** `/api/v1/tunes/{id}`

**Method:** `DELETE`

**Description:** Delete a specific tune by ID.

**Response:**

- **204 No Content:** Tune successfully deleted.
- **404 Not Found:** Tune not found.

### Delete a Note

**Endpoint:** `/api/v1/notes/{id}`

**Method:** `DELETE`

**Description:** Delete a specific note by ID.

**Response:**

- **204 No Content:** Note successfully deleted.
- **404 Not Found:** Note not found.

## Tutorials

### Retrieve a List of Songs and Links

For a step-by-step guide on how to retrieve a list of songs and links using the TunePile API, please refer to our [key tutorial](/tutorials/retrieve-a-list-of-songs-and-links).
