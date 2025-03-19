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

## Oracle Database Backup using RMAN

### Backup Database in NOARCHIVELOG Mode

To backup an Oracle Database in NOARCHIVELOG Mode execute the following steps.
Make sure to set 
ORACLE_SID=XE and 
ORACLE_HOME=C:\app\zbook\product\21c\dbhomeXE to to the current CDB$ROOT Container name and include ORACLE_HOME/bin to PATH variable.
Afterwards you are able to execute the following steps.


```
C:\app\zbook\product\21c\dbhomeXE\bin>rman

Recovery Manager: Release 21.0.0.0.0 - Production on Mi Mrz 19 15:02:32 2025
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle and/or its affiliates.  All rights reserved.

RMAN> connect target "/ as sysdba"

mit Zieldatenbank verbunden (nicht gestartet)

RMAN> startup force dba;

Oracle-Instanz gestartet
Datenbank angeschlossen
Datenbank ge├Âffnet

Gesamte System Global Area    1610609432 Byte

Fixed Size                     9855768 Byte
Variable Size               1023410176 Byte
Database Buffers             570425344 Byte
Redo Buffers                   6918144 Byte

RMAN> shutdown immediate;

Kontrolldatei der Zieldatenbank wird anstelle des Recovery-Katalogs verwendet
Datenbank geschlossen
Datenbank nicht angeschlossen
Oracle-Instanz heruntergefahren

RMAN> startup mount

mit Zieldatenbank verbunden (nicht gestartet)
Oracle-Instanz gestartet
Datenbank angeschlossen

Gesamte System Global Area    1610609432 Byte

Fixed Size                     9855768 Byte
Variable Size               1023410176 Byte
Database Buffers             570425344 Byte
Redo Buffers                   6918144 Byte

RMAN> backup
2> device type disk
3> database;

backup wird gestartet bei 19.03.25
Zugewiesener Kanal: ORA_DISK_1
Kanal ORA_DISK_1: SID=621, Ger├ñtetyp=DISK
Kanal ORA_DISK_1: Vollst├ñndiges Backup Set f├╝r Datendatei wird begonnen
Kanal ORA_DISK_1: Datendateien in Backup Set werden angegeben
Dateinummer der Eingabedate=00001, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\SYSTEM01.DBF
Dateinummer der Eingabedate=00003, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\SYSAUX01.DBF
Dateinummer der Eingabedate=00004, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\UNDOTBS01.DBF
Dateinummer der Eingabedate=00007, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\USERS01.DBF
Kanal ORA_DISK_1: Piece 1 wird auf 19.03.25 begonnen
Kanal ORA_DISK_1: Piece 1 auf 19.03.25 beendet
Piece Handle=C:\APP\ZBOOK\PRODUCT\21C\DBHOMEXE\DATABASE\013KOCH6_1_1_1, Tag=TAG20250319T150509, Kommentar=NONE
Kanal ORA_DISK_1: Backupset abgeschlossen, abgelaufene Zeit: 00:00:07
Kanal ORA_DISK_1: Vollst├ñndiges Backup Set f├╝r Datendatei wird begonnen
Kanal ORA_DISK_1: Datendateien in Backup Set werden angegeben
Dateinummer der Eingabedate=00010, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\SYSAUX01.DBF
Dateinummer der Eingabedate=00013, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\APEX01.DBF
Dateinummer der Eingabedate=00009, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\SYSTEM01.DBF
Dateinummer der Eingabedate=00011, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\UNDOTBS01.DBF
Dateinummer der Eingabedate=00015, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\APEX_12176058083270037.DBF
Dateinummer der Eingabedate=00012, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\USERS01.DBF
Dateinummer der Eingabedate=00014, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\XEPDB1\APEX_4800437602748884.DBF
Kanal ORA_DISK_1: Piece 1 wird auf 19.03.25 begonnen
Kanal ORA_DISK_1: Piece 1 auf 19.03.25 beendet
Piece Handle=C:\APP\ZBOOK\PRODUCT\21C\DBHOMEXE\DATABASE\023KOCHD_2_1_1, Tag=TAG20250319T150509, Kommentar=NONE
Kanal ORA_DISK_1: Backupset abgeschlossen, abgelaufene Zeit: 00:00:07
Kanal ORA_DISK_1: Vollst├ñndiges Backup Set f├╝r Datendatei wird begonnen
Kanal ORA_DISK_1: Datendateien in Backup Set werden angegeben
Dateinummer der Eingabedate=00006, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\PDBSEED\SYSAUX01.DBF
Dateinummer der Eingabedate=00005, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\PDBSEED\SYSTEM01.DBF
Dateinummer der Eingabedate=00008, Name=C:\APP\ZBOOK\PRODUCT\21C\ORADATA\XE\PDBSEED\UNDOTBS01.DBF
Kanal ORA_DISK_1: Piece 1 wird auf 19.03.25 begonnen
Kanal ORA_DISK_1: Piece 1 auf 19.03.25 beendet
Piece Handle=C:\APP\ZBOOK\PRODUCT\21C\DBHOMEXE\DATABASE\033KOCHK_3_1_1, Tag=TAG20250319T150509, Kommentar=NONE
Kanal ORA_DISK_1: Backupset abgeschlossen, abgelaufene Zeit: 00:00:03
backup wurde beendet bei 19.03.25

Control File and SPFILE Autobackup wird gestartet bei 19.03.25
Piece Handle=C:\APP\ZBOOK\PRODUCT\21C\DBHOMEXE\DATABASE\C-3065698935-20250319-00, Kommentar=NONE
Control File and SPFILE Autobackup wurde beendet bei 19.03.25

RMAN> alter database open;

Anweisung verarbeitet
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
