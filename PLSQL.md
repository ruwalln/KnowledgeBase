# ORACLE - PL/SQL inside 

Create or Replace a procedure written in PL/SQL

```
CREATE OR REPLACE FUNCTION apex_labs.check_date (
                 date1 IN DATE, 
                 date2 IN DATE )
RETURN VARCHAR2 IS
-- DECLARE
BEGIN
   IF (TRUNC(date1) > TRUNC(date2)) 
   THEN
      RETURN 'TRUE';
   ELSE
      RETURN 'FALSE';
   END IF;
END;
```
