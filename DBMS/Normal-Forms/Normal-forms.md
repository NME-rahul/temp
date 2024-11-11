## NOTE: After merging and decomposing any table you must need to think what will be the prime-key.

# 1 NF

* Fileds must contain atomic values.
* **To Remove this**
  * create seprate row for each value

<div align="center">

|PatientID|PatientName|Doctor|Dieases|DoctorID|PatientAddress|
|---------|-----------|------|-------|--------|--------------|
|5001|Rahul, 38|Ram, Chavi|alphaviruses, Acute Flaccid Myelitis|1001, 1004|Jaipur|
|5002|Sursh, 56|Dhruv, Sambhavita|Cold, Cancer|1002, 1003|Jodhpur|
|5003|Ramesh, 23|Ram, Druv|alphaviruses, Arthritis|1001, 1002|Delhi|
|5004|Neelam, 60|Chavi, Sambhavita|Babesios, Cancer|1004, 1003|Bikaner|
</div>

### Coversion in 1NF

<div align="center">

|PatientID|PatientName|Age|Doctor|Dieases|DoctorID|PatientAddress|
|---------|-----------|---|------|-------|--------|--------------|
|5001|Rahul|38|Ram|alphaviruses|1001|Jaipur|
|5001|Rahul|38|Chavi|Acute Flaccid Myelitis|1004|Jaipur|
|5002|Sursh|56|Dhruv|Cold|1002|Jodhpur|
|5002|Sursh|56|Sambhavita|Cancer|1003|Jodhpur|
|5003|Ramesh|23|Druv|Arthritis|1002|Delhi|
|5003|Ramesh|23|Ram|alphaviruses|1001|Delhi|
|5004|Neelam|60|Chavi|Babesios|1004|Bikaner|
|5004|Neelam|60|Sambhavita|Cancer|1003|Bikaner|
</div>

* We have removes multivalued attribute but what is the prime-key? This will be composit-key of previous prime-key and multivalued-attribute column i.e (```PatientID``` ```Dieases``` ```DoctorID``` ```Age```) because during transforming we created redundant entries in prime-key column.
* can you take less attribute in prime-key like prime-key with only one other multivalued-attribute?
  * No, if the person with same age, disease, treated by same by Doctor then?
    <div align="center">	
     
     |PatientID|PatientName|Age|Doctor|Dieases|DoctorID|PatientAddress|
     |---------|-----------|---|------|-------|--------|--------------|
     |5001|Rahul|38|Ram|alphaviruses|1001|Jaipur|
     |5035|Rahul|38|Chavi|Babesios|1004|Shimla|
     |5035|Rahul|38|Ram|alphaviruses|1001|Shimla|
     |5035|Rahul|38|Chavi|Acute Flaccid Myelitis|1004|Shimla|
    </div>

* now answer this can you identify the Dieases of a patient with (PatientID and DoctorID) given respectively (5035, 1004)?
  * No, there are two entry for this (5035, Rahul, 38, Chavi, Babesios, 1004, Shimla,) (5035, Rahul, 38, Chavi, Acute Flaccid Myelitis, 1004, Shimla). with only (patientID and Age) you cant' idenetify doctorID, Doctor name, Dieseas, with only (patientID, Doctor) you can't identify Dieases, DoctorID because name of doctors can be same treating the same Dieases.
  * So, we can't take less attributes in candidate-key, by taking less attributes we can identify the non-multivalued attributes uniquly but not itself multivalued-valued entries.

* You do this, and this is valid, but there are some anamolies like updation, insertion and deletion, you can't add new diseases and delete any disease or doctors entry because it can violate constraint of prime-key, and also during updation you have to update multiple entries, due to data redundency, so the best idea is to create a seprate table for each multivalued attributes having forigen-key which is primary-key of main table.

## 2 NF

* The table should be in 1NF.
* Non-prime key should be partially dependent on candidate-key.
* Each non-key in table should fully-functionally dependent on the entire primary-key or candidate-key.
* **Functioanly dependent:** If values of field B is determined by the field A, and there can be only one value in field B. Here, A is a prime-key and B is non-prime-key.
  * **Symbolic repersentation:** A ---> B
* **To remove this:**
  * create a table for functionlaly dependent attributes. primary-key --> non-key1, primary-key --> non-key2, primary-key --> non-key3...,.
  * Think about primary key for each table.

<div align="center">
 
|PatientID|PatientName|Age|Doctor|Dieases|DoctorID|PatientAddress|
|---------|-------|---|-------|-------|---------|----|
</div>

* From the table the functional dependencies are
  * PatientID ---> PatientName, Age, PatientAddress
  * DoctorsID ---> Doctor
  * Dieases ---> DoctorID, Doctore
  * Here, {PatientId, Dieases} is a candidate key, and attributes {PatientName, Age, PatientAddress} and {DoctorID, Doctorw} are partially dependent on PatientId and Dieases reectively, so this is not in 2NF. to make this in 2NF create seprate table for each dependecies {PatientID ---> PatientName, Age, PatientAddress} and {Dieases ---> DoctorID, Doctor} and create a new table that joins both tables.
  * Here we are no talking abot dependency, {DoctorsID ---> Doctor} beacuse it is internally taken by Dieases attribute.

* Patients Table
<div align="center">
 
|PatientID|PatientName|Age|Dieases|
|---------|-------|---|---|
|5001|Rahul|38|alphaviruses|
|5001|Rahul|38|Acute Flaccid Myelitis|
|5002|Sursh|56|Cold|
|5002|Sursh|56|Cancer|
|5003|Ramesh|23|Arthritis|
|5003|Ramesh|23|alphaviruses|
|5004|Neelam|60|Babesios|
|5004|Neelam|60|Cancer|
</div>

* Doctors Table

<div align="center">

|Doctor|Dieases|DoctorID|
|-------|-------|---------|
|Ram|alphaviruses|1001|
|Chavi|Acute Flaccid Myelitis|1004|
|Dhruv|Cold|1002|
|Sambhavita|Cancer|1003|
|Druv|Arthritis|1002|
|Ram|alphaviruses|1001|
|Chavi|Babesios|1004|
|Sambhavita|Cancer|1003|
</div>

* Here, in this we are changing the name of attribute from Dieases to Specialist beacuse initially we assigned the doctors according, in which disease they have mastered and that is not possible in initial tables but now.
* There, is something intresting in the 2nd table(Doctors Table) which is now we have repeating value in table and this is happening beacuse same Docotor is speacialist with the two dieases, we should remove this repeating value form table.

* now, create a new table, having attribute of both the table's primary-key, candidate-key or we can say the attribute on which non-key attributs are dependent. here, PatientID and Dieases.

<div align="center">
 
|PatientID|Dieases|
|---|---|
|5001|alphaviruses|
|5001|Acute Flaccid Myelitis|
|5002|Cold|
|5002|Cancer|
|5003|Arthritis|
|5003|alphaviruses|
|5004|Babesios|
|5004|Cancer|
</div>

* There is one more thing which has to point out that creating a new column has no relation with normaliztion here,

## 3 NF

* Table should be in 2NF.
* There should be no transitive dependencies for non-prime attributes.
  * **Transitive dependencies:** If a non-key field is determined by the value in another non-key. A ---> B ---> C. Here, A, B and C is a non-prime-key.
* **To remove this:**
  * Find the attributes that are transitively dependent.
  * Create seprate table for each of dependencies, A ---> B and B ---> C

<div align="center">

|Doctor|Dieases|DoctorID|
|-------|-------|---------|
|Ram|alphaviruses|1001|
|Chavi|Acute Flaccid Myelitis|1004|
|Dhruv|Cold|1002|
|Sambhavita|Cancer|1003|
|Druv|Arthritis|1002|
|Chavi|Babesios|1004|
</div>

* Now, Check Functional dependecies for each table, and for the Doctors table.
  * DoctorID ---> Doctor
  * Dieases ---> DoctorID
  * Here, Dieases is a candiate key and as well as prime key, DoctorID is not a prime key beacuse column have repeated value.
  * And there is transative functional dependecy, Dieases ---> DoctorID ---> Doctor
  * To remove this create seprate table for each dependency Dieases ---> DoctorID and DoctorID ---> Doctor
  
<div align="center">
 <table>
  <tr><th>Dieases table</th><th>Doctor Table</th></tr>
  <tr>
   <td>

   |Dieases|DoctorID|
   |-------|---------|
   |alphaviruses|1001|
   |Acute Flaccid Myelitis|1004|
   |Cold|1002|
   |Cancer|1003|
   |Arthritis|1002|
   |Babesios|1004|
   </td>
   <td>
    
   |Doctor|DoctorID|
   |-------|---------|
   |Ram|1001|
   |Chavi|1004|
   |Dhruv|1002|
   |Sambhavita|1003|
   |Druv|1002|
   |Chavi|1004|
   </td>
  </tr>
 </table>
</div>
  
* At last create a new table that joins both the tables.

<div align="center">
   
   |Dieseas|DoctorID|
   |-------|---------|
   |alphaviruses|1001|
   |Acute Flaccid Myelitis|1004|
   |Cold|1002|
   |Cancer|1003|
   |Arthritis|1002|
   |Babesios|1004|
</div> 

* Repeat the same procedure for Pateint table.

## Boyce-Codd Normal Form(BCNF)

* It is a new 3NF.
* The table should be in 3NF.
* There should be no overlapping candidate keys.
  * **Overlapping Candidate key:** If we have more then one composit-key and every composit-key have a common attribute, then the keys are called the overlapping candidate keys. eg (A,B) and (A,c)
* **To remove this:**
  * Create seprate table for each unique combination of composit-key's attribute. (A,B), (A,C) and (B,C)

* We know there are other dieases and there is no doctor avaiable to treat it. For the sake of understanding, we are extending Dieases table, you can add these extra attribute from starting of the normalization this will not affect much.

* We know one dieases can be discover by more then one scientist and a dieases can have more then sympotoms and same symptoms can be seen in multiple dieases.

  <div align="center">
   
   |Dieases|DiscoverBY|Symptoms|DoctorID|
   |-------|----------|--------|--------|
   |alphaviruses|Carlos Finlay|body aches|1001|
   |Acute Flaccid Myelitis|Michael Wilson|arm Weakness|1004|
   |Cold|Egyptian|Cough|1002|
   |Cancer|Hippocrates|bleeding|1003|
   |Arthritis|Dr Augustin Jacob|pain|1002|
   |Arthritis|Landré-Beauvais|swelling in joints|1002|
   |Babesios|Victor Babes|arm Weakness|1004|
   |tuberculosis|Victor Babes|pain|None|
  </div>
 
* In this table now, we can't determine any attribute by single attribute, we need composit keys to detemine unique rows.
  * for eg.,{Arthritis, Dr Augustin Jacob} deterimens uniquly a symptom "pain" but "Arthritis" alone can not not determine a single symptom. another example is {Victor Babes, arm Weakness} determines the single dieases "Babesios" but "Victor Babes" alone can not determine a single "dieases" so we need composit keys to determine each row uniqly.
* Here (Dieases, DiscoverBY) and (DiscoverBY, Symptoms) are composit-keys, and each have DiscoverBY attribute common.
* Crate table for each unique combination of composit-key. {(Dieases, DiscoverBY, DoctorID) and (DiscoverBY, Symptoms, DoctorID) }
* What is Composit-key here? it is a candidate-key.
* Note: Every 3NF is BCNF if it's minimal-key(candidate-key) have only 1 attribute.
  
  <div align="center">
 <table>
  <tr><th>Dieases table</th><th>Symptom table</th></tr>
  <tr>
   <td>

   |Dieases|DiscoverBY|DoctorID|
   |-------|----------|--------|
   |alphaviruses|Carlos Finlay|1001|
   |Acute Flaccid Myelitis|Michael Wilson|1004|
   |Cold|Egyptian|1002|
   |Cancer|Hippocrates|1003|
   |Arthritis|Dr Augustin Jacob|1002|
   |Arthritis|Landré-Beauvais|1002|
   |Babesios|Victor Babes|1004|
   |tuberculosis|Victor Babes|None|
   </td>
   <td>
    
   |DiscoverBY|Symptoms|DoctorID|
   |----------|--------|--------|
   |Carlos Finlay|body aches|1001|
   |Michael Wilson|arm Weakness|1004|
   |Egyptian|Cough|1002|
   |Hippocrates|bleeding|1003|
   |Dr Augustin Jacob|pain|1002|
   |Landré-Beauvais|swelling in joints|1002|
   |Victor Babes|arm Weakness|1004|
   |Victor Babes|pain|None|
   </td>
  </tr>
 </table>
</div>

* **Note**: This decomposition may give lossy decomposition, so after 3NF you should always check you get the same dependeency set as before decomposition or not, if not then it will stop here.

## 4 NF

* The table should be in BCNF.
* There should be no multi-valued dependency.
  * **Multi-valued dependencies:** In field A, there is a set of values for both fields B and C but fields B and C are not related.
* **To remove this:**
  * create seprate table for each attribute with field A . (A,B) and (A,C)
 
|Movie|Star|Producer|
|---|---|---|

* Here, A movie can have more then one star and producer, so for each record of tuple there can set of values on Start and Producer column.
* Create seprate table for (Movie,Start) and (Movie,Producer).
  |Movie|Star|
  |---|---|

  |Movie|Producer|
  |---|---|

|DeptCode|ProjectNum|ProjectMgr|Equipment|PropertyID|
|---|---|---|---|---|


## 5 NF

* The table should be in 4NF.
* There should be no cyclic dependency.
  * **Cyclic dependency:** It occures when you have multifield primary-key consisting three of more fields. for example, let's say your primary key consists of fields A, B, C. the cyclic dependency would arise when fields were related in pairs of {A,B}, {B,C} and {C,A}.
* **To remove this:**
  * create seprate table for each of pairs.

|Buyer|Product|Company|
|---|---|---|

* Here, Primary-key consists of all three fileds.
* To eleiminate cyclic redundancy, create seprate table for each pair of fields.
  |Buyer|Product|
  |---|---|

  |Buyer|Company|
  |---|---|

  |Company|Product|
  |---|---|

---

* It is not possible or fesiable to convert a table into it's 4th or 5th or even some cases BCNF beacuse it difficult and costly to maintain.
* As you go higher in normalization you will get more and more tables from a single table.
* A table in 3NF is good. 
