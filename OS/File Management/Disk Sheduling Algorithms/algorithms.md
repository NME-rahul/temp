## 1. FCFS(First Come First Serve)

It is simplest disk sheduling algorithm, that serves the access requrests in the order they came.


## 2. SSTF(Shortest Seek Time First)

In SSTF, requests having the shortest seek time are executed first, so the seek time of every request is needed to calculate in advance. It have high reposne time because it favours low seek time request's


## 3. SCAN/ELEVATOR

In the SCAN, the disk arm moves in particulare direction and service the request coming in its ath and after reaching the end of disk, it reverse the direction and again service the request arriving in its path. So this algorithm works as an elevator algorithm


## 4. C-SCAN

In SCAN, the disk arm again scans the path that has been scanned, after reversing its direction. but this situation is avoided in C-SCAN it doesn't scan the already serviced path, and directly goes to the other end of disk and start scanning the disk again.


## 5. LOOK

It is the same as SCAN, despite in SCAN algorithm the disk arm goes to the end of disk tracks and then reverses, in LOOK algorithm the disk arm only moves to the last request and the reverses thus saving the extra delay. 


## 6. C-LOOK

As LOOK is similar to SCAN, in the same way C-LOOK is similar to the C-SCAN. In C-LOOK the disk arm in spite of going to the end goes only to the last request and then from ther goes o the other end's last request. Thus, it also prevents the extra delay occured due to unnecessary traversal to te end of the disk.
