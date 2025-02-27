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
### Compare a String value of two String Arrays using String.equals

```
        for (x=0;x<val.length;x++){             
            for(y=0;y<args.length;y++){
                if(val[x].equals(args[y])){
                    System.out.println(args[y]+" gefunden");
                }                   
            }       
        }
```

### Save a Java TreeModel to Disk (serializable)

```
import javax.swing.tree.DefaultTreeModel;
import javax.swing.tree.DefaultMutableTreeNode;
import java.io.FileOutputStream;
import java.io.ObjectOutputStream;
import java.io.IOException;

public class TreeModelSaver {

    public static void saveTreeModel(DefaultTreeModel treeModel, String filePath) {
        try (FileOutputStream fileOut = new FileOutputStream(filePath);
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(treeModel);
            System.out.println("TreeModel has been serialized to " + filePath);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    public static void main(String[] args) {
        // Example usage
        DefaultMutableTreeNode root = new DefaultMutableTreeNode("Root");
        DefaultMutableTreeNode child1 = new DefaultMutableTreeNode("Child 1");
        DefaultMutableTreeNode child2 = new DefaultMutableTreeNode("Child 2");
        root.add(child1);
        root.add(child2);

        DefaultTreeModel treeModel = new DefaultTreeModel(root);
        saveTreeModel(treeModel, "treeModel.ser");
    }
}
```

### Load a Java TreeModel from Disk (serializable)

```
import javax.swing.tree.DefaultTreeModel;
import java.io.FileInputStream;
import java.io.ObjectInputStream;
import java.io.IOException;

public class TreeModelLoader {

    public static DefaultTreeModel loadTreeModel(String filePath) {
        DefaultTreeModel treeModel = null;
        try (FileInputStream fileIn = new FileInputStream(filePath);
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            treeModel = (DefaultTreeModel) in.readObject();
            System.out.println("TreeModel has been deserialized from " + filePath);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
        return treeModel;
    }

    public static void main(String[] args) {
        // Example usage
        DefaultTreeModel treeModel = loadTreeModel("treeModel.ser");
        // Use the treeModel as needed
    }
}

```

### Scroll thru a complete JTree Model visit all available nodes

```
public static void visitAllNodes(JTree tree) {
        TreeNode root = (TreeNode) tree.getModel().getRoot();
        visitAllNodes(root);
    }

    public static void visitAllNodes(TreeNode node) {
        System.out.println(node);
        if (node.getChildCount() >= 0) {
            for (Enumeration e = node.children(); e.hasMoreElements();) {
                TreeNode n = (TreeNode) e.nextElement();
                visitAllNodes(n);
            }
        }
    }
```
