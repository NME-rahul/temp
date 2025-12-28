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
2. <C, H, S> (cylindere, surface, Sector)

<img width="1197" height="582" alt="image" src="https://github.com/user-attachments/assets/010a6c05-4276-4d1f-9e9a-898960a57e86" />


LBA $\rightarrow$ <C, H, S>
* Take division with sectors
  * Divide by sectors in 1 cylider
  * reamaning divide by sector in a surface.
  * remaining will be as it is sector value.
* For eg. A disk has $6$ surfaces, $3$ platters, $5$ cylinder, $4$ track/sector and $512$ Byte sector size. Convert sector address $45$ to $<C, H, S>$
  * There $6*4$ sectors in a cylider $\lceil \frac{45}{24}  \rceil = (1, 21)$, there are 4 track per sector $\lceil \frac{21}{4}  \rceil = (5, 1)$ remaining is $1$ sector.
  * $<C, H, S> = <1, 5, 1>$
* similarily  convert address $<2, 3, 1>$ to $LBA$
  * There $6*4$ sectors in cylinders and we've covered $2 * ( 6 * 4) = 48$
  * $4$ sector in a track of a surface and we've coverd $5 * 4 = 20$
  * Remaning is $1$ in sector will be as it is,
  * $LBA = 48 + 20 + 1$
