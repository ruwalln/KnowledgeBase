# Java Development Platform Installation

## Install Netbeans24 from Apache Group

First download Netbeans Java Application from Apache Group Website.
URL: https://www.apache.org/dyn/closer.lua/netbeans/netbeans/24/netbeans-24-bin.zip

Afterwards unzip the zip archive netbeans-24-bin.zip to a destination program folder of your choice.
If done, execute Netbeans using the following command line syntax:

```
cd c:\app\zbook\product\netbeans\bin
netbeans64 --jdkhome C:\app\zbook\product\jdk-21.0.6 --console new
```


## Java HowTo

### useful Methods

```
String.concat("Text");

String names[]={"John","Peter","Mary","Duke"};
for(int i: names){
 <code-block>; // executes codeblock in a loop variable i for every element of array names.
}
```

### Right or Left Pad a string with 0  or spaces

```
String.format("%10s", "foo").replace(' ', '*');
String.format("%-10s", "bar").replace(' ', '*');
String.format("%10s", "longer than 10 chars").replace(' ', '*');
```
### scan a Number Array for max or min Value

```
int max_x = Arrays.stream(x)
   .max()
   .getAsInt();
```
### StringBuilder add Spaces to a variable

```
// build an empty 225 char string

      int numberOfSpaces = 225;
      StringBuilder sb = new StringBuilder(numberOfSpaces);
      for (int i = 0; i < numberOfSpaces; i++) {
            sb.append(' ');
      }
```
### Compare a String value of two String Arrays

```
        for (x=0;x<val.length;x++){             
            for(y=0;y<args.length;y++){
                if(val[x].equals(args[y])){
                    System.out.println(args[y]+" gefunden");
                }                   
            }       
        }
```

