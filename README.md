Group-Chat-Application
======================

Group Chat Application

What is it?
•	Simple group chatting app
•	Communication between different clients (web-web, web-android, or android-android)
•	Similar to Whatsapp, Viber, Wechat

How will it be built?
•	Using network sockets
•	Programmed using Java, JavaScript, HTML, and CSS
•	Using Eclipse IDE with J2EE and Tomcat server support

What is sockets?
•	A method of communication flow between a client program and a server program
•	Defined as the endpoint in a connection

How are we going to use sockets?	
•	Android and web apps will connect to the socket server
•	A TCP connection will open between server and client 
•	JSON strings exchanged between server and client 
•	Each JSON string contains a node (called a flag) that identifies the purpose of the JSON message

What is a TCP (transmission control protocol)?
•	A standard that defines how to establish and maintain a network conversation 

What is a JSON string (Java Script Object Notation)?
•	A more compact way of transmitting sets of data across network connections

What is a node?
•	A basic unit in computer science
•	Are devices or data points on a larger network 
•	On the internet, nodes are anything with an IP address 

How to build the socket server?
•	Creating dynamic web project on Eclipse 
•	JSONutils.java is a class that contains methods to generate JSON strings that are required to communicate with socket server and clients
•	Each JSON contains one out of the four possible flag node which tells clients the purpose of the JSON message
•	Actual server is implemented in SocketServer.java where there are four callback methods

What are the four flag node values in JSON messages?
•	Self – Contains session information on particular client
•	New – Broadcasted to every client informing about the new client that is connected to the socket server
•	Message – Contains message sent by a client to server 
•	Exit – Informs every client that the client is disconnected from the socket server

What are the four callback functions?
•	onOpen()– Called when a new socket client connects
•	onMessage()– Called when a new message is received from the client 
•	onClose()– Called when a socket client is disconnected from the server
•	sendMessageToAll()– Used to broadcast a message to all socket clients

How is the web app built?
•	Using HTML, CSS, and JQuery 
•	Adding stlye.css, main.js, and index.html to the same socket server project

What does the style.css file do?
•	Contain styles for the web app UI

What does the main.js file do?
•	Contains functions that handles communication between the socket server and the client 
•	Parses JSON messages

What does the index.html file do?
•	Defines the content for the webpage of the app

How will the android chat application be made? 
•	New android application project on eclipse IDE

How to change the app’s appearance?
•	Added colors.xml, strings.xml, and styles.xml
•	Adding background image and tile_bg.xml, bg_msg_from.xml, and bg_msg_you.xml

What does each class do?
•	Utils.java contains functions to save user’s session ID (cookie)
•	Message.java contains the message ID and where to align the message in the chat box

What do the functions in the main activity (MainActivity.java) class do?
•	Functions onConnect(), onMessage(), and onDisconnect(), creates a web socket using the WebSocketClient 
•	parseMessage() is calle dto parse (turn one type of data into another) the JSON string received from the socket server and the purpose of the JSON string is read 
•	adapter.notifyDataSetChanged() is called to update chat list
•	sendMessageToServer() send message from android device to socket server
•	playBeep() is called to play device’s notification sound whenever new message is received 


