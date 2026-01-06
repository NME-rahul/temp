<div align="">
  <img width="581" height="304" alt="image" src="https://github.com/user-attachments/assets/09ec0d45-a8a7-4808-bdd1-129e2b0e3324" />
  <img width="617" height="179" alt="image" src="https://github.com/user-attachments/assets/ee661734-8a0e-4aeb-8af4-c91966a13281" />
  <img width="661" height="405" alt="Screenshot 2026-01-06 at 6 39 48 AM" src="https://github.com/user-attachments/assets/0f58284a-a3e8-42e2-9b75-3617ace1d30b" />
</div>

* When C and E spreads the information of failed link immediately, all neighbour router to C will update the cost to infinity node having next Hope E.
* Similarily all neighbour router to E will update the cost to infinity node having next Hope C.

<div align="">
  <img width="672" height="409" alt="Screenshot 2026-01-06 at 6 39 54 AM" src="https://github.com/user-attachments/assets/be32fb65-6569-4376-b736-360394fa2459" />
</div>

* In solution b, If A and D exchange the vector immediately before they get updated by router C and D respectively, then in routing table of A and D we have infinity corespoding to next hope E and C since A recieved the vector from D so it will update the cost of all nodes having infinity according the received vector and similar of D.
* In solution C, If C receives the vector from A before then this type of FALSE cost will updated by C(i.e. count to infinity problem)
