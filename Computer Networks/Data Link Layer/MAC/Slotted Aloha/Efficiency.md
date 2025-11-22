# Efficiency $\equiv$ Throughput $\equiv$ Probability of slot not wasted

### CASE 1: When Number of stations in network are very large.

* For a large number of stations in network it follows the poisson distributon.

$$P(X = k) = \frac{ e^{-\lambda} \lambda^k }{k!}$$

Where:<br>
* $\lambda$ : Average number of frames transmitted in one tranmission == $G$

* Probability of transmitting k frames in one transmission or slot by? <br>
$P(X = k) = \frac{e^{-G} G^k}{k!}$


* Probability of transmitting 0 frames in one transmission?<br>
$P(X = 0) = e^{-G}$

* Probability of transmitting k frames in one transmission by the whole network?<br>
$P(X = 1) = e^{-G} G$ that is our throuhput formula it means that "Probability of packets per slot"

* Obviosuly in a given slot only one station can tranmist otherwise it will always be a collision so whenever we say "slot is not wasted" meaning only 1 station is transmitting.
* $P(X = 1)$ is the probability of slot not being wasted = throughput (packets/slot)
* you know there is one thing we know $G e^{-G}$ and this is the probability of successful(slot not being wasted) tranmission of frames by the whole network(i.e. 1 station).
* $P(X=0)$ is the probability of transmitting 0 frames or slot being wasted.
* 1 slot = 1 transmission time

### CASE 1: When Number of stations in network are Finite.

* packet size is fixed.
* Each staton transmittes independently with probability $p$.
* Assume, there are n stations.

Packets get successfully tranmitted is only possible when one station tranmittes at a time probability of success is $P_{success} = np(1-p)^{n-1}$

it follows the binomial distribution where $r = 1$, that means probabilty of transmitting packet successfully that is only possible when exactly station transmittes a time.



