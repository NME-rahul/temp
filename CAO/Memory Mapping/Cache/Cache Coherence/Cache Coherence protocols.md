# Cache Coherence protocol

1. Snooping based/Bus-based protocol
2. Directory-based protocol

## Snooping Based Protocol

<p align="center">
<img width="1440" alt="Screenshot 2024-01-10 at 2 16 55 PM" src="https://github.com/NME-rahul/temp/assets/100432854/44fd4862-4753-44a2-99dc-aafde4f1f3e0">
</p>


**Coherence Miss**: if line inside the cache of processor is in invalid state the processor can not use the line for performing operation, this situation is known coherence miss.

**Working**:
1. Suppose A is a variable inside the main-memory with value 7.
2. When P1 wants to access the variable A then state of A will turn to shared inside the private cache.
3. Now other processor P3 also wnats to access the same shared data variable A.
4. When P1 wants to perform operation as P1: A+1 in that case the state of the of the copy of variable A inside the private cache of P1 will turn to modified.
5. The moment when P1 updates the value of A, it places an invalidate signal on Bus indicaating all other cache to invalidate their shared copy of variable A.
6. IF we use **Write Through** policy in the cache then the updation will imidiatly propgate to the main-memory.
7. IF we use **Write Back** policy in the cachethen the updation in the mai-memory will reflect in the next cache block replacement.
8. In **Write update** strategy instead of generating invalid request, P1 generates an update request and place it on the shared bus commandng all other cache memory to update their local copies of A. Once the all update is done the state will change into the "shared".

## Directory Based Protocol

**NOte**: In snooping-base protocol when we have N number of processors then the common bus bottlenecks.

* In this organization each processor have their own cache meory, main-memory as well as directory.
* The communication between the processors is done by the Point-2-Point communication.

<p align="center">
<img width="1421" alt="Screenshot 2024-01-10 at 2 40 23 PM" src="https://github.com/NME-rahul/temp/assets/100432854/5e913305-e10b-4933-af80-d416f485c0e2">
</p>

1. 




 
