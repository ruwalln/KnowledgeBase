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



