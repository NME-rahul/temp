# Pipelineing

## Data Hazard
1. Data Hazard
2. Control Hazard
3. Structural Hazard: This type of hazard are eliminated by stalls or using more hardware.

## 1. Data Hazard Solutions

* Here we'lll discuss solutions only RAW data hazards.

1. Delay Solution/stall solution
   1. Hardware Solutions
   2. Software Solutions: Inserting NO OP instruction by compiler.
3. Forwarding solution

1.i **Hardware Solutions**:
  * Detect the dependency
  * Wait(Stalls) until the value is appeared in the register correctly.
<img width="392" height="367" alt="Screenshot 2025-12-16 at 2 20 35 PM" src="https://github.com/user-attachments/assets/b4d2fac5-ad91-4cff-a845-6eed604529dd" />



2. Forwarding Solutions: In this solution the content of one stage is forwared to the stage where it needed.
<img align="center" width="400" height="600" alt="Screenshot 2025-12-16 at 2 20 35 PM" src="https://github.com/user-attachments/assets/b39029f0-2efe-43bd-9455-eefba3d0897e" />



### 2. Control Hazard Solutions

1. Stop Fecthing after every instruction
2. Keep Fetching
   1. Predict not Taken: It assumes that predict is not branch will not be taken and starts fetching next instruction, if branch is resolved to taken in future stages then we will flush the pipeline and control will be transfered to ranch target address. So stall will be there for instructions that causes branch to transfer control.
   2. Predict Taken: In this solution we assumes that branch will be taken and at `IF` stage addittional hardware is used to get the target address from instruction and next instruction to be fetch are the target address and its successive instructions by this way we only causes the stalls for instructions that do not cause branch to be not taken later in execution stage.
  
3. Dynamic ranch Prediction: It keeps learning after new data like machine learning model. For eg. A instruction sequence have 20% branch instruction, hardware have prediction accuracy of 70% and Branch REsolves Branch in 3rd stage then we will have avg. $CPI = 1 + 0.2*0.3*2$

4. Delayed Branching: (Usesd in classical MIPS(RISC) pipeline) Up until We're having stalls if mispredicts. In this solution what we will do is fetch instruction that are not dependent on branch, dependent instructions are the instructions those are in `the fall through path of Branch and Branch target instructions`.
   * If we do not have any independent instructions then compiler adds the NOP instructions. A NOP instrution essentially tells the processor to "do nothing" for a set of number of clock cyles and does not alter the system state(aprt from the program counter).
  <img width="475" height="338" alt="Screenshot 2025-12-16 at 2 20 28 PM" src="https://github.com/user-attachments/assets/c5d6dd13-7df7-4354-b7fe-24ce69ab93fc" />
  <img width="392" height="367" alt="Screenshot 2025-12-16 at 2 20 35 PM" src="https://github.com/user-attachments/assets/79d340fe-4e2b-48b2-99f7-e5b220c106ac" />
  <img width="392" height="367" alt="Screenshot 2025-12-16 at 2 20 35 PM" src="https://github.com/user-attachments/assets/60c6cb7e-3751-450e-a3d1-8b68e14f37dd" />
