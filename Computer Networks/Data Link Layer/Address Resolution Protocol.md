# Address Resolution Protocol

At anytime the sender node have the ip address of the destination host, but to move to frame in link we need link address(MAC). To get to know the link address the soruce boradcasts the ARP request packet. The packet includes the MAC and IP address of sender and the IP address of the reciever. Every router and host on the network recieves the ARP request packet, but the only intended recipient recignizes its IP address and send back ARP response packet. The respnse packet is the uncast directly to the node that sent request packet.
