# Websockets-chat-app
Websockets using nodejs

**To run the POC**:
1) >npm install
2) >npm run dev (provided nodemon is installed on system), else do >npm run start
3) Open multiple browsers on localhost:3000
4) Connect to different chat rooms with different users, and start sending messages over websockets.


**Libraries used in the POC**
1. socket.io for websokcets. Included on both server as well as the UI (see chat.html) side.
2. Mustache for rendering the UI.
3. Filter for blocking out profane text at client side itself (eg. try sending 'hell' as the chat text) 
4. Moment.js: for formatting the epoch timstamp shared between server and client.
5. qs.js: 
6. 

