# JavaFX HowTos 

## Requirements to compile and run a JavaFX Programm

### Compile a JavaFX Program

- no classpath directive

```
C:\app\zbook\product\jdk-21.0.6\bin\javac --module-path "C:\app\zbook\product\javafx-sdk-21.0.5\lib" --add-modules javafx.controls,javafx.fxml,javafx.graphics "C:\Users\zbook\eclipse-workspace\HelloJavaFX\src application.Main.java
```

- classpath directive
  
```
C:\app\zbook\product\jdk-21.0.6\bin\javac --module-path "C:\app\zbook\product\javafx-sdk-21.0.5\lib" --add-modules javafx.controls,javafx.fxml,javafx.graphics -classpath "C:\Users\zbook\eclipse-workspace\HelloJavaFX\bin" Main.java HelloJavaFXController.java
```

### Execution of JavaFX Classes 

```
C:\app\zbook\product\jdk-21.0.6\bin\javaw.exe --module-path "C:\app\zbook\product\javafx-sdk-21.0.5\lib" --add-modules javafx.controls,javafx.fxml,javafx.graphics -Dfile.encoding=UTF-8 -Dstdout.encoding=UTF-8 -Dstderr.encoding=UTF-8 -classpath "C:\Users\zbook\eclipse-workspace\HelloJavaFX\bin" -XX:+ShowCodeDetailsInExceptionMessages application.Main
```

```
C:\app\zbook\product\jdk-21.0.6\bin\javaw.exe --module-path "C:\app\zbook\product\javafx-sdk-21.0.5\lib" --add-modules javafx.controls,javafx.fxml,javafx.graphics -Dfile.encoding=UTF-8 -Dstdout.encoding=UTF-8 -Dstderr.encoding=UTF-8 -classpath "C:\Users\zbook\eclipse-workspace\HelloJavaFX\src" -XX:+ShowCodeDetailsInExceptionMessages application.Main
```
