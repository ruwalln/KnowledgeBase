# Oracle Database Profiles 

## Table : DBA_PROFILES

| Name  |  Null? |  Typ  |         
| ----- | ------ | ----- | 
| PROFILE |          NOT NULL | VARCHAR2(128) |
| RESOURCE_NAME |    NOT NULL | VARCHAR2(32)  |
| RESOURCE_TYPE  |            | VARCHAR2(8)   |
| LIMIT   |                   | VARCHAR2(257) |
| COMMON   |                  | VARCHAR2(3)   |
| INHERITED |                 | VARCHAR2(3)   |
| IMPLICIT   |                | VARCHAR2(3)   |
| ORACLE_MAINTAINED |         | VARCHAR2(3)   |
| MANDATORY   |               | VARCHAR2(3)   |


Display all existing Database User Profiles.
In most cases the default database profile is 'DEFAULT'.
There are only two Resource Types available : PASSWORD and KERNEL

PASSWORD Resource Names are used to limit :

| RESOURCE_NAME | VALUES |
| ------------- | ------ |
| FAILED_LOGIN_ATTEMPTS |  |
| PASSWORD_LIFE_TIME |  |
| PASSWORD_REUSE_TIME |  |
| PASSWORD_REUSE_MAX |  |
| PASSWORD_VERIFY_FUNCTION |  |
| PASSWORD_LOCK_TIME |  |
| PASSWORD_GRACE_TIME |  |
| INACTIVE_ACCOUNT_TIME |  |
| PASSWORD_ROLLOVER_TIME |  |


```
SELECT DISTINCT PROFILE
FROM DBA_PROFILES

```

Display a specific Database User Profile

```
SELECT PROFILE,
       RESOURCE_NAME,
       LIMIT
FROM DBA_PROFILES
WHERE RESOURCE_TYPE='PASSWORD'
AND PROFILE='DEFAULT'
ORDER BY PROFILE,
         RESOURCE_NAME
```


