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

**Request Description:** Retrieves information about the current Spotify user's profile, including their display name, number of followers, and profile image (if available).

**Endpoint:** `GET https://api.spotify.com/v1/me`

**Response Status Code:** `200 OK`
### API Request and Response

To retrieve the current user's profile information, send a GET request:
![getcurrentusersprofile](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/getusersprofile.PNG)
### JavaScript Tests
![testgetusersprofile](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/testgetuserprofile.PNG)
![responsegetusersprofile](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/responsegetusersprofile.PNG)
## 2. Save Album for Current User

**HTTP Method for Request:** `PUT`

**Request Description:** Save one or more albums to the current user's 'Your Music' library.

**Endpoint:** `PUT https://api.spotify.com/v1/me/albums`

**Response Status Code:** `200 OK`

### API Request and Response
To save one or more albums to the current user's library, send a `PUT` request:
![savealbum](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/savealbum.PNG)
### JavaScript Tests
![savealbumtest](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/savealbumtest.PNG)
## 3. Get User's Saved Albums

**HTTP Method for Request:** `GET`

**Request Description:** Retrieves a list of albums saved in the current Spotify user's 'Your Music' library.

**Endpoint:** `GET https://api.spotify.com/v1/me/albums`

**Response Status Code:** `200 OK`

### API Request and Response
To get a list of saved albums for the current user, send a `GET` request:
![getuserssavedalbums](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/getuserssavedalbum.PNG)
### JavaScript Tests
![getuserssavedalbumstest](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/getuserssavedalbumtest.PNG)
![getuserssavedalbumsresponse](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/getuserssavedalbumresponse.PNG)
## 4. Delete User's Saved Album

**HTTP Method for Request:** `DELETE`

**Request Description:** Remove one or more albums from the current user's 'Your Music' library.

**Endpoint:** `DELETE https://api.spotify.com/v1/me/albums`

**Response Status Code:** `200 OK`

### API Request and Response

To remove one or more albums from the current user's library, send a `DELETE` request:
![deleteuserssavedalbum](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/deleteuserssavedalbum.PNG)
### JavaScript Tests
![deleteuserssavedalbumtests](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/deleteuserssavedalbumtests.PNG)
## 5. Create Playlist

**HTTP Method for Request:** `POST`

**Request Description:** Create a new playlist for a Spotify user. The playlist will be empty initially and will need tracks added to it separately. Each user is generally limited to a maximum of 11,000 playlists.

**Endpoint:** `POST https://api.spotify.com/v1/users/{user_id}/playlists`

**Response Status Code:** `201 Created`

### API Request and Response

To create a new playlist for a user, send a `POST` request:
![createplaylist](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/createplaylist.PNG)
### JavaScript Tests
![createplaylisttests](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/createplaylisttests.PNG)
![createplaylistresponse](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/createplaylistresponse.PNG)
## 6. Add Songs to Playlist

**HTTP Method for Request:** `POST`

**Request Description:** Add one or more tracks to an existing playlist for a Spotify user. 

**Endpoint:** `POST https://api.spotify.com/v1/playlists/{playlist_id}/tracks`

**Response Status Code:** `201 Created`

### API Request and Response

To add tracks to a playlist, send a `POST` request
![addsongstoplaylist](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/addsongstoplaylist.PNG)
### JavaScript Tests
![addsongstoplaylisttests](https://github.com/BiancaN13/Spotify_Postman-API_Testing/blob/main/addsongstoplaylisttests.PNG)
## 7. Get Current User's Playlists

**HTTP Method for Request:** `GET`

**Request Description:** Retrieve a list of playlists owned or followed by the current Spotify user.

**Endpoint:** `GET https://api.spotify.com/v1/me/playlists`

**Response Status Code:** `200 OK`

### API Request and Response

To get a list of the current user's playlists, send a `GET` request:

### JavaScript Tests

## 8. Change Playlist Details

**HTTP Method for Request:** `PUT`

**Request Description:** Update the details of an existing Spotify playlist. You can change the playlist's name, description, and visibility (public/private).

**Endpoint:** `PUT https://api.spotify.com/v1/playlists/{playlist_id}`

**Response Status Code:** `200 OK`

### API Request and Response

To update the details of a playlist, send a `PUT` request:

### JavaScript Tests

## 9. Get Artist

**HTTP Method for Request:** `GET`

**Request Description:** Retrieve Spotify catalog information for a single artist identified by their unique Spotify ID.

**Endpoint:** `GET https://api.spotify.com/v1/artists/{id}`

**Response Status Code:** `200 OK`

### API Request and Response

To get information about a specific artist, send a `GET` request:

### JavaScript Tests

## 10. Get New Releases

**HTTP Method for Request:** `GET`

**Request Description:** Retrieve a list of new album releases on Spotify. This endpoint provides information about newly released albums.

**Endpoint:** `GET https://api.spotify.com/v1/browse/new-releases`

**Response Status Code:** `200 OK`

### API Request and Response

To get a list of new releases, send a `GET` request:

### JavaScript Tests






   
