# Design of Synchronous counter

1. Identify the number of states(counting) and calculate the number of flip-flops required to design counter using 2^(number of states).
2. Create the pre-state nex-state table of flip-flop.
3. Create state diagram and pre-state nex-state table of counting.
4. Obtain simplifies equation using k-map.
5. Draw the logic diagram.

---

**Question**

Design a 2bit synchronous up counter.

**Solution**

1. J-k flip-flop, given 2 bit counter means 2 flip-flops, and number of states = 2^bit = 2^2 = 4.
2. Create the pre-state nex-state table of flip-flop.
   |$$Q_n$$|$$Q_{n+1}$$|J  |K  |
   |-------|-----------|---|---|
   |0      |0          |0  |d  |
   |0      |1          |1  |d  |
   |1      |0          |d  |1  |
   |1      |1          |d  |0  |

3. 
