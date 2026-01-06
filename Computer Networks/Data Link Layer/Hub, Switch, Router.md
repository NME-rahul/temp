# Hub
* A Hub is essentially a multiport router, that also regenerates week signals to prevent from attanuation.
* A hub is dumb device it just connects the device and whatever packets it receices it broadcasts to every connected to it.
* It works on physical layer of OSI model.

<div align="center">
  
<video src="https://github.com/user-attachments/assets/473723dd-caef-43c0-98a2-ff455cbb8aaf" /></video>
</div>




# Switch 
* A Switch Keeps record of MAC address and matching ports in its table, and unicast the incoming frames to intended destination.
* A switch works Data Link layer and it can see inside the frames and identify the MAC address.
* the broadcast domain is genrally all the hosts that are connected to it.
  
<div align="center">
<video src="https://github.com/user-attachments/assets/9a06c6ea-efdc-47bf-ace6-a2f343c924a3" /></video>
</div>

# Router
* Routes Data from one network to another network.
* It works on network layer of OSI model can see and manipulate the IP information.
* A router is gateway of network.
 
<div align="center">
  <img width="700" height="400" alt="Screenshot 2026-01-07 at 1 22 58 AM" src="https://github.com/user-attachments/assets/f2b19e1f-f5ba-4f18-bc71-d7fc6640a296" />
  <img width="700" height="400" alt="Screenshot 2026-01-07 at 12 25 04 AM" src="https://github.com/user-attachments/assets/43792f54-0973-4d2a-a3eb-09863fcdd15e" />
</div>


* Routers can also be used to physically diivde the network into subnetwork, that sperates the broadcast domain and routes traffic efficiently.
 
<div align="center">
  <img width="700" height="400" alt="Screenshot 2026-01-07 at 1 23 57 AM" src="https://github.com/user-attachments/assets/4dba1a5a-36e9-43da-8dbb-3393388ca23f" />
</div>

---
* Hubs and switches are used to exchange data within a local area network, Not used to exchange data outside their own network.
* To Exchange data outside their own network, a device needs to be able to real IP address.
* Essentially Hubs and switches are used to create network, whereas routers are used to connect network.
