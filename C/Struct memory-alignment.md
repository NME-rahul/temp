# struct memory-alignment

* Every element must be plced at the memory location of multiple of own size, for eg. if `int` is of 4 bytes then it can be stored at memory locations 0, 4, 8, 16, .....

<div></div>

    struct stu_a {
      int i; //int of size 4
      char c; //char of size 1
    }

<div align="center">
  <img height="400" width="400" src="https://github.com/user-attachments/assets/4d6165a3-071e-40f8-8c7f-fc6865302ed5" >
</div>


    struct stu_a {
      long l; //long of size 8
      char i; //char of size 1
    }

<div align="center">
  <img height="400" width="400" src="https://github.com/user-attachments/assets/6ee50b0d-ae35-4ee6-a55a-df387b0fc77d">
</div>



    struct stu_a {
      int l; //
      long i; //long of size 8
      char c; //char of size 1
    }

<div align="center">
  <img height="400" width="400" src="https://github.com/user-attachments/assets/e3236b06-50e0-4540-ad88-7fe5aa459fba">
</div>


    struct stu_a {
      long l;
      int i; 
      char c; 
    }

<div align="center">
  <img height="400" width="400" src="https://github.com/user-attachments/assets/29710eb3-66ab-4f1e-8e13-13b82ac840a4">
</div>

* By just changing the order we can save the space.

    struct stu_a {
      short s;
      char c; 
      int i;
      long l;
    }

<div align="center">
  <img height="400" width="400" src="https://github.com/user-attachments/assets/1d568c27-aa7a-44ba-a4fc-06b173022b50">
</div>
