# For loops

1. Initlaize
2. Check Condition
3. Run for loop body
4. increment/decrement

### standard for loop

    for(initlazer; condition; incrementer/decrementer){
      //body
    }

## for loop without intializer

    int i = 0
    for(; i < n; i++){
      //body
    }

## for loop without condition

    for(i = 0; ; i++){
      if(i < n){
        //body
      }
    }

## for loop without increment/decrement

    for(i = 0; i < n; i++){
        //body
      i++;
    }

    for(i = 0; i < n; i--){
        //body
      i--;
    }
    
## for loop with body

    int i = 0
    for(; ; ){
      if(i < n){
        //body
      }
      i++;
    }

## for loop with function

    for(i = 0; condition(i); increment(i)){
      //body  condition() function must return boolean value, and increment() function must return integer value
    }

## for loop with multiple initialzer, condition and increment/derementer

    for(initalizer1, initalizer2, initalizer3,.... ; condition1, condition2, condition3 ....; increment1, increment2, increment3 ....){
      //body you can use conditions with logical operators with
    }
