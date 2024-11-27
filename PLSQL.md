# ORACLE - PL/SQL inside 

Create or Replace a procedure written in PL/SQL

```
CREATE OR REPLACE PROCEDURE check_date (date1 in DATE)
IS
-- DECLARE
BEGIN
   IF (TRUNC(sysdate) > TO_DATE('01.01.2024','DD.MM.YYYY')) 
   THEN
      dbms_output.put_line('TRUE');
   ELSE
      dbms_output.put_line('FALSE');
   END IF;
END;
```
