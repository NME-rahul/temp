# Direct Memory Access

* Without DMA, CPU requires to involve in data transfer that is not efficient for a CPU, with DMA, CPU only involved at time of intialization, after then it does other operation while the transfer is in progress, and it finally recieves an interrut from the DMA controller(DMAX) when the data transfer is done.

#### Sequence of operations:
1. When the processor wants to transfer data, it issues a commant to DMA controller & intialize the DMA module by sending the following information to DMA module.
   1. Address of the I/O devide
   2. Starting location of the memory to write/read.
   3. The number of words to be read/write.
2. After initializing DMA module, the processor continue wih other work.
3. When I/o Deice is ready for transfer, the IO device informs the DMA module.
4. Now the DMA module need ti use the system buses to ansfer data. so it sends a signal caled HOLD(or BUS request) to processor.
5. DMA waits tiil he next DMA breakpoint then CPU reqlinquish control of the system BUS and responds with DMA-ACK or HLDA(hold acknowledgement) signal to DMA module, indicating that the DMA module can use the bus.
6. The DMA modules transfer the data, one word at a time, directly from memory without going through the processor.
7. After the DMA has finished its job it will deactivathe HRQ(DMA-RQ), signaling the  that it can regain control over its bus.
8. When the transfer is complete the DMA module sends an interupt a signal to the processor.


### 1. Brust Mode:

* A brust of data is transfered between memory and IO before CPU takes control of the bus again.

### 2. Cycle stealing:(Data is prepared before requesting)

* Slow IO device takes time to prepare data to be transfered. During this time CPU keeps control of the bus. Whenever the word or byte is ready then CPU gives the control of the buses to the DMA contoller to one memory cycle. During this cycle the data is transfered between memory and IO.

### 3. Interleaving mode:(leave control bus when CPU not needed it)

* Whenever CPU performs internal operations and does not require the buses then DMA contoller will be given the control of the buses. Hence CPU will be never blocked.

---

### # % Time CPU is blocked

let,

Time required to prepare the data in IO = tx

Time required to transfer the data to memory = ty

* % time CPU is blocked in brust mode

$$  \frac{ty}{tx + ty} * 100$$

* % time CPU is blocked in cycle stealing mode
* total time = Time required to prepare the data in IO
  
  $$\frac{t_y}{t_x} * 100$$

* % time CPU is blocked in interleaving mode is 0

### # Time CPU is blocked

* total time in brust mode = Time required to prepare the data in IO + Time required to prepare the data in IO
* total time in cycle stealing mode = Time require to transfer the data
* total time in interleaving mode = 0
