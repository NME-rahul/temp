# Median In Unsorted Array O(n)

* There is a naive apprach to find median in the unsorted array is to first sort the algorithm and then find middle element but it takes $O(n.logn)$ time.
* Another Appraoch is to modify the quick sort algorithm which can find median in $O(n)$ time, it is also called quick select algorithm and it totally depends on the choice of pivot element, and time can go upto $O(n^2)$.

      modified_quicksort(A, first, last):
          pivot = A[ random(0, n) ]

          i = first; j = last;
          while(i <= j){
              while(A[i] < pivot ) i++;
              while(A[j] > pivot) j++;

              swap(A[i], A[j]);
          }

          middleIndex = (low + last)/2
          if( j != middleIndex ){
              if( j > middleIndex ){
                  modified_quicksort(A, j+1, last);
              }
              else if ( j < middleIndex ){
                  modified_quicksort(A, first, j-1);
              }
          }
          if( j == middleIndex ){
              median = A[middleIndex];
          }

          return median;

* There is an another algorithm called median of medians, effciently finds the median in $O(n)$ time.

## Median-of-Medians

https://ocw.mit.edu/courses/6-046j-design-and-analysis-of-algorithms-spring-2012/c3a8610ea2120258eaa0d71f95f59fde_MIT6_046JS12_lec01.pdf
