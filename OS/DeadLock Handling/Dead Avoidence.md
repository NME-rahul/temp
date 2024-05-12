# Deadlock Avoidence

* This stratergy invoves maintaing a set of data using which a decision is made whether to entertain the request or not.
* If entretaining the new request causses the system to move in an unsafe state, then it is discarderd otherwise not.
* This starergy requires that every process declares it maxmum requirenment of each resources type in the begining.
* The main chhenge with this appraoch is predicting the requirment of the process before execution.
* Banker's algorithm is an example of a deadlock avoidance stratergy.
