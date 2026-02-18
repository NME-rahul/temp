# Static storage class

* Varible declared by `static` are alive througout the life cycle of prgoram, but their scope is limited to their function or block where they are declared.


# static and linker

* `static` keyword can be used to manage how linker sees you code. Its all about Linkage, which determines whether a variable(or function) is visible only within file where it is declared or outside the file.
* Inrenal linkage: when we apply  `static` to a global variable or function, you give it internal linkage, this means the linker will hide it from other trasaltion unit(file). The benfit is we can reuse the same name in different file of same programm, for example you declared `static int hello`
 in fileA.cpp and same `staic int hello` in fileB.cpp, now during linker this will not produce any linker error.
* by default(without `static`) the variables or functions have global linkage meaning they are visible accross program.
