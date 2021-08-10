# Functional Programming Concepts

## What is functional programming?

a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia

## What is a pure function and how do we know if something is a pure function?

It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects

## What are the benefits of a pure function?

The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts.

## What is immutability?

Unchanging over time or unable to be changed.
When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

## What is Referential transparency?

pure functions + immutable data = referential transparency

# Modules and require()

## What is a module?

is a software component or part of a program that contains one or more routines. ... Modules make a programmer's job easy by allowing the programmer to focus on only one area of the functionality of the software application. Modules are typically incorporated into the program (software) through interfaces.

## What does the word ‘require’ do?

in Node. js, it's a built-in function with a special purpose: to load modules. Modules are a way to split an application into separate files instead of having all of your application in one file.

## How do we bring another module into the file the we are working in?

You can include functionality from other modules in any other module. To do so is referred to as "requiring" the module, which is simply calling for a certain special object representing the functionality of the module.

``` module.exports.temperature = temperature; ```
## What do we have to do to make a module available?
 we need Node.js and npm installed on your development environment.
 
 ## Things I want to know more about 
