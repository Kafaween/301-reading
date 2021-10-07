# Stacks

A stack is an abstract data type that holds an ordered, linear sequence of items. In contrast to a queue, a stack is a last in, first out (LIFO) structure. A real-life example is a stack of plates: you can only take a plate from the top of the stack, and you can only add a plate to the top of the stack. If you want to reach a plate that is not on the top of the stack, you need to remove all of the plates that are above that one. In the same way, in a stack data structure, you can only access the element on the top of the stack. The element that was added last will be the one to be removed first. Therefore, to implement a stack, you need to maintain a pointer to the top of the stack (the last element to be added).



The stack is a linear data structure that is used to store the collection of objects. In other words it used to store `Nodes`.

## Common terminology for a stack is

1. **Push** Nodes or items that are put into the stack are **pushed**.

2. **Pop** Nodes or items that are removed from the stack are **popped**. When you attempt to pop an empty stack an exception will be raised.

3. **Top** This is the top of the stack.

4. **Peek** When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

5. **IsEmpty** returns true when stack is empty otherwise returns false.

## Concepts:

* **FILO**: First In Last Out. That means the first item added in the stack will be the last item go out of the collection.

* **LIFO**: Last In First Out. That means the last item added in the stack will be the first item go out of the collection.

* **Stack Visualization**: When **push** (add item) something to stack it becomes the new `top` and when **pop** (remove item) that means remove cuurent `top` and set the next `top` as `top.next`.

* **Push O(1)**: Add a new node to the top of stack. 

* **Pop O(1)**: Remove the node from the top of the stack.

* **Peek O(1)**: When conducting a `peek`, you will only be inspecting the `top` Node of the stack.

![stacks data structure](https://static.studytonight.com/data-structures/images/stack-data-structure.png)

# What is a Queue

## Common terminology for a queue is

1. **Enqueue** Nodes or items that are added to the queue.

2. **Dequeue** Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.

3. **Front** This is the front/first Node of the queue.

4. **Rear**  This is the rear/last Node of the queue.

5. **Peek**  When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.

6. **IsEmpty** returns true when queue is empty otherwise returns false.

## Concepts:

* **FIFO**: First In First Out. That means the first item added in the queue  will be the first item go out of the collection.

* **LILO**: Last In Last Out. That means the last item added in the queue will be the Last item go out of the collection.

![queue data structure](https://www.tutorialandexample.com/wp-content/uploads/2020/05/Queue-in-DS-1.jpg)
