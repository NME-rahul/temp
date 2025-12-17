# Interrupt IO

* The device has provision(interrupt signal) to inform to CPU about communication.
* When CPU Recieves interrupt.
  * It completes execution of current instruction.
  * Saves the status of current process on the stack.
  * Branches to service the interrupt.
  * Resume the previous process be taking out the values from stack.
 
* To service the intrrupt, in memory there is samll programm called ISR(Interrupt Service Routine) is executed.
* For every problem in IO there is different ISR, these ISR are installed with device drivers.

**ISR(Interrupt Service Routine)** A routine or function, execution of which service the routine.

**Vector Address**: Starting address of ISR in MM.

||Vectored|Non-Vectored|
|---|---|---|
||Device sends interrupt and vector|Device sends only interrupt|
|working| Device sends the interrupt to CPU and CPU sends acknowledgment to device After recieving acknowledgement the device sends the ISR of Interrupt|The branch address is assigned to a fixed location in memory.|

---

|Maskable Intrrupt|Non-Maskbale Intrrupt|
|---|---|
|CPU can accept or reject the interrupt|CPU Always accepts the interrupt|

---

|External Interrupt|Internal Interrupt|
|---|---|
|IO Generates the intterupt|Interrupt due to unexpected error during instruction execution|
|Due to failure of external hardware|Due to software. eg. page fault, system call|

---

### Time required in interrupt IO

* Time required in interrupt IO = Interrupt overhead time + service time(includes IO speed of transfering data)
  * Interrupt overhead time: context saving + includes time of ACK by CPU + transfer of VAD
* Interrupt overhead time = Intrrupt accepts + device acknowledgment + vector transfer


### Hardware soltion has two types
1. Serial(daisy chaining)
2. parallel

#### 1. Serial(daisy chaining)

* The daisy chaining involves connecting all the devices that can request an interrupt in serial manner.
* The Device with highest priority is placed followed by the second highest priority device and so on.
* Starvation is possible.

<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/ef1cec6e-c581-4aeb-a9de-18e085aa2b68" height="" width="" />
</p>

#### **Working**
<img width="522" height="337" alt="Screenshot 2025-12-17 at 5 10 36 PM" src="https://github.com/user-attachments/assets/05f60e69-ab47-4987-8a02-1bd6cb6cd4b6" />


