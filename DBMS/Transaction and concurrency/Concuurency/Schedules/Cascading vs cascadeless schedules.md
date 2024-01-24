#  Cascadeless vs Cascading schedules


<p align="center">
  <img src="" />
</p>

<div align="center">
  
|Cascadeless|Cascading|
|---|---|
|A schedule in which if a transaction fails then no transactions has to rollback.|A schedule in which if a trasaction $T_i$ fails then other transactions who reads the dirty value of $T_i$ has to rollback.|
|To avoid the problem of cascading don't allow the transactions to read the vale until or unless T1 complete its transactons and commit.|IF T1 fails due to any reason all the transactions who are using the same data item will abost beacuse of reading dirty value.|

</div>
