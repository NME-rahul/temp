# FTP(File Transfer Protocol)

* Uses two seprate connection one for Control(port 21) and other for data transfer(port 20).
* Control is use to for sending control information - user identification, password.
* The data connection is used to actually send data.
* The Contorl connection is always open but for every new data file the new TCP connection forms and old one closes.

When a user starts an FTP session with a remote host, the client side of FTP first initiates a control TCP conection with the server side on the derver port number 21. With this the client side of FTP sends identification and other credentials over this connection. also with this the clients shares some control data like file name of control connection. Afte ethe sever sides TCP initiates the TCP data connection to the client side. FTP sends exactly one file over data connection and then closes the data connection. IF during the same session, the user wants to transfer another file, FTP opens another data connection. Thus the FTP control connection remains open throught the duration of user session..
