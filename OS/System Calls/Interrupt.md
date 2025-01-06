# Interrupt

* An interrupt is signal emitted by a hardware or sfotware when a process or an event needs immediate attention.
* In I/O devices, one of the bus control line is dedicated for this purpose and is called the Interrupt Service Routine(ISR).
* When a device raises an interrupt, the processor first completes the current instruction. Then the interrupted process PCB is stored to continue the process.
* in I/O device one of the bus control lines is dedicated for this purpose and is called the Interrupt Service Routine(ISR).

## Typess of Intrrupt

Event-relaated software or hardware can trigger the issuance of interrupt signals.
1. Software Interrupts
   1. System calls
   2. Exceptions
2. Hardware Interrupts(in COA)
   1. Maskable Interrupts
   2. non-maksbale Interrupts


### 1. Software Interrupts

It is produced by software or system as opposes to hardware. These are generally made by the system calls whenever any process needs a service for os for eg. fork(), division by zero etc.

a particular instruction known as "interrupt instruction" is used to create software interrupts. we the interrupt instruction is used the processor stops what it is doing and  switches over a particular interrupt handler code. The interrupt hnadler routie complete the required work or handles anyy erors before handling back control to the iterrupted application.



 

 
