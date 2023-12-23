# Direct Memory Access

* Data transfer between IO and memory.


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
