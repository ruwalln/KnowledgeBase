# ORACLE DATABASE Knowledge

## Scripts Section - Using Dynamic Performance View

```
select DBID
, NAME
, CREATED
, LOG_MODE
, OPEN_MODE
, CURRENT_SCN
, FLASHBACK_ON
, CDB
 , CON_ID
from v$database
/

SQL> set lines 1000
SQL> /

      DBID NAME      CREATED  LOG_MODE     OPEN_MODE            CURRENT_SCN FLASHBACK_ON       CDB     CON_ID
---------- --------- -------- ------------ -------------------- ----------- ------------------ --- ----------
3065698935 XE        09.11.24 NOARCHIVELOG READ WRITE               9251639 NO                 YES          0

```


