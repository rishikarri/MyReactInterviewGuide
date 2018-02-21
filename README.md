What Happens when you call setState? 

setState is used to update the local state of a component. When you call setState, react merges the object you passed it with the current state object of the component. This kicks off a process called reconciliation (updating hte UI based on new state). React will construct
a new tree of React elements (which you can think of as an object representation of your UI). Once it has this tree in place, React will 
diff this new tree against the previous element tree. By doing this, React will then know the exact changes which occur and by knowing exactly what changes occured, will be able to update the UI only where necessary