# Dangling pointers

    int *p, n, *pp;
    scanf("%d", &n);

    p = (int *)malloc(n*sizeof(int));
    pp = p;
    free(p);

p and pp are pointing to the same memory location but when free(p) is executed memory allocated to it released now both pp pointer is poitning to the released memory, now pp will be called dangling pointer.
if we use free(pp) then p will become dangling pointer.

using prevously allocated memory by pointer p that is deallocated by some other pointer refrence curenlty, is known as dangling pointer.
