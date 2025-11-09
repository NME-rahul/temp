# Sotrage Classes

<p align = "center">
  <img src="https://github.com/user-attachments/assets/197d67a7-1c9a-4428-9f68-bc1475f76b62" />
</p>

## 1. Automatic

* By default storage class of every local variables is **auto**.
*  **Storage**: RAM
*  **Default value**: Garbage
*  **Scope**: Within defined block
*  **Lifetime**: Within defined block

## 2. Register
* Variabale will store in CPU register. It is a request not command, and it is not necessary that variables will get space in register. Varibles that are frequently used should assigned with register, for eg. indexing variable.
*  **Storage**: CPU Register
*  **Default value**: Garbage
*  **Scope**: Within defined block
*  **Lifetime**: Within defined block

## 3. Static

* Defined once in a lifetime and its memory does not deallocate when control is again transfer to main.
*  **Storage**: RAM
*  **Default value**: 0
*  **Scope**: Within defined block
*  **Lifetime**: whole program

## 4. External
* Extern  storage class is used to declare a variable or a function but not to define i.e. it gives information to compiler that x is only decalred here bu definition can be present same or other file.
* It extends the visibilty of the variables and functions in C to multiple source file.
* If local and global varible have same name then prioity will be given to local varible, to use global variable **scope resolution operator(::)** is used.
* No seperate memory for local x and it will use memory of global x only.

      extern int x; //declared here, but defined 

*  **Storage**: RAM
*  **Default value**: 0
*  **Scope**: whole program
*  **Lifetime**: whole program
