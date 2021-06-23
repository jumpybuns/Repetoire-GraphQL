**Repertoire using GraphQL-Apollo Client**
----
  <_Additional information about your API call. Try to use verbs that match both request type (fetching vs modifying) and plurality (one vs multiple)._>

* **Website**

  Ethans-Repertoire.netlify.app

* **Method:**
  
  <Mutation schemas including the following: 'POST' song, 'POST' lyric to song, 'GET' all songs, 'GET' a song, 'GET' all lyrics of a song, 'DELETE' a song

  `GET` | `POST` | `DELETE` 
  
*  **URL Params**

   /#/ - Home
   <br>/#/songs/(id) - Song Page

* **Data Params**
Song List
      {"query":"{\n  songs {\n    id\n    title\n    __typename\n  }\n}\n","operationName":""}

Lyric List
      {"query":"query SongQuery($id: ID!) {\n  song(id: $id) {\n    id\n    title\n    lyrics {\n      id\n      content\n      __typename\n    }\n    __typename\n         
        }\n}\n","variables":{"id":"60cff8c9308710452443bb4e"},"operationName":"SongQuery"}


* **Success Response:**
  
  <_What should the status code be on success and is there any returned data? This is useful when people need to to know what their callbacks should expect!_>

  * **Code:** 200 <br />
    **Content:** `{ id : 12 }`
 
* **Error Response:**

  <_Most endpoints will have many ways they can fail. From unauthorized access, to wrongful parameters etc. All of those should be liste d here. It might seem repetitive, but it helps prevent assumptions from being made where they should be._>

  * **Code:** 404 FILE NOTE FOUND <br />
    **Content:** `{ error : "Not Found" }`

* **Notes:**
  This song database was built because i only know the words to few songs and I always forget them anyway. Digging around the internet is too time consuming to do when performing in front of people so I built an app that can store any amount of songs with links their lyrics, all in one place. I used MongoDB for the first time and I think I really liked it. I found the layout to have a learning curve but once I realized what I was looking at, the design of the visualized data is appealing. It is unfortunate that only the first Cluster is free and that I have to keep resetting the IP address but I guess thats not Mongo's fault. 
<br>  Express, Node and Axios are the main tools used in the backend and React, CSS and some Material-UI thrown in for the front end. I used GraphQL inconjunction with graphQL-tag and the Apollo Client to grab the data from my database. The Apollo-Client seems to have the right amount of flexibility and ease of use in compared to other clients like Relay or Lokka. No wonder graphQL and apollo are becoming inseperable. The Graphical docs were created by Stephen Grinder, using those I was able to create reliable schemas and mutations that can be altered to fit any kind of data for upcoming projects.
  
