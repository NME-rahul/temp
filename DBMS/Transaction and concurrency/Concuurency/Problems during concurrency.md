## Problems during Concurrent execution

There are three main problems

1. Lost updates
2. Dirty Read / Uncommited data
3. Phantom Read problem
4. Unrepeatable Read problem

### Lost updates

* This problem occures when two transaction working on same data updates the records at the same time.
* The first transaction updates the recored and then second transaction updates the records again. 

<p align="center">
  <img height="350px" width="400px" src="https://github.com/NME-rahul/temp/assets/100432854/be791aee-e747-497e-b842-e7c9edc46069" />
</p>


### Dirty read problem

* It occurs when a transaction reads the data has been updated by another transaction that is still uncommited.

<div align="center">

|Time|A|B|
|----|---|---|
|T1|READ(X)|--|
|T2|X = x + 500|---|
|T3|WRITE(X)|---|
|T4|---|READ(X)|
|T5|---|COMMIT|
|T6|ROLLBACK|---|
</div>


### Phantom Read problem

* THe phantom read problem occurs when a transaction reads a variable once but when it tries to read the same variable again, an error occurs saying that the variable does not exist.

<div align="center">
  
|Time|A|B|
|---|---|---|
|T1|READ(X)|---|
|T2|---|READ(X)|
|T3|DELETE(X)|---|
|T4|---|READ(X)|
</div>

* Transaction B face the problem of phantom read when it reads X at T4.

### Unrepeatable Read problem

* THE unrepeatable read problem ocuurs when two or more different values of the same data are read during operation.

* Let the initial value of x is 1000

<div align="center">

|Time|A|B|
|---|---|---|
|T1|READ(X)|---|
|T2|---|READ(X)|
|T3|X=X+500|---|
|T4|WRITE(X)|---|
|T5|---|READ(X)|
</div>

* B initially read the 1000 but after updation by A it reads the value 1500.
