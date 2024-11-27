# ORACLE - PL/SQL inside 

Create or Replace a procedure written in PL/SQL

```
CREATE OR REPLACE PROCEDURE check_date (date1 IN DATE, date2 IN DATE)
IS
-- DECLARE
BEGIN
   IF (TRUNC(date1) > TRUNC(date2)) 
   THEN
      dbms_output.put_line('TRUE');
   ELSE
      dbms_output.put_line('FALSE');
   END IF;
END;
```
