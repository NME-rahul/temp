* It is not appraoch to always find the by taking example and then run sometimes we can try by converting SQL query into statemnts and then matching the statement whether the statement and query is same or not.


$R(name, age, state)$
We have to find the name and age of yongest graduate who lives in rajasthan.

      SELECT name, age
      FROM graduates
      WHERE state = "RAJ"
      and
      age = (SELECT MIN(age) FROM graduates)

1. First state the subquery/innerquery.
  * select min age from the table of all graduates.

2. go to outer query
   * Select name and age of those graduates who lives in rajasthan and their age is, minimum of all the graduates. 


* is it the match?
  * No, because it selects the only graduate from rajasthan whos age is younges in all the graduates but the question asks "younges graduate who lives in rajastha" that mean whatever the age the age is it must be minimum out of graduates of rajsthan. but out query is selecting only those graduates who are youngest not in rajasthan but in all states as well.
  * So, this query works well only when rajasthan graduates is youngest from all graduates otherwise.
    * works good:  minimum age >= rajsthan’s minimum age
    * gives NONE:  minimum age < rajsthan’s minimum age
   
--

      SELECT name, age
      FROM graduates
      WHERE state = "RAJ"
      and
      age == (SELECT MIN(age) FROM graduates WHERE state = "RAJ")

1. Select minimum age of gragraduates who lives in rajasthan.(innerquery)
2. Select name and age of students who lives in rajasthan and their age is equal to minimum age of gragraduates who lives in rajasthan.(outer query with inner query)

* Now this will gives correct result.
