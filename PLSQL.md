# ORACLE - PL/SQL inside 

Create or Replace a function written in PL/SQL
condition is to pass two parameters date1, date2 and compare if date1 is greater than date2.
IF true the function RETURN VARCHAR2 'TRUE' OR 'FALSE'

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
