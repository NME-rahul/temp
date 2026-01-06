# WireSpeed Forwarding.md

*  Wire Speed forwarding means a network devices(like a switch or router) forwards data packets at the maximum possible speed of the physical connection, without internal bottlenecks, ensuring data flow at its therotical limit.

**FOR EXAMPLE**
A Router has two full duplex Ethernet each operating at $100 mb/s$. Ethernet frames are at least $84$ Bytes long(including the preamble and the inter-packet-gap). The maximum packet processing time at the router wirespeed forwarding to be possible(in $\mu s$)?

There Two Full duplex interface total speed $\Rightarrow 200 mb/s$
needs to send $84$ Bytes, so total theoritical speed possible is $\frac{84 * 8}{200 * 10^6} = 3.3 \mu s$
