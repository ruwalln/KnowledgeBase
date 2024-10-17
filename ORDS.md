#### PUBLIC USER ORDS_PUBLIC_USER has been expired 

Error Message starting ords service.

Verbindung zu Benutzer: ORDS_PUBLIC_USER URL: jdbc:oracle:thin:@//localhost:1521/XEPDB1 konnte nicht hergestellt werden
ORA-28001: Kennwort ist abgelaufen

HowTo fix this
---------------

1. Logon to the database using an administrative accout like SYS AS SYSDBA

```
C:\app\zbook\product\ords23\bin>sqlplus sys as sysdba

SQL*Plus: Release 21.0.0.0.0 - Production on Do Okt 17 13:10:02 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.

Kennwort eingeben:

Verbunden mit:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL>
```

2. Check the Container for the Session of SYS

```
SQL> show con_name

CON_NAME
------------------------------
CDB$ROOT
```

3. Change Session using the Container for APEX and ORDS_PUBLIC_USER

```
SQL> alter session set container=xepdb1
  2  /

Session wurde geõndert.
```

4. Check Users from Database xepdb1 like APEX or ORDS for EXPIRED

```
select username, account_status from dba_users where username like '%ORD%' where account_status like '%EXPIRED%'

USERNAME                     ACCOUNT_STATUS   PASSWORD
---------------------------- --------------- -------------------------------------
ORDS_PUBLIC_USER             EXPIRED

SQL>
```

5. ALTER Username password using the DBMS_METADATA.GET_DDL Function

```
set long 1000000
exec dbms_output.enable(1000000)

SELECT DBMS_METADATA.get_ddl ('USER', 'ORDS_PUBLIC_USER')
FROM DUAL
/

DBMS_METADATA.GET_DDL('USER','ORDS_PUBLIC_USER')
--------------------------------------------------------------------------------

   CREATE USER "ORDS_PUBLIC_USER" IDENTIFIED BY VALUES 'S:E96ABD740AC15679E68BEA
C8C43C1D38775B90693488A52483FE3CF02864;T:306302E4C7FB2645954E1256A96AA90F622222B
0B61AFA3F731024B531732796CEF4C1A04ABA58297BE8A4285F4FEBE914F06FB321416CA232BD850
588337034063652D5EB65F205B0ED861E11371E48'
      DEFAULT TABLESPACE "SYSAUX"
      TEMPORARY TABLESPACE "TEMP"
      PASSWORD EXPIRE

SQL>alter user "ORDS_PUBLIC_USER" IDENTIFIED BY VALUES 'S:E96ABD740AC15679E68BEAC8C43C1D38775B90693488A52483FE3CF02864;T:306302E4C7FB2645954E1256A96AA90F622222B0B61AFA3F731024B531732796CEF4C1A04ABA58297BE8A4285F4FEBE914F06FB321416CA232BD850588337034063652D5EB65F205B0ED861E11371E48'
/

Benutzer wurde geõndert.

SQL>
```
