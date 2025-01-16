# Oracle 21c - Multitenant Adminsitration

## Connect to a Oracle multitenant Database Environment

Move into ORACLE_HOME/bin Folder and execute SQLPLUS to Login into Oracle Database.

```
UNIX : 

cd $ORACLE_HOME/bin
sqlplus / as sysdba

Windows :

cd %ORACLE_HOME%\bin
sqlplus / as sysdba

```

### Get informations about current container database, application containers and all pluggable databases.

- The current container can be CDB$ROOT (CDB root) only for common users.
- The current container can be a specific PDB for common users and local users.
- The current container can be an application root only for common users or for application common users created in the application root.
- The current container can be a specific application PDB for common users, application common users, and local users.
- The current container must be the CDB root or an application root when a SQL statement includes CONTAINER = ALL.
- You can include the CONTAINER clause in several SQL statements, such as the CREATE USER, ALTER USER, CREATE ROLE, GRANT, REVOKE, and ALTER SYSTEM statements. Note the following rules about CONTAINER = ALL:
- When a SQL statement includes CONTAINER = ALL and the current container is the CDB root, the SQL statement affects all containers in the CDB, including all PDBs, application roots, and application PDBs.
- When a SQL statement includes CONTAINER = ALL and the current container is an application root, the SQL statement affects all containers in the application container, including the application root and all the application PDBs that belong to the application root. The SQL statement does not affect the CDB root or any PDBs or application PDBs that do not belong to the current application root.
- Only a common user or application common user with the commonly granted SET CONTAINER privilege can run a SQL statement that includes CONTAINER = ALL.

### Show current container

```
SQL> SHOW CON_NAME
CDB$ROOT

SQL> SHOW CON_ID
1

SQL> SELECT SYS_CONTEXT ('USERENV', 'CON_NAME') FROM DUAL;
CDB$ROOT

SQL> show pdbs

    CON_ID CON_NAME                       OPEN MODE  RESTRICTED
---------- ------------------------------ ---------- ----------
         2 PDB$SEED                       READ ONLY  NO
         3 XEPDB1                         READ WRITE NO
```

### Display all existing databases in a multitenant environment.

```
SET ECHO OFF
SET PAGES 1000
SET LINESIZE 1000
COLUMN CON_ID FORMAT 999
COLUMN DBID FORMAT 9999999999999
COLUMN NAME FORMAT A10
COLUMN OPEN_MODE FORMAT A15
COLUMN PDB_COUNT FORMAT 999
SELECT CON_ID, DBID,NAME, OPEN_MODE, PDB_COUNT
FROM V$CONTAINERS
/

CON_ID           DBID NAME       OPEN_MODE       PDB_COUNT
------ -------------- ---------- --------------- ---------
     1     3065698935 CDB$ROOT   READ WRITE              1
     2     2402705404 PDB$SEED   READ ONLY               0
     3      603957675 XEPDB1     READ WRITE              0

```
