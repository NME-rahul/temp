# Programmed IO

* There is no provision in programm IO by peripheral device can communicate with CPU.
* To transfer data from IO to CPU, IO devices have their own status bits. Sets status bits whenever there is need of data tranasfer.
* CPU runs a program periodicaly that checks each connected IO device's flag bits sequentially one-by-one.
* If any device has flag bit set then CPU perform data transfer with it.

**Disadvantage**: wastage of CPU time


## Time required in programmed IO

= Time to read status bits + Time to check satus bit is set or not +  Data transfer time

$ by default the status register have size = 1 byte $
