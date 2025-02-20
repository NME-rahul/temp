# Data link layer

An internet is a combination of networks glued together by connecting devices. These devices provides provides different functionalties at different level, and every data needs to pass through these essential networks to each at destination. slowly, we will learn about these devices, their working, and some important algorithm that is used in them.

Data link-layer has two sub-layers that is Logical-Link control layer(LLC) and MAC sublayer

## Services of Data-link layer

1. **Framing**: The functionality of the framing is provided by the logical-link sub-layer, in this data from higher-level is encapsulated (like a later in an envelope) in a frame, that gives information about source address and destination address, error detectoion information and length of the frame. on the receiver side this frame is again decapsulated. A packet at data-link layer is usally called frame.

2. **Flow-Control**: Whenever we have producer and consumer we need to think about the about flow control. Here sender is producer and reciever is the consumer and data-link layer needs to ensure that sender does not send more then what recevier can recieve.

3. **Error Control**: A frame in a data-link layer needs to be change the bits into electrmagnatic signals, and transmitted through the transmission media. Electromagnatic signals are susceptible to error, The error needs to be detected and corrected at the receiver side. The problem of error is at layer that needs to be address.

4. **Congestion Control**: A link can be congestd with frames, which may result in frame loss.


