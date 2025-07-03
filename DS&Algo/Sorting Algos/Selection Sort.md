# Selction Sort

It is a most natural sorting algorithm.
at each time you select maximum or minimum element and put that into last/inital.

    for i=0 to n:
      min = arr[i]
      for j=0 to n:
        if min > arr[j]:
          min = arr[j]

      temp = a[i]
      a[i] = min
      a[j] = temp

Whatever the case, it always produces $O(n^2)$ time complexity because at each it checks for max element starting from 0 to n
