## **Repertoire using GraphQL-Apollo Client**

- **Notes:**
  This song database was built because i only know the words to few songs and I always forget them anyway. Digging around the internet is too time consuming to do when performing in front of people so I built an app that can store any amount of songs with links their lyrics, all in one place. I used MongoDB for the first time and I think I really liked it. I found the layout to have a learning curve but once I realized what I was looking at, the design of the visualized data is appealing. It is unfortunate that only the first Cluster is free and that I have to keep resetting the IP address but I guess thats not Mongo's fault.
  <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Express, Node and Axios are the main tools used in the backend and React, CSS and some Material-UI thrown in for the front end. I used GraphQL inconjunction with graphQL-tag and the Apollo Client to grab the data from my database. The Apollo-Client seems to have the right amount of flexibility and ease of use in compared to other clients like Relay or Lokka. No wonder graphQL and apollo are becoming inseperable. The Graphical docs were created by Stephen Grinder, using those I was able to create reliable schemas and mutations that can be altered to fit any kind of data for upcoming projects.

* **Website**

  ethans-repertoire.netlify.app

* **Method:**

  <Mutation schemas including the following: 'POST' song, 'POST' lyric to song, 'GET' all songs, 'GET' a song, 'GET' all lyrics of a song, 'DELETE' a song

  `GET` | `POST` | `DELETE`

* **URL Params**

  /#/ - Home
  <br>/#/songs/(id) - Song Page

* **Data Params**
  <br>Song List
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>{"query":"{\n songs {\n id\n title\n \_\_typename\n }\n}\n","operationName":""}

<br>Lyric List
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>{"query":"query SongQuery($id: ID!) {\n song(id: $id) {\n id\n title\n lyrics {\n id\n content\n **typename\n }\n **typename\n  
 }\n}\n","variables":{"id":"60cff8c9308710452443bb4e"},"operationName":"SongQuery"}

- **Success Response:**

  - **Code:** 200 <br />
    **Content:** `{ id : 12 }`

- **Error Response:**

  - **Code:** 404 FILE NOTE FOUND <br />
    **Content:** `{ error : "Not Found" }`
