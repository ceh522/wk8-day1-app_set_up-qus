# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using Vue, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

## MVP

### Task

<!-- contains a db of games, once have run seeds - have the option, when in the browser, for the user to add a game and for this to be pushed into the database
we have the router to give us options to update the details in the forms and then update the database as a result of the change
 -->


Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
<!-- create_router is used to set up restful routes, to be used by the application. This is used in server.js to set up the gamesRouter. -->
2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
<!-- The client handles info on the structure of the app, so the src and the public files, so files that create the structure of the files and mechanisms for emitting and listening for changes.  The server deals primarily with the data, including the database, seed data, the router which corresponds with HTTP request methods.-->
3. What are the the responsibilities of server.js?
<!-- Server.js connects up the server files and brings in the packages that the server needs to function, e.g. mondodb.  It also sets up conditions that other files in the server will need to be aware of, e.g. the games router should take as it's starting point '/api/games'-->
4. What are the responsibilities of the `gamesRouter`?
<!-- Games Router sets out restful routes for the games collection, e.g. providing ways to update, delete, etc.   -->
5. What process does the the client (front-end) use to communicate with the server?
<!-- The app is set up to listen to  what is going on at localhost:3000. The restful routes built into the app allow the frontend of the app to communicate with the backend using HTTP protocols. For this app, the GameService.js file deals directly with ensuring that the returned data works like a json and so can be interpreted and acted on by the app. -->
6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
<!-- postGame(payload){
  return fetch(baseURL, {
    method: 'POST',
    body: JSON.stringify(payload),
    headers: { 'Content-Type': 'application/json'}
  }) this helps with interpretation, so making the payload into something like json, for the app to work with
<!--  -->
7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

<!-- post -->

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
<!-- allows for a two-way interaction between a mongo db database and the front-end, so the seed data can be displayed on the front-end and info can be input by the user that is then persisted to the database.  -->

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?
<!-- to allow us to uniquely identify objects, i.e. pieces of data  -->

Add to your diagram the dataflow for removing a game.
