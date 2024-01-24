# Types of Serializable

1. Conflict Serializabilty
2. View Serializability

   <p align="center">
     <img height="300" width="" src="https://github.com/NME-rahul/temp/assets/100432854/b929082c-77e9-460f-bbc3-1abf5a1dd512" />
   </p>

## **Conflict Serializable**:
   * A sschedule having conflict pairs called conflict serializable.
   <div align="center">
     
   |Conflict pairs|
   |----|
   |R(A) - W(A)|
   |W(A) - W(A)|
   |W(A) - R(A)|
   </div>

* **To check conflict seralizability**:
  * Create a precedence graph using conflict pairs.
  * if there exist any loop in graph.
    * schedule is conflict serailizable
  * else
    * no conflict schedule.
  * If a schedule is conflict serializable than it is guranted that schedule is serializable schedule and hence consistent schedule.

**find serial schedule of serializable schedule**:
 * $1.$ Repeat step 2 and 3 procedure until 1 vertex remain.
 * $2.$ Calculate indegree of each vertx.
 * $3.$ Remove vertex having the 0 indegree.
 * $4.$ Now, create a sequence in which you removed the vertex, the formed sequence will be the serial schedule.

* **Conflict eqvivlance**: Two transaction that have same precedence graph.

 ## **View Serializable**:
   * Conflict serailizable has limited scope, even if a schedule's precedence graph has loop it could be a serializable schedule.
   * To overcome the limitation of conflict serailizable view serializable is used.
   * If a schedule is a conflict serializable schedule then its definatly view serializble but inverse is not ture because conflict serializable schedule is a subset of view serialble schedules.
   * View serialzbility is a NP-hard problem beacuse we have to check $n!$ view equivalance combinations.
  
**View Equivalance**: 2 schedules are said to be view equivalent if they follow some conditions.
* $1.$ If non-serial schedual and its equivalnet serial schedule Reads the same data item initially.
* $2.$ Final write should same.
* $3.$ Intermidiate read should same.
* **Definition**: a schedules a is said to be view serializable if there exist a View Equivalance schedule and that we need to check one-by-one.

* **Note**: Never check view serializability always check conflict serializability because if a schedule is conflict serializable then it is definatly view serializable.

## Blind Write:

IF any transaction in schedule write data without before readig then it is called blind write.

<div align="center">
   <img height="" width="" src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240124_154259.jpg" />
</div>

**easy solution**:
   * To check whether a schedule is view serializable find if there exist a blind write or not.
