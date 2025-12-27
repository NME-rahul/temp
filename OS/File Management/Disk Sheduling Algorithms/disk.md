* The number of actuaters(R/W head) or platters is nothing with the speed but actually to increase the storage space, multiple platters just provide more capcaity and actuators are just to read/write on correspoonding platters. Only one actuator works at a time, reducing only the seek time and not rotational latency and tansfer time by overlapping time.
* Data in the hard disk is stored in disk cylinderwise thus reducing the seek time.

* Seek Time: Time to put R/W head on desired track.
* Rotational latency: Time to reach at the starting byte of scector of the track.
* Transfer time: Time to transfer data = time move head on the desired contnious sectors.

**Tip:**
* If avaerage latency seek time is not given then first count the average number of tracks(starting from 0 to n-1) for eg. $0 + 1 + 2 + ... + n-1 = \frac{n(n-1)}{2n}$ here, divided by n to find average.
* Now multiply the given head movement time to find average seek time.
