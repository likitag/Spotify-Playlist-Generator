Original App Design Project - README Template
===

# Spotify Playlist Generator


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
- **Mobile: This app is suited for Mobile use since it generates playlists for users based on few of their preferences.
- **Story: Music plays such an important role in our lives, but with everyone's busy schedules, it can be difficult to find the time to create playlists and discover new music. With this app you can easily and quickly create and discover new playlists customized for you. 
- **Market: This app would be targeted towards music listeners, specifically spotify users. 
- **Habit: Users would open this app everytime they are in need for a new playlist to listen to, or if they want to see what their friends are listening to. 
- **Scope: This application would have the core feature of generating playlists based on a specified time duration and specified preferences of genres/artists. Since we can utilize the Spotify API, this would be doable in the duration of this program. 

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* Users are able to login/sign-up/logout from the application
* Users are able to enter desired time length and genre/artist preferences for their customized playlist
* Users are able to see other user's playlists
* Users can edit/delete playlists


**Optional Nice-to-have Stories**

* Users have a feed that shows what playlists their friends are listening to 
* Users can leave react emojis to feed items
* Users can categorize their playlists 
* Calendar feature that shows most listened to song/artist each day (if spotify allows you to access this information)


### 2. Screen Archetypes

* Log in Screen
    * Users are able to login using spotify authentication
* Dashboard screen
    * Users can view their custom made playlists

* Create Playlist Screen 
    * Users can enter time length and genre preferences for their customized playlists

* Generating playlist screen

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Dashboard Screen 
* Create Playlist Screen 

**Flow Navigation** (Screen to Screen)

* Dashboard Screen
   * See different categories of playlists
   * View the playlists in each of these categories
   * View user information (number of playlists created, profile info)
* Create playlist Screen
   * Enter information for customized playlist creation
   

## Wireframes
[Add picture of your hand sketched wireframes in this section]
<img src="YOUR_WIREFRAME_IMAGE_URL" width=600>



### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
[This section will be completed in Unit 9]


### Models
[Add table of models]
Playlist


| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique id for the user's playlist (default)     |
| author   | Pointer to User    | playlist author     |
| createdAt   | DateTime    | date when playlist is created (default field)     |
| Song List  | List | List of Song objects      |
| Category  | Pointer to Category | category of thr playlist    |

Song
| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique id for the song (default)     |
| artist   | String    | artist of song     |
| duration   | DateTime    | time length of song     |
| Genre | String | Genre of music      |

Category
| Property | Type | Description |
| -------- | -------- | -------- |
| objectId    | String     | unique id for the category (default)     |
| title  | String    | category of title     |
| image   | File   | image for the category     |
| playlists  | Integer   | number of playlists    |







### Networking
- [Add list of network requests by screen ]
- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp]
