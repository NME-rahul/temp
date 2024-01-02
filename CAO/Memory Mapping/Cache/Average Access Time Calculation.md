# Effective Address Calculation

* There will be only two types of questions,

 1. First type is parallel/simulatneous access(default) when nothing is specified, how is memory is orgnized. In this case the effective memory access time is $EAT = H_1*T_1 + (1-H_1) * H_2 * T_2 + (1-H_1)(1-H_2)*T3$
    
    <p align="center">
      <img src="https://github.com/NME-rahul/temp/assets/100432854/dab8bd46-ddc7-459d-8c83-d9f8d716dec2" height="" width="" />
    </p>

 2. Second type is series/hierarchical access, it will be specifically defined in the question. In this case the effective memory access time will be $EAT = H_1 * T_1 + (1-H_1)* H_2 *(T_1 + T2) + (1-H_1) * (1-H_2) *(T_1 + T_2 + T_3)$
    
    <p align="center">
      <img src="https://github.com/NME-rahul/temp/assets/100432854/77b36628-97c8-49d2-b09c-72c9e7c360fc" height="" width="" />
    </p>


## Miscelleneous

* Questions with Write-back, Write-through or Write-allocation, No write-allocation or mixed stratergies.
