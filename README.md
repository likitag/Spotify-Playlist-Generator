Original App Design Project - README Template
===

# Spotify Playlist Recommender


## Table of Contents
1. [Overview](#Overviccew)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
Users can enter their musical preferences as well as a desired playlist time duration, and this application will create a spotify playlist customized for the user's needs. 
### App Evaluation
- **Category: Music/Social
- **Mobile: This app is suited for Mobile use since it creates playlist recommendations for users based on a few of their preferences, and their time constraints.
- **Story: Music plays such an important role in our lives, but with everyone's busy schedules, it can be difficult to find the time to create playlists and discover new music. With this app you can easily and quickly create and discover new playlists customized for you. 
- **Market: This app would be targeted towards music listeners, specifically spotify users. 
- **Habit: Users would open this app everytime they are in need for new playlists to listen to. 
- **Scope: This application would have the core feature of recommending playlists based on a specified time duration and specified preferences of genres/artists. The user will rate this playlist, and based on this rating, app will give more playlist recommendations. Since we can utilize the Spotify API, this would be doable in the duration of this program. 

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* Users are able to login/sign-up/logout to the application through spotify authorization 
* Users are able to enter desired time length and genre/artist preferences for playlist recommendations. 
* users can save playlists that they like. 
* Users can rate their playlist.



**Optional Nice-to-have Stories**

* More options of playlist ratings (ex. 5 stars)
* users can share playlists that they like 


### 2. Screen Archetypes

* Log in Screen
    * Users are able to login using spotify authentication
* Dashboard screen
    * Users can view their saved playlists 
    * Uses can view their top favorite artists and songs

* Recommend Playlist Screen 
    * Users can enter time length and genre preferences for their customized playlist recommendation

* Generating playlist screen
* Rating Screen 
   * Users can rate this recommended playlist 

* suggestions screen 
   * Based on the user's playlist rating, recommend other playlists.  



### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Profile Screen 
* Recommend Playlist Screen

**Flow Navigation** (Screen to Screen)

* Dashboard Screen
   * View user information (number of playlists created, profile info)
   * View users favorite artists and songs 
   * View users saved playlists 
* Recommend playlist Screen
   * Enter information for customized playlist recommendation 
   * Rating Screen 
      * like / dislike screen 
      * If selected like: 
         * Select favorite song 
         * Redirect to new playlist recommendations
      * If selected dislike: 
         * Select least favorite song  
         * Redirect to new playlist recommendations 
   

## Wireframes
[Add picture of your hand sketched wireframes in this section]



![Wire Frames](https://github.com/likitag/Spotify-Playlist-Generator/blob/18a92d9dff94667f862e3538e321f6f10f21051c/Wire%20frames%20.png)

### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
[This section will be completed in Unit 9]


### Models
[Add table of models]

Playlist
| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique Parse id for the user's playlist (default)    |
| playlistId | String | Spotify playlist Id |
| author   | String   | holds the object Id of the user that created this playlist   |
| createdAt   | DateTime    | date when playlist is created (default field)     |
| Spotify recommended List | JSON Array  | holds all the spotify id's for the set of recommended songs |
| Song List  | JSON Array | holds all the ids of the selected songs for this playlist  |
| Desired Length | Integer | user input of desired playlist time length |
| Rating | Integer | Rating that the user gives the playlist |
| Top song | Song | user selects their favorite song from the playlist |
| Worst song | Song | user selects least favorite song from playlist |

Song
| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique Parse id for the song (default) |
| trackId | String | spotify id for the specified track |
| artist   | String    | spotify id of artist of the song    |
| duration   | Integer    | time length of song     |
| Genre | String | Genre of music from available spotify genres |


User
| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique Parse id for the user(default)     |
| username | String    | username for account    |
| password   | String  | user's account password    |
| email  | String   | email associated with user |
| profile image  | File   | Parse File for the users profile picture |
| favorite artists  | JSON Array  | holds all the Spotify ID's associated with the user's favorite artists  |
| favorite genres  | JSON Array  | holds all the user's favorite genres (from the list of spotify genres)  |
| favorite tracks  | JSON Array  | holds all the Spotify ID's associated with the user's favorite tracks |




### Networking
- [Add list of network requests by screen ]
- GET /reccomendations: 
   -  Query: up to 5 seed artists, up to 5 seed genres, up to 5 seed tracks, limit (target size of of the list of recommended tracks)
   -spotifyApi.getRecommendations().limit(...).seed_artists("...").seed_genres("...").seed_tracks("...").build();

- POST /user /user_id/ playlist 
   - creates a playlist. Null until items are added to playlist 
   - spotifyApi.createPlaylist(userId, name).collaborative(false).public_(false).description(...).build();

- POST / playlists / playlist_id / tracks
   - add items to playlist

- GET / reccomendations / available-genre-seeds
   - retrieves a list of available genre seeds that users can select from  

## Playlist recommendation algorithm ideas 
   - Use the users playlist rating, favorite song, and least favorite song to generate playlist recommendations 
   - Get the genre, artist,  

- [Create basic snippets for each Parse network request] 
- [OPTIONAL: List endpoints if using existing API such as Yelp]
