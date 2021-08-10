# In memory storage

## Understanding the JavaScript Call Stack.

> The call stack is primarily
> used for function invocation (call)
## What is a ‘call’?

 a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

## How many ‘calls’ can happen at once?


## What does LIFO mean?

operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

## Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

![]([https://miro.medium.com/max/437/1*rLV0q6if8Drx1PbrncybXw.png])

## What causes a Stack Overflow?

occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

# JavaScript error messages

## What is a ‘refrence error’?

## What is a ‘syntax error’?

occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse,this can be solved by just fixing the syntax

## What is a ‘range error’?

is thrown when trying to pass a value as an argument to a function that does not allow a range that includes the value

## What is a ‘tyep error’?

Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

## What is a breakpoint?

You can also add conditional breakpoints by right-clicking a previous set breakpoint, which will make your program stop at that point only if a condition is met, this is awesome for when you want to debug huge cycles for specific values

## What does the word ‘debugger’ do in your code?

console.log() for example.

##  Things I want to know more about
