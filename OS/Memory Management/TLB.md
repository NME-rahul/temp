# Translation Lookaside Buffer

* It is a high speed memory or registers that is used to store page table or segment table so that memory access time can be reduce.
* After using TLB the Effective Memory Access time is $EMAT = H_1 * (T_1 + T_2) + (1-H_1)*(T_1 + 2 * T_2)$
  * where, $H_1$: TLB hit ratio.
  * $T_1$: TLB access time.
  * $T_2$ : MM access time.
 
### Working

1. CPU generates the logical address having page or segment no.
2. This page or segment no. is then searched into page or segment table store in the TLB.
3. If there is Hit(page or segment no. is available in TLB).
   * Get the frame no.
4. IF there is Miss(page or segment no. is not available in TLB)
   * then it access the MM to acces the page to segment table.
   * and get the frame coressponding to the page or segment no.
5. After accessing Frame no. from Main Memory, the Main Memory is again accesed to access the content inside frame.

<p align="center">
 <img src="https://github.com/NME-rahul/temp/assets/100432854/0480db93-8533-480e-834b-0311b0ea5b14" width="600" height=""/>
</p>


* It is a Heiraarchical process it always starts b searching TLB for table and then search in MM, that's why we use this series access formula for calculating Effective Memory Access Tme $EMAT = H_1 * (T_1 + T_2) + (1-H_1)*(T_1 + 2 * T_2)$
