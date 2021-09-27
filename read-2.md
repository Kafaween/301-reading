# The statement order is as follows.

1-Package statment (optional).

2-Imports (optional).

3-Class or interface definitions.

# examples of imports

* import javax.swing.*; ----------------       *Make all classes visible altho only one is used.*

* import javax.swing.JOptionPane; ------------------  *Make a single class visible.*

* Alternately we can the fully qualified class name without an import.

``` class ImportTest {
    public static void main(String[] args) {
        javax.swing.JOptionPane.showMessageDialog(null, "Hi");
        System.exit(0);
    }
}
```

## Common cases 

* import java.awt.*;	Common GUI elements.
* import java.awt.event.*;	The most common GUI event listeners.
* import javax.swing.*;	More common GUI elements. Note "javax".
* import java.util.*;	Data structures (Collections), time, Scanner, etc classes.
* import java.io.*;	Input-output classes.
* import java.text.*;	Some formatting classes.
* import java.util.regex.*;	Regular expression classes.


# Loops

### there are 4 types of loops in java:
* Simple for loop
* Enhanced for-each loop
* While loop
* Do-While loop

## For Loop :A for loop is a control structure that allows us to repeat certain operations by incrementing and evaluating a loop counter.
``` for (int i = 0; i < 5; i++) {
    System.out.println("Simple for loop: i = " + i);
} 
```

## While Loop:The while loop is Java's most fundamental loop statement. It repeats a statement or a block of statements while its controlling Boolean-expression is true.

``` int i = 0;
while (i < 5) {
    System.out.println("While loop: i = " + i++);
}
```

## Do-While Loop : The do-while loop works just like the while loop except for the fact that the first condition evaluation happens after the first iteration of the loop.

``` int i = 0;
do {
    System.out.println("Do-While loop: i = " + i++);
} while (i < 5); 
```
