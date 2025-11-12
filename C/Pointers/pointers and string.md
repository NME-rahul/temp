# Pointers and String

    int x[4] = "ABCD\0";

* x is constant pointer to first element
* to update any value we need to use specific address otherwise it will give error.
  * x  = "abcd" is an error, you can not do this, you can update 1 value at a time. x[0] = a; this will work fine.

*x  = "abcd" what is mean by it?
 * The compiler will first allocate memory to "abca"(from static area) and then assigns its base address to x. we can't update values at address pointed by x but we can assign a new address to variable x since it is a pointer to char.

    if("abcd" == "abcd")
       printf("yes");
    else
       printf("No");

the above program will print "No", earlier we have seen that the compiler first allocate the memory and then take it's base address for further operation let's  first "abcd" is stored at addresss 1000 and second "abcd" is stored at address 2000 and the comparision will on the base address of these two strings and if condition becomes false.


* printf("%s", "ABCD"[1])

What will above statemnet print? go by procedure, first compiler will allocate the memory for the string and then index it to first addres from base address and that will print "B".


* printf("%s", "pqrst" + 2);

let's say compiler allocate it memeory on base address 100 now we'll increment by 2 and then print all the elements from 2nd address until \0. and it will print "rst".


    int x[5], y[5] = "pqrst";
    x = y;
    printf("%s %s", x, y);


What above program will print?
  * It will generate error message because we are assigning/updating the constant variable x;

<div></div>

    int x[5] = "pqrst";
    x[0]++;

    printf("%s", x);

What above program will print, will it generate error?
  * No above program will not generate errror, becasue x[0]== *(x + 0) is not an address but value at address, so it will increment first "p" by 1 and this will give output as "qqrst".

----


<div align="center">
    <img src="https://github.com/user-attachments/assets/0921c8de-2e3b-422f-819d-de78c01ad736">
    <img src="https://github.com/user-attachments/assets/eadd5238-a5dd-4dad-b6b2-f39d45646888">
    <img src="https://github.com/user-attachments/assets/153b2b74-b925-461d-996a-feca37432b18">
</div>

