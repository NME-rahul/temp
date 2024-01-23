# Schedule

The Order in which operations of multiple transactions appears for execution is called Schedule.

## Types of Schedule

<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/4cbf23d6-365c-4858-8b85-c0c60944697d" />
</p>

1. **Serial Schedule**:
   * All the transactions exceutes serially one after another.
   * When one transaction is execute, no other transaction is allowd to execute.
   * Total possible serial schedules = $n!$
   * **Characteristics**:
     * Consistent
     * Recoverable
     * Cascadeless
     * Strict

1. **Serial Schedule**:
   * Multiple transactions executes concurrently.
   * Operations of all the transactions are interleaved with each other.
   * **Characteristics**: may not always.
     * Consistent
     * Recoverable
     * Cascadeless
     * Strict

# Serailzability

IF a non-Serial schedule can be transformed into it's eqvivalent serial schedule then it is called serializable.


## Types of Serializable

1. **Conflict Serializable**:
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

* **find serial schedule of serializable schedule**:
  * $1.$ Repeat step 2 and 3 procedure until 1 vertex remain.
  * $2.$ Calculate indegree of each vertx.
  * $3.$ Remove vertex having the 0 indegree.
  * $4.$ Now, create a sequence in which you removed the vertex, the formed sequence will be the serial schedule.

* **Conflict eqvivlance**: Two transaction that have same precedence graph.
  
2. **View Serializable**:
   * Conflict serailizable has limited scope, even if a schedule's precedence graph has loop it could be a serializable schedule.
   * To overcome the limitation of conflict serailizable view serializable is used.
   * If a schedule is a conflict serializable schedule then its definatly view serializble but inverse is not ture because conflict serializable schedule is a subset of view serialble schedules.
   * View serialzbility is a NP-hard problem beacuse we have to check $n!$ view equivalance combinations.
  
**View Equivalance**: 2 schedules are said to be view equivalent if they follow following rules.
* $1.$ Same data item in both schedules should read first from database.
* $2.$ the order of read from other transaction's written value should same in both schedules for each data item.
* $3.$ same data item should be written last on database in both schedules.

* **Definition**: a schedules a  is said to be view serializable if there exist a View Equivalance schedule. that we need  to check one-by-one.

* **Note**: Never check view serializability always check conflict serializability becaue if a schedule is serializable then it is definatly view serializable.
