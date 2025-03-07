# ORACLE DATABASE Knowledge

## Check Requirements


In an ORACLE Linux environment please check the following assigments in the environment before connecting to an Oracle Database.

oracle@host$ id <enter>
uid=54321(oracle), gid=54321(oinstall), groups=54321(oinstall), 54322(dba), 54323(oper), 54324(backupdba), 54325(dgdba), 54326(kmdba), 54330(racdba) 

To select an Oracle Instance for your current environment please use the oraenv script to the the following environment variables before.

ORACLE_HOME
ORACLE_SID

oracle@host$ . oraenv

## How to use SQLCl using an Windows environment

First download the current version of SQLCl from the Oracle Website 
decompress the file into an directory inside a Users local APP folder for example : C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib
We assume all other Oracle Tools from the User are stored here C:\Users\zbook\app\oracle\tools
To execute the current SQLCl Client you have to make C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin as a current directory.
Now you have to set the env variable 

SET LD_LIBRARY_PATH=C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib

Afterwards you are able to execute SQL.EXE inside the folder C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin as shown in the example.

- The current ORACLE_HOME is C:\app\zbook\product\21c\dbhomeXE
- The PATH variable includes C:\app\zbook\product\21c\dbhomeXE\bin folder to execute Oracle executables.
- Changes diectory to C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin
- SET LD_LIBRARY_PATH=C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib
- execute SQL.EXE from C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin folder
- you are done

Example for executing SQLCl in a Microsoft Windows Environment

```
c:\>SET ORACLE_HOME=C:\app\zbook\product\21c\dbhomeXE

c:\>cd %ORACLE_HOME%

C:\app\zbook\product\21c\dbhomeXE>cd C:\Users\zbook\app\oracle\tools

C:\Users\zbook\app\oracle\tools>dir
 Volume in Laufwerk C: hat keine Bezeichnung.
 Volumeseriennummer: 5E15-AA2F

 Verzeichnis von C:\Users\zbook\app\oracle\tools

12.11.2024  10:36    <DIR>          .
12.11.2024  10:36    <DIR>          ..
25.11.2023  11:25    <DIR>          datamodeler
12.11.2024  10:36    <DIR>          sqlcl-24.2.0.180.1721
12.11.2024  10:35        68.708.889 sqlcl-24.2.0.180.1721.zip
28.11.2023  13:49    <DIR>          sqldeveloper-22.2.1
28.11.2023  13:27    <DIR>          sqldeveloper21.4.3
               1 Datei(en),     68.708.889 Bytes
               6 Verzeichnis(se), 110.796.472.320 Bytes frei

C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721>cd C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib

C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib>set LD_LIBRARY_PATH=C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib

C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\lib>cd C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin

C:\Users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin>sql / as sysdba
Copyright (c) 1982, 2024, Oracle. All rights reserved. Alle Rechte vorbehalten.

Verbunden mit:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL> set sqlformat csv
SQL> select * from dual
  2* /
"DUMMY"
"X"

```


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
- Show current container


```
SQL> show con_name

CON_NAME
------------------------------
XEPDB1

```
- Show current PDBS exists in the container

```
SQL> show pdbs

    CON_ID CON_NAME                       OPEN MODE  RESTRICTED
---------- ------------------------------ ---------- ----------
         2 PDB$SEED                       READ ONLY  NO
         3 XEPDB1                         READ WRITE NO
```


## Scripts Section - Using Dynamic Performance View

### Display all existing Dynamic Performance Views in CDB

To display all available Dynamic Peformance Views in the CDB please query the data-dictionary and the table V$FIXED_TABLE.

### V$FIXED_TABLE

```
select *
from V$FIXED_TABLE
where name like 'V$%'
order by name
/
```

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
