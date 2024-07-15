# Language processor

<div align="center">
  <img width="544" alt="Screenshot 2024-07-15 at 3 05 59 PM" src="https://github.com/user-attachments/assets/785abfc3-66e6-4f43-ae75-a74fb0f6ae5b">
</div>



# Structure of Compiler 

* We can see compilers as two parts: **Analysis** and **Synthesis**.
* **Analysis part:** breaks up the source program into pieces and impose a grammatical structure on them. The analysis part contains phases from lexcal analysis to the intermidiate code generation. It collects information about the source programs and stores it in data strcture called symbol table, which is paases along with intermidate representation to the synthesis part. Phases in this part are machine independent.
* **Synthesis part:** This construct the desired target program from the intermidiate reprsentation and information in the symbol table. Phases in this part are machine dependent.

<div class="" align="center">
  <img width="667" alt="Screenshot 2024-07-15 at 3 21 45 PM" src="https://github.com/user-attachments/assets/5c7944ab-fec9-422b-8b57-959514d07eec">
</div>
