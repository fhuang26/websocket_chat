## websocket_chat
* This app provides an online chat room, by using WebSocket, Spring Boot, Java, JavaScript, Maven, and IntelliJ. A user can enter the online chat room anytime and chat with other people currently online. Please see "chatting online" for a recording (1 min).

* We can do "localhost:8080" or "http://localhost:8080/chat?username=David" on a browser to start.

* username is not available in Java onOpen(). So when a new user David enters the chat room, the first message "David: online" is requested in JavaScript getWebSocket() in chat.html on client side, processed in Java onMessage() in server with message.type ENTER, and then distributed to all online users.

* onlineCount is assigned on the server side and is distributed to all current clients.

* login.html takes a username and redirects to the chat page.

* In chat.html, a username is obtained from query in href of window.

* When a user clicks CLOSE or [x] of a browser tab to leave the chat room, it will show a message like "David: offline" to rest online clients.

* It takes some time (< 1 sec) for WebSocket to set up and reach a ready state to process messages. In chat.html, setTimeout() with 1.4 sec is used to hold for WebSocket to reach a stable state and then send the first message "David: online".

* During development on Java side, I turned on Run > Edit Config > Maven > 'Show console when a message is printed to standard output stream' to trace object flow on server and fix a few bugs.
