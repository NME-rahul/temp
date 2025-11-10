# Number Representation

* In C numbers are represented using 2's complement.

<p align="center">
int x = 9 Suppose: size of int is 8 bit<br>
  it will be represented as: 0000 1001<br>
int x = -9 <br>
it will be represented as: 1111 0111
</p>

## Format specifers

<p align="center">
  <img height="650px" width="650px" src="https://github.com/user-attachments/assets/7ec9fb8b-1326-48ad-b575-42b4338bbd93">
</p>

It doesn't matter with which repersentation we're declaring variable, Compiler will store negative numbers as they were repesented in 2's complmented and the value of variable will be recognized based on how we're treating it.
for eg.

    unsinged int X = -9;
    
X will be stored as 1111 0111 in 2's complement.

    printf("%d", X);
    output:- -9
    
    printf("%u", X); //unsigned int
    output:- 503

For `printf()` function the `type` is not valued it prints the value based on what specifer is used. The `type` provides information when we preform arithmatic operations.


## Extension and Truncataion

**Extension**: Coping a lower bit number to higher bit. eg. short to int.
**Truncation**: Copying a higher bit number to lowe bit. for eg. int to short

**Extension**:
Extesion happens based on source `type` if source is of signed then it retains the sign the MSB bit for remaning bits while extension.
<p align="center">
<img width="690" height="426" alt="Screenshot 2025-11-10 at 11 43 21 AM" src="https://github.com/user-attachments/assets/edc3e459-d789-4654-ba94-335ad0940db2" />
</p>

* Even after changing the destination `type` we're still doing extension based on source `type`. 
<p align="center">
<img width="690" height="426" alt="Screenshot 2025-11-10 at 11 44 26 AM" src="https://github.com/user-attachments/assets/d50a5921-b8a9-462e-b50f-1b786d4fef46" />
</p>

* THe source that is `short int y` is a signed reprsentation so the extension is happend based on what is sign bit and retains the sing bit.

<p align="center">
<img width="690" height="426" alt="Screenshot 2025-11-10 at 11 51 24 AM" src="https://github.com/user-attachments/assets/04226f39-6cec-4a69-98cd-f0ab1cdc25d9" />
</p>

* Since the source is `unsigned short int y` the whole bits is used represented the numbers i.e. their is no sign bit thats why while extensing it is putting 0's.


**Truncation**
While Truncation regardless of source or destination `unsigned` or `signed` type, truncation always just truncates. This can cause the number to change drastically in sign value.

<p align="center">
  <img width="573" height="163" alt="Screenshot 2025-11-10 at 12 02 36 PM" src="https://github.com/user-attachments/assets/171630e4-2500-4eb4-82fa-4ffffa7d3b04" />
</p>



## Integer Promotion
Whenever a `short` or `char` is used for an expression it will be promoted to `int`(rest rules are same as type Extension).

<p align="center">
  <img width="690" height="426" alt="Screenshot 2025-11-10 at 1 41 37 PM" src="https://github.com/user-attachments/assets/1b4aa59d-7f59-47f1-b0d4-a22be63621b6" />
</p>
