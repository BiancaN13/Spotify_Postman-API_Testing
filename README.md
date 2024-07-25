# Spotify-API Testing

Welcome to the Spotify API Testing in Postman project! This repository is dedicated to testing various endpoints of the Spotify Web API using Postman. This project includes pre-configured requests, environment setups, and automated tests to ensure the Spotify API works as expected. The aim is to facilitate understanding and integration of Spotify's extensive music data in your applications.
## Introduction
Spotify Web API enables the creation of applications that can interact with Spotify's streaming service, such as retrieving content metadata, getting recommendations, creating and managing playlists, or controlling playback.

The Spotify Web API provides a wide range of functionality for developers, including:

- Retrieve data from your favourite artist, album, or show.
- Search for Spotify content.
- Control and interact with the playback: play and resume, seek to a position, or retrieve your queue.
- Manage your personal library by creating a new playlist and adding your favourite tracks to it.
- Get recommendations based on the music you listen to the most.
- And much more! You can find a complete list of available endpoints in the API Reference.
## Getting Started with Spotify Web API - Authorization (OAuth 2.0)
To access Spotify's resources or user data, you'll need an access token containing the credentials and permissions required.
## 1. Create a Spotify Developer Account

1. **Sign up:** Create a new Spotify account if you don’t have one.
2. **Login:** Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/).
## 2. Register Your Application

1. **Create an app:**
   - Click on **Create an App**.

2. **Enter details:**
   - **App Name:** e.g., My App
   - **App Description:** e.g., API testing
   - **Redirect URL:** e.g., `https://oauth.pstmn.io/v1/browser-callback`
   - Agree to the **Developer Terms of Service**.
   - Click **Create**.
3. **Get Client ID and Client Secret:**
   - Go to the Dashboard.
   - Click on the app you created.
   - Click on **Settings** to find your **Client ID** and **Client Secret**.

## 3. Set Up Your Spotify API Environment

1. **Create a New Environment:**
   - Create a new environment.
   - Add the following variables to the environment:
     - **Client ID**: Your Spotify Client ID
     - **Client Secret**: Your Spotify Client Secret
   - Make them variables.


2. **Create a Collection:**
   - Create a new collection in your API client named **Spotify API**.

3. **Configure OAuth 2.0 Authorization:**
   - Within the **Spotify API** collection, set up a new request to handle OAuth 2.0 authorization.
   - **Access Token URL:** `https://accounts.spotify.com/api/token`
   - **Authorization URL:** `https://accounts.spotify.com/authorize`
   - **Callback URL:** The URL you used when creating your app, e.g., `https://oauth.pstmn.io/v1/browser-callback`
   - **Client ID:** `your-client-id`
   - **Client Secret:** `your-client-secret`
   - **Scope:** `playlist-modify-public playlist-read-private playlist-modify-private user-read-playback-state playlist-read-collaborative user-library-modify user-library-read`

4. **Obtain Access Token:**
   - Use the **Spotify API** collection to request and manage access tokens. The token will be valid for 60 minutes.

## Types of requests

The Spotify Web API supports various HTTP methods to interact with its resources. Below are the different types of requests you can perform, along with examples of each method:


### 1. GET
**Description:** Retrieves resources from the server. This method is used to request information about artists, albums, playlists, and more.

**Example Usage:**
- **Get Artist Information:** Retrieve detailed information about a specific artist.
  - **Endpoint:** `GET /v1/artists/{id}`
  - **Description:** Returns information about an artist, including their name, popularity, genres, and albums.

### 2. POST
**Description:** Creates new resources on the server. This method is used to add new playlists, add tracks to playlists, and more.

**Example Usage:**
- **Create a Playlist:** Create a new playlist for a user.
  - **Endpoint:** `POST /v1/users/{user_id}/playlists`
  - **Description:** Creates a new playlist in the specified user's account.

### 3. PUT
**Description:** Changes and/or replaces resources or collections. This method is used to update existing data, modify playlists, and more.

**Example Usage:**
- **Update Playlist Details:** Modify the details of an existing playlist.
  - **Endpoint:** `PUT /v1/playlists/{playlist_id}`
  - **Description:** Updates the playlist's name, description, and public status.


### 4. DELETE
**Description:** Deletes resources from the server. This method is used to remove playlists, tracks, and more.

**Example Usage:**
- **Delete a Playlist:** Remove a playlist from a user's account.
  - **Endpoint:** `DELETE /v1/playlists/{playlist_id}`
  - **Description:** Deletes the specified playlist from the user’s account.
 ## Tests perfromed
## 1. Get Current User's Profile

**HTTP Method for Request:** `GET`

**Request Description:** Retrieves Spotify catalog information for a single artist identified by their unique Spotify ID.

**Endpoint:** `GET https://api.spotify.com/v1/artists/{id}`

**Response Status Code:** `200 OK`
### API Request

To get information about a specific artist, send a GET request to the following URL, replacing `{id}` with the artist's Spotify ID:
   
