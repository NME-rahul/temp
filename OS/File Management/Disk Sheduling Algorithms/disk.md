* The number of actuaters(R/W head) or platters is nothing with the speed but actually to increase the storage space, multiple platters just provide more capcaity and actuators are just to read/write on correspoonding platters. Only one actuator works at a time, reducing only the seek time and not rotational latency and tansfer time by overlapping time.
* Data in the hard disk is first stored sectors wise in same track then cylinderwise thus reducing the seek time.
  * First fill all sectors in same track,
  * Then fill the second track on the same cylinder(i.e. the first track of second surface),
  * after filling all tracks of a cylinder start the process from first sector of first track of second cylider of first surface and so on..
* By default track start from 0 and the outermost track is called track 0. The highest number track is nearest to the spindle.
* Address are given to the sectors(smallest unit of disk).

* Seek Time: Time to put R/W head on desired track.
* Rotational latency: Time to reach at the starting byte of scector of the track.
* Transfer time: Time to transfer data = time move head on the desired contnious sectors.

**Tip:**
* If avaerage latency seek time is not given then first count the average number of tracks(starting from 0 to n-1) for eg. $0 + 1 + 2 + ... + n-1 = \frac{n(n-1)}{2n}$ here, divided by n to find average.
* Now multiply the given head movement time to find average seek time.


### Addressing 

1. LBA : counting start from 0th sector of the 0th cylidener and first go sectors wise in same track then another track of same cylidner i.e. as the data is stored in sectors.
2. <C, H, S> (cylindere, surface, sector)

<img width="1197" height="582" alt="image" src="https://github.com/user-attachments/assets/010a6c05-4276-4d1f-9e9a-898960a57e86" />
