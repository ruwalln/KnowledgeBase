# Oracle User Profile usage 

Display all existing Database User Profile

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
There are only two Resource Types available : PASSWORD and KERNEL
