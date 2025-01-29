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

### Right or Left Pad a string with 0  or spaces

```
String.format("%10s", "foo").replace(' ', '*');
String.format("%-10s", "bar").replace(' ', '*');
String.format("%10s", "longer than 10 chars").replace(' ', '*');
```
