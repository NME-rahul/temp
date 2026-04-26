# DNS
* It translates human-readable domain name to associated IP address of the machine hosting particular service.
  * Why translation needed? because to access the machine over internet requires address(IP address) of that machine and it is 4/16 byte integer number.

* DNS works on the `UDP` protocol of TCP layer and uses `port 53`.
* But for Zone transfer it used TCP protocol and port 53.


## Servers invloving:

There are 4 Servers involved in resolve DNS query

### 1. DNS recusor
* The clinet sent a recursive query to find the IP of a particular domain meaning client want final answer.
* now, Its upto DNS recursor which method it uses either recusive or iterative to talk with rest of the server.
* DNS recursor also uses caching to give answer faster.
* Popular DNS recursors are: google DNS server 8:8:8:8 or 8:8:4:4, cloudflare 1:1:1:1

### 2. Root server
* root server does not hold any translation it only have IP address of Top level domain.
* when a DNS recursor asks to root server it only give IP address of the Top-Level domain DNS server for the IP, for example DNS recursor asks IP for domain "google.com" then it will only give IP address of the DNS server having all domain related to "com".

### 3. TLD server
* It consists of IP address of autoritative server that contains the IP address of the machine related domain.
  
### 4. Authoritative server
* Now autoritateive servers resolves the IP address of corresponding domain.

<div></div>

## Working

* DNS works on distributed database system, meaning there are not only one root, TLD and authoritative server.
* in DNS, a domain name name is resolved in the reverse fashion
  * for example: "gmail.google.com." is a fully qualified domain name(FQDN).
  * first dot for root, .com for TLD server, and google for authoritative server.
  * "gmail" can be thought of as department under the google and IP address is not other then the "google.com", the department provides serveice throught the domain name "google.com"(can e different in some cases).

<div></div>

<div align="center">
  
|Iterative|Recursive|
|---|---|
|<img width="400" height="150" alt="DNS-SERVER" src="https://github.com/user-attachments/assets/b14f9b64-db25-4ae9-ae07-03f28a982687" />|<img width="300" height="260" alt="00S6Q" src="https://github.com/user-attachments/assets/c150b370-b85c-4e4b-ab7f-2027c3951d25" />|
</div>


## Zone Trnasfer

### What is zone?
* DNS is broken into managable pieces, a DNS zone is a portion of the DNS namespace that is managed by a specific orgnaization or administrator.
<div align="center">
  <img width="1503" height="1000" alt="image" src="https://github.com/user-attachments/assets/a5e3e444-d283-45d2-9496-0a5e60811609" />
</div>

* A single zone have two or multiple servers for providing fault tolerance.
* A DNS zone transfer is the porcess of replicating DNS records from primary DNS server to a secondary server. This enures synchronization, provide tolerance and blances load, as the secondary server can resolve DNS query if primary fails.
  
