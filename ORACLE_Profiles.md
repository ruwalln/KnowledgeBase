# Oracle Database Profiles 

Display all existing Database User Profiles.
In most cases the default database profile is 'DEFAULT'.
There are only two Resource Types available : PASSWORD and KERNEL

PASSWORD Resource Type are used to limit :

| RESOURCE_TYPE | VALUES |
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
| ------------- | ------ |

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


