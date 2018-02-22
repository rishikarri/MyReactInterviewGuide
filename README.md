# Software Dev Interview Questions with a focus on React

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

An uncontrolled component is one that stores its own state internally. Data is handled by the DOM, not by React. You don’t have
access to its value and you will likely have to use ref to query the DOM if you want to get
it.

The best example that comes to mind where I have used controlled components is a
Material-UI Text-Field or any other input field.

Typically should use controlled components as they support instant field validation, allow you to disable / enable buttons and enforce input formats

### What is Redux?

Redux is a JavaScript library used to predictably manage an application’s state. 

### Talk to me about Error Boundaries

### What is Reselect?

### In which lifecycle event do you make AJAX requests and why?

componentDidMount - by doing this, you can guarantee that there is actually a component to update. Additionally, this will only run one time as opposed to other lifecycle hooks which could trigger an infinite re-render and break your app. 

### What does shouldComponentUpdate do and why is it important?

### When would you use a class component over a functional component? 

If your component has state or a lifecycle method, use a class component. Otherwise, use a functional component. 

### What are refs in react? 

Refs are an escape hatch which allow you to get direct access to a DOM element. In order to use them you attach a ref attribute to your 
component whose value is a callback function which recieves the underlying DOM element as its first argument. 

### What is a callback? 

A callback function, also known as a Higher Order Function, is a function passed to another function as a parameter. By doing this you can 
execute the function passed as the parameter (the callback function) at a later time.

### Other good information to know



React Fiber is the next implementation of React's reconciliation algorithm. 



