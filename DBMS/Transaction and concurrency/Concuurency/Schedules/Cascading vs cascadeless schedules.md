# Cascading vs Cascadeless schedules


<p align="center">
  <img src="" />
</p>

<div align="center">
  
|Cascading|Cascadeless|
|---|---|
|To avoid the problem of cascading don't allow the transactions to read the vale until or unless T1 complete its transactons and commit.|IF T1 fails due to any reason all the transactions who are using the same data item will abost beacuse of reading dirty value.|

</div>
