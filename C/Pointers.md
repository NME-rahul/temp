# Pointers

* $*$ is a operator that means "value at"(derefrence the memory)
* & is a operator that means "address of"


* Pointers are variables that stores the memory address of operand instead of direct value.

      void *p = NULL; //generic pointer that has no data type until casting
      printf("pointer address: %p", p);

* $p^*$ shows the operand at address and $p$ shows the address of operand.

      int x = 45;
      int *p = &x;
      printf("pointer address: %d", p);
      printf("operand at address: %d", *p);


## general initialization & assignmenet

      int x = 45;
      void *p = &x;
      printf("pointer address: %p", p);

## Use with function

    void fun(int *x){ //if caller funtion send parameter as address then calle need to store if it in pointer
      printf("X: %d ", *x);
    }
    int main(){
      int x = 45;
      fun(&x); // it calls the function with address of x
      //fun(x); it calls the function with copy of x
      return 0;
    }

## Use with function array

    void fun2(int *x){ //if caller funtion send parameter as address then calle need to store if it in pointer
      printf("X: %d ", x[0]);
    }
    
    void fun1(int x[]){ //if caller funtion send parameter as address then calle need to store if it in pointer
      printf("X: %d ", x[0]);
    }
    int main(){
      int x[] = {34, 56, 74, 12};
      fun(x); //in case of array you don't explicitly need to send address of array because array itself contains the base address by using this it iterates to the next value.
      // it is equivalent to &x[0]
      fun(x); //both will work absolutley fine
      return 0;
    }

* Rememeber because we are passing address instead of copy, operation performed on the passed array will reflect in the original array.


## Use with function 2D array

#### Statically declared 2D array


      void fun1(int col, int x[][col]){
        printf("X: %d ", x[0][3]);
      }
      
      int main(){
        int x[][5] = {{34, 56, 74, 12},
                    {45, 67, 11, 0, 34}};
        fun1(5, x); 
        return 0;
      }


#### Passing dynamicaly allocated array

* A 2D dynamically allocated array, is array of pointers and each pointer, pointes to to a 1D array.

      void fun1(int rows, int cols, int **x){ //first start denotes the first pointer of pointer array and 2nd start denotes the that each pointer has base address of 1D array
        printf("X: %d ", x[0][3]);
      }
  
      int main(){
        int rows = 5;
        int cols = 3;
        int **array = (int **)malloc(sizeof(int *) * rows) ;
        for(int i=0; i<rows; i++){
          x[i] = (int *)malloc(sizeof(int) * cols);
        }
        fun1(rows, cols, x);
        return 0;
      }

## Use with function 3D array

#### Statically declared 3D array

      void fun1(int dim, int row, int col, int x[dim][row][col]){
        printf("X: %d ", x[0][0][0]);
      }
      
      int main(){
        int x[3][5][5] = {
                          {
                            {34, 56, 74, 12}, 
                            {45, 67, 11, 0, 34}
                          }, 
                          {
                            {22, 3, 34,  1}, 
                            {342, 42}, 
                            {323, 56, 64, 90}
                          }
                        }; //dim , row, col
        fun1(5, 5, 3, x);
        return 0;
      }


#### dynamically allocated 3D array

* It is just pointers to pointers to pointers, 3D array have 3 parmeters, first is dimesnion second is row, and third is column
* Basically, the first parameter(dimension) is a 1D array of pointers and each pointer points to the 2D arrays.
* and 2D array, is array of pointers and each pointer pointes to to a 1D array.

      void fun1(int dim, int row, int col, int ***array){
        printf("X: %d ", array[0][0][0]);
      }
      
      int main(){
        int dim = 4;
        int rows = 5;
        int cols = 6;

        int ***array = (int ***)malloc(sizeof(int **) * dim);
  
        for(int i = 0; i < dim; i++){
          array[i] = (int **)malloc(sizeof(int *) * rows);
          for(int j = 0; j < rows; j ++){
            array[i][j] = (int *)malloc(sizeof(int) * rows)
          }
        }
  
        fun1(5, 5, 3, x);
        return 0;
      }
