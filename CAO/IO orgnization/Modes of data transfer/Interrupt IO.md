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

**Working**

* When no interrupt are pending, the interrupt line stays in the high-level state and enables the intrrupt input lines.
* Device place the inttrupt signal and places the interrupt line in the low state, menas now no device can place interrupt signal on line.
* The CPU acknowledges the interrupt request throught intrrupt acknowledgment line in repsone to request.
* The signal is recieved at PI input of first device on line.
* If device has no interrupt, it passes the signal to the next ddevice throgh it PO(PI=1 & PO=1).
* However, if device had requested the interrupt then device consumes the acknowledgmentsignal and block its further use by placing 0 at it's PO.
* The device then proceed to place its interrupt vector address(VAD) into the data bus of CPU.
* The device puts its interrupt signal in HIGH state to indicate its intrrupt has been taken care of.

