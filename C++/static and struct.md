# static and struct

* `static` with `struct` and `class` works in a smiliar way.

      struct Hello{
          static int x, y;
          static print(){
            std::cout << x << " " << y << std::endl;
          }
      };

      int main(){
          Hello e1;
          e1.x = 2;
          e1.y = 3;

          Hello e2;
          e2.x = 9;
          e2.y = 10;

          e1.print();
          e2.print();
      }


* here e1 and e2 are not two different variables but they sharing same memory it like two name of the same memory locations.
* By compiling t we'll get compileation error because `static int x, y;` have visibility to the struct variable only to access the we need to declare them `int Hello::x, Hello:y;`

<div></div>

     struct Hello{
          static int x, y;
          static print(){
            std::cout << x << " " << y << std::endl;
          }
      };

      int Hello::x, Hello::y;

      int main(){
          Hello e1;
          e1.x = 2;
          e1.y = 3;

          Hello e2;
          e2.x = 9;
          e2.y = 10;

          e1.print();
          e2.print();
      }


* Because e1 and e2 are the same instance so it will print two times $9$ and $10$ because we have called _print_ method two times. Make it correct by following.


<div></div>

     struct Hello{
          static int x, y;
          static print(){
            std::cout << x << " " << y << std::endl;
          }
      };

      int Hello::x, Hello::y;

      int main(){
          Hello e1;
          Hello::x = 2;
          Hello::y = 3;

          Hello e2;
          Hello::x = 9;
          Hello::y = 10;

          Hello::print();
          Hello::print();
      }

* `static` with `struct` is used for the orgnization of data, instead of using global variable just create an entity using struct or class with static to orgnize the global variables.
