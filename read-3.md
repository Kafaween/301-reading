### Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a 
reference type.

### Every object contains a single value of the corresponding primitive type. The wrapper classes are immutable (so that their state can't change once the object is constructed) and are final (so that we can't inherit from them). 

``` 
Integer j = 1;          // autoboxing
int i = new Integer(1); // unboxing

```


### The situation becomes more interesting if we compare how much memory occupy arrays of the types under consideration.

When we create arrays with the various number of elements for every type, we obtain a plot:

![](https://www.baeldung.com/wp-content/uploads/2018/08/plot-memory-bits.gif)


### The performance of a Java code is quite a subtle issue, it depends very much on the hardware on which the code runs, on the compiler that might perform certain optimizations, on the state of the virtual machine, on the activity of other processes in the operating system.

### compare the performance of this operation for the case when the array contains variables of the primitive types and for the case when it contains objects of the reference types.

![](https://www.baeldung.com/wp-content/uploads/2018/08/plot-benchmark-primitive-wrapper-3.gif)

## What Is an Exception?

An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.

Valid Java programming language code must honor the Catch or Specify Requirement. This means that code that might throw certain exceptions must be enclosed by either of the following:

A try statement that catches the exception. The try must provide a handler for the exception,

## Example on how to throw an Exceptions

```
public Object pop() {
    Object obj;

    if (size == 0) {
        throw new EmptyStackException();
    }

    obj = objectAt(size - 1);
    setObjectAt(size - 1, null);
    size--;
    return obj;
}
```

## Advantage of Exceptions

The use of exceptions to manage errors has some advantages over traditional error-management techniques

## Scanning

Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.
