# Minimum Hamming distance

* To detect $k$ bit error we need at least $d+1$ hamming distance.
* To correct $k$ bit error we need at least $2d+1$ hamming distance.

<img width="1001" height="287" alt="Screenshot 2026-01-08 at 3 27 50 PM" src="https://github.com/user-attachments/assets/cc9f2687-ccf0-442f-9ad8-1dbfd68f5175" />

Consider the below example, here we have given that distance between two valid codeword is 5, meaning there are 4 invalid codewords in between 2 valid codewords, and there sphere of influence is 3*2(excluding itself) code words around it,
so if we'receive a codeword that is detected to invalid then we can see to which valid code sphere it belongs and can correct it

<div align="center">
  <img width="300" height="35" alt="Screenshot 2026-01-08 at 3 35 09 PM" src="https://github.com/user-attachments/assets/e05b924b-e2d3-4d65-bfab-e43dd086020a" />
</div>

* The value of sphere inflence should be $2d + 1$(including itself), wher $d$ is the number if bits that can be corrected,
* Here the value is given $5 >= 2d + 1$, that means we can correct upto $d <= 2$ error, meaning find the codeword(from given) that can be obtained by chnaging $2$ or less bits, in the above example that valid code word is $0000011111$
