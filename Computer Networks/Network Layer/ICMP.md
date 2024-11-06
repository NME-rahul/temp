# Internet Message Control Protocol(ICMP)

* IP is best effort delivery system i.e. it niether have Flow Control not Error Control.
* IP needs Support from ICMP for Flow and error control.
* ICMP can't detect or correct errors, actually it is an error reporting protocol.
* An Network layer Device such as Router or an host ICMP message to source whenever it detects and issue.

<p align="center">
  <img src="https://github.com/user-attachments/assets/98d96375-39e7-40a9-b6a5-2f818e643a0c" />
</p>

* In case of Error, ICMP protocol attaches errornious packet's header with additional 8 bytes(of TCP header) with own ICMP header and sent it to source(sending ICMP error again requires and IP header).

## Categories of Messages

<div align="center">
  
|Categories of ICMP Messages|
|---|
</div>

||Error Reporting Messages|Query Messages|
|----|----|----|
|1.|Destination Unreachable|Echo request and Echo reply(PING)|
|2.| Source Quench: Buffer Full|Time Stamp request and reply|
|3.|Time Exceeded: Time to Leaver becomes 0 before destination|Address mask request and reply|
|4.|Parameter Problem: Header corrupted|Router Solicitation and Advertisement|
|5.|Redirection: Packet doesn't drop but route is not appropriate||
