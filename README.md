# Front-End Interview Questions with a focus on React library

### What is React? 

It is a JavaScript library for building User Interfaces. 

### What is a React Element? 

A React Element describes what you want to see on the screen. It isn't the ACUAL THING you see on the screen, but rather 
is an object representation of a DOM node. 

What is a DOM node? 

What is the DOM? 


### What Happens when you call setState? 

setState is used to update the local state of a component. When you call setState, react merges the object you passed it with the current state object of the component. This kicks off a process called reconciliation (updating the UI based on new state). React will construct
a new tree of React elements (which you can think of as an object representation of your UI). Once it has this tree in place, React will 
diff this new tree against the previous element tree. By doing this, React will then know the exact changes which occur and by knowing exactly what changes occured, will be able to update the UI only where necessary. 



### What is the difference between a controlled component and an uncontrolled
component?

A controlled component is one that takes its current value through props and notifies
changes through callbacks like “onChange”. Usually the parent component will have a
function called something akin to “handleChange”. The parent will pass handleChange to
the child. The child will then run something like this: onChange={props.handleChange}.
Then the handleChange in the parent will update state in the parent and pass the value
down to the child.

An uncontrolled component is one that stores its own state internally. You don’t have
access to its value and you will likely have to use ref to query the DOM if you want to get
it.

The best example that comes to mind where I have used controlled components is a
Material-UI Text-Field or any other input field.

### What is Redux?

Redux is a JavaScript library used to predictably manage an application’s state. It is primarily used with React to build User Interfaces. 