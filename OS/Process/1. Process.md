# Process

<img width="637" height="647" alt="Screenshot 2025-12-20 at 1 50 49 PM" src="https://github.com/user-attachments/assets/b464b2d5-37d7-4e06-aecb-bc4a8002819e" />
<img width="691" height="686" alt="Screenshot 2025-12-20 at 1 54 27 PM" src="https://github.com/user-attachments/assets/bbaad403-72ef-4381-8028-e4a50e452ea7" />
<img width="691" height="686" alt="Screenshot 2025-12-20 at 1 54 27 PM" src="https://github.com/user-attachments/assets/5cf10c5a-55f3-4f33-9556-35d228c9d930" />


### Schedulars
* The names of these schedular is based on the frequency of their use, the short-term schedular is highest frequency of use and long-term schedular has least frequency of use.
1. **Long-term Scheduler(Job Schedular)** : Select which process should be brough into the ready queue. The long-term schedular control the **degree of multiprogramming**. For desktop computer we dont require this schedular, and process are admiited automatcally. This type of scheduling is very important for real-time OS.
2. **Mid-term Schedular**: The mid-term schedular is present in every system with virtual memeory, it temporarily removes process from main-memory and places them on secondary memory. This also affects the degree of multiprogramming as it brings suspended process from secondary to main-memory again.
3. **Short-term Schedular**: Firtstly A decision is made to which process from ready queue is selected to schedule in CPU and this decision must not be delayed, is done by the dispatcherand scheduling is done by the short-term schedular. Short-term schedular provides the multitasking capability in single core processor where one core is shared between multiple processes.
