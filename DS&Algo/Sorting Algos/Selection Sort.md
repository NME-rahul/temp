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
