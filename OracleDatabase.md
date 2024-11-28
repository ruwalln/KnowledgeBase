# ORACLE DATABASE Knowledge

## Check Requirements


In an ORACLE Linux environment please check the following assigments in the environment before connecting to an Oracle Database.

oracle@host$ id <enter>
uid=54321(oracle), gid=54321(oinstall), groups=54321(oinstall), 54322(dba), 54323(oper), 54324(backupdba), 54325(dgdba), 54326(kmdba), 54330(racdba) 

To select an Oracle Instance for your current environment please use the oraenv script

oracle@host$ . oraenv



## ORACLE Database Connection Types

- Operating System Authentication

```
C:\>sqlplus / as sysdba

SQL*Plus: Release 21.0.0.0.0 - Production on Do Nov 28 10:59:46 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.


Verbunden mit:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL>

```

- Easy Connect Syntax (no configuration files needed)

```
C:\>sqlplus /nolog

SQL*Plus: Release 21.0.0.0.0 - Production on Do Nov 28 11:01:49 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.

SQL> connect system/manager@localhost:1521/xepdb1
Connect durchgef├╝hrt.
SQL>
```



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
