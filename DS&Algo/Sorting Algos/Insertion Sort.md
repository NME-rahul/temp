# Insertion Sort

* It workd on assumption that whatever in left of me(current element) is always sorted.
* For each incoming element(current) it cheks left side and put that element at its appropriate position.

      for i = 1 to n:
        current = arr[i]
        for j = i-1 to -1:
          if arr[j] < current:
            arr[j] = arr[j-1]
          else if arr[j] <= current:
            arr[j+1] = current
          else if j < 0:  //when ith elements' appropriate position is first
            arr[0] = current;

* Time Complexity: $O(n^2)$
* Stable and In Place
* Best case time complexity: $O(n)$

### Binary Search and Insertion Sort

* Because we know left side of current element is already sorted so we can use binary search to find the correct position of current element in $O(lgn)$ time. But still we have to shift the element from appropriate elements to current elements' position. Coclusion binary search doesnt help in reducing time complexity.
* Time Complexity: $O(n^2)$
