* it is used to manage memory efficiently, statilcally allocated memory may or not be used throughout the program execution.
* dynamic memory allocation is always done from heap and static memory allocation is always from stack.
* it is not conitguos

* malloc(); calloc(); allocte memory
* realloc(); to update memory size
* free(); to release memory

<div></div>

    int *p, n;
    scanf("%d", &n);
    p = malloc(n*sizoef(int));  //allocate n integer size memory blocks

genearlly malloc returns void pointer, that's why you need to typecase it every time you use.


    int *p, n;
    scanf("%d", &n);
    p = (int *)malloc(n*sizoef(int));  //allocate n integer size memory blocks.

now you can access integer size block of memory using indexing i.e. p[0], p[1], ..


    p = (int *)realloc(p, <new size>); //to allocate more memory

if during reallocation process does not found contigiuos memory then it reallocate the the whole memory where it will found contigous memory.


    p = (int *)calloc(<no of chunks>, <chunk size>);

it takes two arguments, else works same as malloc. one main differece between calloc and malloc is calloc intialize every memory location with 0 but malloc does not intialize meomory block it returns memory having previous data(garbage).


    free(p);

it will free entire memory, without malloc() and calloc() free() can not be used
