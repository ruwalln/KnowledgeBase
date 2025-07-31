# HowTo's using ORACLE LINUX 8

### HowTo use X11 applications on OEL8 on local machine using X11 GUI

user1 = root

```
xauth list $DISPLAY
oracle8linux1.localdomain/unix:  MIT-MAGIC-COOKIE-1  731f4bc2114420b228cb6a2ec58e2c54 <-- use this hex key for authorization

echo $DISPLAY
:0
```

user2 = oracle

```
DISPLAY=:0; export DISPLAY
xauth add $DISPLAY . 731f4bc2114420b228cb6a2ec58e2c54
```
Now you are able to start X11 applications using user2 authorization.



