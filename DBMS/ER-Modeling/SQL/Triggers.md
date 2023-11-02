## Triggers

Triggers are precompiled procedure that are stored along with database and invoked whenever a certain condition occur.


**Syntax**

    CREATE TRIGGER {trigger_name}
    {BEFORE, AFTER, INSTEAD OF} {INSERT, DELETE, UPDATE} ON {table_name}
    FOR EACH ROW
    BEGIN
      {SQL statement}
    END;


eg.

    CREATE VIEW hydrabad_supplier 
    AS SELECT supplier_number, supplier_name, status FROM Supplier 
    WHERE city = "hydrabad";


Here, HYDERABAD_SUPPLIER is a view table

    CREATE TRIGGER hydrabad_supplier 
    INSTEAD OF INSERT ON HYDRABAD_SUPPLIER 
    REFERENCING NEW ROW AS R
    FOR EACH ROW
    BEGIN
        INSERT INTO Supplier (Supplier_number, Supplier_name, status, city)
        VALUES (R.Supplier_number, R.Supplier_name, R.status, 'Hyderabad');
    END;


with this trigger whenever an insertion is attempted on the HYDRABAD_SUPPLIER view, the trigger will be activated and corresponding data will be inserted into the supplier table with the city value set to "hyderabad" and rest will be same
