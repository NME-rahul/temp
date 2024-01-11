# Types of Control unit

1. Hardwied Control Unit
2. Microprogrammed Control Unit

## Hardwired Control Unit

* Control logic is implemented through the circuits like Gate, flip-flop, decoder etc.
* It is a finite state machine(FSM) that generates control word.

* **Advatnage**: It is faster as compared to Micorprogrammed Control Unit.
* **Disadvatnage**: Once the circuit is implemented the updation is not possible.


<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/39c1a92d-8eeb-4fec-a1d8-9fe13a32b121" width="" height="" />
</p>



## Microprogrammed Control unit

* The programing approach is used to implement the control unit.
* Control logic is implemented through micro-programms that is made up of sequence of micro-instructions.
* All possible control words are stored in a memory and based on the requirments specific word is fetched & sent to the CPU.

* **Advatnage**: updation of control logic is easy.
* **Disadvatnage**: Slower as compared to Hardwired Control unit.

**Standard Mico-Instruction Format**

|Control Word|Mux select|Next Address|
|---|---|---|

**Control Word**: A control word in the micro-instruction is a set of signals(0 or 1) that enables the diffrent circuits(ie. ALU, MUX) to perfrom a single instruction(in RISC) or micro-instruction(in CISC).

**Next Address**: it helps to calculate the next microinstruction's address.

<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/73df0695-243d-409b-9227-31d929cd62fb" width="" height="" />
</p>

1. **Next Address Generator(sequencer)**: It is used to calculate the next microinstruction's address.
2. **Control Address Register(CAR)**: It stores the address of the next microinstruction and to read the control memory it sends the address to the control memory.
3. **Control Memory(ROM)**: The control memory then sends the microinstruction accroding to incoming address from Control Address Register to the control data register.
4. **Control Data Register(CDR)**: It outputs the control word to the CPU and next address of microinstruction again to the Sequencer.

### Microinstruction execution cycle

1. **Fetch phase**: The microinstruction is fetched from the control memory. The address of the next microinstruction is determined by the current microinstrucction's address field or modifid based on certain conditions.
2. **Decoder phase**: The fetched microinstruction is decoded to extract the control word signal and other relevant information.
