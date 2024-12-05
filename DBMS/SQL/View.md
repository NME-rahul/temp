# View
* View in SQl are a kind of virtual tabe. A view also has rows and columns like tables, but a view doesn't take physical space to store table.
* View Defines a customized query that retrieves data from one or more tables, and repersents the data as if ir was coming from a single source.

#### Advantages of View

1. Restricting data access: Views provide an additional level of table security by restricting access to a original soruce.
2. Hiding data Complexity: A view can hide the complexity that exists in multiple joined tables.
3. Simplfy commands for the use: Views can be used to store complex queries.
4. Rename columns: Views can also be used to rename the columns without affecting the base table.
5. They provide data independency.

<div></div>

    CREATE VIEW <view_name> AS <query>

* For every query a new View is created.

<div></div>

    CREATE VIEW book
    (SELECT price, title FROM Supplier)
    SELECT title FROM book WHERE price > 100;

* It first creates view named book having two attributes price and title and then selects title of the book having price greater then 100.

* It is not neccesary that we use only single table but also we can join multiple and can create view.
