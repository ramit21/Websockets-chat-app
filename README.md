# Websockets-chat-app
Websockets using nodejs. Websockets are used for real time messaging using persisant connections.

When a user joins a chat room, websocket connection is established with the servers. When the user sends a message to the server, the server then pushes the same message to all other users connected to the same chat room.

**To run the POC**:
1) >npm install
2) >npm run dev (provided nodemon is installed on system), else do >npm run start
3) Open multiple browsers on localhost:3000
4) Connect to different chat rooms with different users, and start sending messages over websockets.

**Libraries used in the POC**
1. **socket.io** for websokcets. Included on server side, and its client side version is included on the UI side (see chat.html)
2. Mustache for rendering the UI.
3. bad-words for blocking out profane text at client side itself (eg. try sending 'hell' as the chat text) 
4. Moment.js: for formatting the epoch timstamp shared between server and client.
5. qs.js: Query string to setup room names, user names etc. 

**Theory**
1. Message can be sent from server or client like this:
```
socket.emit('event',data)
```
This can then be read at the receiver side using the below:
```
socket.on('event', (data) ={   });
```

2. Ways of sending messages:
```
socket.emit()             -> sends message to a specific client
io.emit()                 -> sends message to every connected client
socket.broadcast.emit()   -> sends message to every client except for the current one (from whom the message has been initiated to the server).
```
You can join a specific room using socket.join(room/section). Applicable only on the server side. You can then send messages to clients only inside this room:
```
io.to(room).emit()        -> sends message to every connected client in the given room
socket.broadcast.to(room).emit -> sends message to every connected client in the given room except the current one.
```

3. Browser's geolocation api has been used to get the latitude and longitude coordinates of the client, which when appended to Google map api, forms a link which shows exact location on the map. See app.js for the same.

