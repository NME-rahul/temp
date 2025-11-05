# DHCP

* The Dynamic Host Configuration Protocol (DHCP) dynamically assigns IP addresses to hosts by leasing them for a specified period. When this lease expires the DHCP server usually renew the IP if available otheriwse assigns a new IP from pool.
* It uses UDP as Transportaion layer protocol.
* Port 67: Used by DHCP server to listen requests
* Port 68: used by client to send message

## Working:

When client first wakeup, to connect with other computers(or internet) it requires an IP, to get this client broadcasts an message() to find, is there any DHCP server is avaialble.

Bradcasts packet contains

    Source IP address: 0.0.0.0
    Destination IP: 255.255.255.255

    Source MAC: own mac address
    Destination MAC: FF:FF:FF:FF:FF:FF


How far this message can be braodcast?
this message will be braodcast in its Local Area Network(not on internet) only, the DHCP must be there in local area netowrk to obtain IP addresses automatically through. YOu can thnk if the DHCP is another LAN then how braodcast packet will cross the router(in LAN, MAC helps to cross switches).


What if there are multiple subnets in the LAN? does any subnet router have a DHCP server?
yes, every subnet router can have a seprate DHCP server but this is avoided mostly, instead there is one single DHCP server is there to serve all clients and each subnet routers acts as DHCP relay agents that performs the following setps:
1. `DHCP Client`: it braodcast the request.
2. `DHCP relay agent`: When relay agent(usually subnet router) receives a DHCP request it send the request to the DHCP server on behalf of client.
   * Source IP: own IP(relay agent)
   * Destination IP: DHCP server IP
   * Source MAC: own MAC(relay agent)
   * Destination MAC: DHCP server MAC
3. `DHCP server`: selects an IP address from the IP pool and sends back a "DHCP Offer" message, again as a unicast(or broadcast) to the relay agent. 
4. `DHCP relay agent`: the relay agent recieves the offer and forward it to client(it can be broadcast or unicast).
5. `DHCP Client`: On receving an offer from DCHP server it selects the offer from all(the DHCP clients usaully selcts the offer that gives the longest lease time), Then DHCP client braodcasts the request to the selected DHCP server from available offers.
6. `DHCP relay agent`: The relay agents recieves the DHCP client request packet that specifes DHCP server from which to obtain configuration information and sends this request packet to each of the DHCP servers.
7. `DHCP server(specified in the request)`: The DHCP server requested by the client sends an acknowledgement(ACK) packet that contains the client’s configuration parameters.
8. `DHCP relay agent`: agent receves the packet with confguartion paramters and forward it to the client.
9. `DHCP client`: The DHCP client receives the ACK packet and stores the configuration information and configure itself.

<a align="center">
<img width="1015" height="565" alt="image" src="https://github.com/user-attachments/assets/00aae1b9-ecd2-4161-9e87-aa68a8fe2de5" />
</a>
