# ROM

* A rom is denoted by the by the $2^n \\\ \times \\\ m$ where $2^n$ denotes the the number address, $n$ denotes the input combination and m denotes the word size at each address.
* This ROM is nothing but the Decoder fused with OR gate to form function because we know a $n \\\ \times \\\ 2^n$ decoder can produce every the output with $n$ variable.
* So the ROM can also be denoted as $n \times \\\ 2^n \times \\\ m$

<div align="center">
<img width="711" height="467" alt="image" src="https://github.com/user-attachments/assets/797ed537-2d04-4f42-99fc-1554e9632cac" />
</div>

* $A_0, A_1, ...., A_5$ are the inputs and $F_1, F_2, F_3, F_4, F_5$ are the outputs making the word size and $2^5$ numbers of words are here.

## Practice

To realize decoder of $2^{14} \\\ \times \\\ 16$ with $2^9 \\\ \times \\\ 2$ we requires $\frac{2^{14} \\\ \times \\\ 16}{2^9 \\\ \times \\\ 2} = 2^5 \\\ \times \\\ 8$ chips. 
Here second term describes that we need to add $8$ chips together to form $8 \\\ \times 2 = 16$ bit word size and to make $2^{14}$ addresses we need to add set of $8-8$ $2^9 \\\ \times \\\ 2$ chips in parralal for $2^5$ times that is $2^5 \\\ \times \\\ 2^9 = 2^{14}$ with the help of decoder.
