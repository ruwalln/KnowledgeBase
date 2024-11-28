# ORACLE DATABASE Knowledge

## Scripts Section - Using Dynamic Performance View

### V$DATABASE

```
-- using V$DATABASES

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

### V$CONTAINERS

```
select CON_ID
,DBID
,GUID
,NAME
,OPEN_MODE
,RESTRICTED
,OPEN_TIME
,TOTAL_SIZE
,BLOCK_SIZE
,RECOVERY_STATUS
,MAX_SIZE
from v$containers

    CON_ID       DBID GUID                             NAME
                        OPEN_MODE  RES OPEN_TIME                                                                   TOTAL_SIZE BLOCK_SIZE RECOVERY_STATUS              MAX_SIZE
---------- ---------- -------------------------------- -------------------------------------------------------------------------------------------------------------------------------- ---------- --- --------------------------------------------------------------------------- ---------- ---------- -------------------------- ----------
         3  603957675 285C0940E59F44E486EDE8D6B615D937 XEPDB1
                        READ WRITE NO  28.11.24 10:03:11,775 +01:00                                                1928462336       8192 ENABLED
             0

```
