# What are component lifecycle events? 
-Mounting, 

-Updating,

-Unmounting 

are the three phases of the component lifecycle.


![](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp) 



### Mounting
 When an instance of a component is being created and inserted into the DOM it occurs during the mounting phase. Constructor, static getDerivedStateFromProps, render, componentDidMount, and UNSAFE_componentWillMount all occur in this order during mounting.
 
 
 ### Updating 
 
 Anytime a component is updated or state changes then it is rerendered. These lifecycle events happen during updating in this order.
 
 ### Unmounting
 
 The final phase of the lifecycle if called when a component is being removed from the DOM. componentWillUnmount is the only lifecycle event during this phase.
 
 ## componentDidMount() 
 
 This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in componentWillUnmount().
setState() can be called here, but it should be used sparingly, because it will cause a rerender, which can lead to perfomance issues.
Here we use componentDidMount() to connect to the YouTube API and get videos when the components is rendered.


## What types of things can you pass in the props? 

* Things you want to render

* Counters

* Displays of titles of sub-titles

* Displays information

Props passes data into the component (child can’t alter parent data)

state is handeled inside of the component (child can alter parent data)

When do we rerender our application?

When we change the state of that component the comopnent gets rerendered.

What are some examples of things that we could store in state?

input elment check-box select-box





## Things I want to know more about
