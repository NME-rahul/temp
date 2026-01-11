# HTTP

* The server uses the por number 80
* HTTP uses the services of TCP.
* Stateless protocol: no User information is stored(but Server stores Cookie in host computerto know to identify its previous users).
* Connectionless Protocol: After making TCP connection with server every HTPP request is independent, meaning for transport layer it will always be conection-oriented and statefull but for application layer, no session is maintained and for devlivery it relies on underlying TCP.

**Two Versions**
1. HTTP 1.0(Non Persistent connection): For every object of every web-page there will be one seprate TCP connection to get it.
2. HTTP 1.1(Persistent connection): There is only one TCP connection for every web-page including all it's objects.

