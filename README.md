# My Software Developer Interview Guide

### What is React? 

It is a JavaScript library for building User Interfaces. It follows the component based approach which helps in building reusable UI components. It was built by Facebook. 

### What is a React Element? 

A React Element describes what you want to see on the screen. It isn't the ACUAL THING you see on the screen, but rather 
is an object representation of a DOM node. 


### What Happens when you call setState? 

setState is used to update the local state of a component. When you call setState, react merges the object you passed it with the current state object of the component. This kicks off a process called reconciliation (updating the UI based on new state). React will construct
a new tree of React elements (which you can think of as an object representation of your UI). Once it has this tree in place, React will 
diff this new tree against the previous element tree. By doing this, React will then know the exact changes which occur and by knowing exactly what changes occured, will be able to update the UI only where necessary. 

### What are synthetic events in React?

Instances of SyntheticEvent are a cross-browser wrapper around the browser's native event. They combine the behavior of different 
browsers into one API. This is done to make sure that the events show consistent properties across different browsers. 

### What is the difference between a controlled component and an uncontrolled component?

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

Error boundaries are a feature of React 16. They are React components that catch JavaScript errors anywhere in their child component tree, log those errors and display a fallback UI instead of the crashed component tree. Think of them as try-catch statements, but for React. 

### What is Reselect?

### What is a Closure in JavaScript?

An function with preserved data. An inner function with access to a variable or parameter outside of its scope.

Example from StackOverflow: 

function sayAlice() {
    var say = function() { console.log(alice); }
    // Local variable that ends up within closure
    var alice = 'Hello Alice';
    return say;
}
sayAlice()();// logs "Hello Alice"

### What React.cloneElement?

You can use this to clone and return a new React Element with all of the original props plus any additional props you would like to add. 

### What React.createElement?

You typically won't be using this function if you are writing React with JSX. React.createElement creates and returns a new React Element of a given type (tag name string such as 'div' or 'span'). 

### What is the difference between deep and shallow merge of JavaScript objects?

In a shallow merge of objects, if the original object and the merged object have the same key, the value will get overwritten by the "merged object", 

in a deep merge, the key will now have both its orginal value and any additional value provided by the merged object. 

As an example: 

let obj1 = {
	tennis: {
		tennisCourt: 'frankie allen park', 
	}
	basketball: {
		basketballCourt: 'LA Fitness', 
	}
}

let obj 2 = {
	tennis: {
		tennisCourt: 'piedmont park'
	}
}

const shallowMergedObject = {
	tennis: {
		tennisCourt: 'piedmont park'
	}
	basketball: {
		basketballCourt: 'LA Fitness', 
	}
}

const deepMergedObject = {
	tennis: {
		tennisCourt: 'frankie allen park', 
		tennisCourt: 'piedmont park'
	}
	basketball: {
		basketballCourt: 'LA Fitness', 
	}
}

### What is Recursion?

A recursive function is one that calls itself. It is an alternative way to solving a problem which requires iterating. 

A recursive function has two cases: A base case and a recursive case. The base case is when the function stops calling itself and the recursive case is when the function calls itself again. 

The best example is a solution I wrote to generating x! when given x: 

const factorial = (x) => {
    if (x === 1) {
        return 1; 
    } else {
        return x * factorial(x-1)
    }
}

### What is a Higher-Order-Component?

A higher order component is a function that takes a component as an input and returns an enhanced component as an output. 

const EnhancedComponent = higherOrderComponent(WrappedComponent);

The most common example I can think of is the connect example in the Redux library that "connects" a React Component to the Redux store


### In which lifecycle event do you make AJAX requests and why?

componentDidMount - by doing this, you can guarantee that there is actually a component to update. Additionally, this will only run one time as opposed to other lifecycle hooks which could trigger an infinite re-render and break your app. 


### What does shouldComponentUpdate do and why is it important?

shouldComponentUpdate is a lifecycle method that allows us to opt out of the reconciliation process for the component we use it in. It allows the developer to have fine motor control over which situations the UI should or shouldn't update. 

### Why would you use React.Children.map(props.children, () => ) instead of props.children.map(() => )

React.Children.map takes into account that props.children may be an array or an object where as props.children.map assumes that there are multiple children (an array of objects). 

### When would you use a class component over a functional component? 

If your component has state or a lifecycle method, use a class component. Otherwise, use a functional component. 

### What are refs in react? 

Refs are an escape hatch which allow you to get direct access to a DOM element. In order to use them you attach a ref attribute to your 
component whose value is a callback function which recieves the underlying DOM element as its first argument. 

### What is two way data binding in an MVC cdoebase? 

Two way data binding means that when properties in the model get updated, so does the UI. 

Similarly, when properties in the UI get updated, so does the model. 

You cannot update one piece of data without the other. The data sets are "bound"

### Explain MVC. 

MVC, or Model View Controller is an architectual pattern commonly used for creating User Interfaces. The pattern divides an application into three interconnected parts. Doing so allows a separation between how information is presented to the user and how information is internally represented. 

The model directly manages data, logic and rules of the application. 

The view is what the user sees. 

The controller is what accepts input and provides instructions to the model to update itself which will then trigger the view to update accordingly. 

### Explain Big O Notation? 

Big O notation is used in computer science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario and can be used to describe the execution time requred or the spaced used by an algorithm. 

O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data size. 

O(N) describes an algorithm where performance will grow linearly and in direct proportion to the size of the input data set. 

O(N^2) performance is directly proprotional ot the square size of the input data set. This is common with algorithms that involve nested iterations over the data set. Think: nested for loop. 

O(2^N) describes an algorithm whose worst case runtime doubles with each addition to the input data set. THe growth cure of an O^2N function is exponential. Think recursive calculation of the Fibonnaci sequence. 

O (logN) - doubling the size of the input data set has little effect on the algorithm's growth as the data set will be halved by each iteration. Think: searching through a phone book. 

### What is a callback? 

A callback function, also known as a Higher Order Function, is a function passed to another function as a parameter. By doing this you can 
execute the function passed as the parameter (the callback function) at a later time.

## SQL 

What is SQL? 

SQL stands for Structured Query Language. It is the standard language for storing, manipulating and retrieving data from databases. 

## What are RDBMS? 

Relational Database Management Systems are programs that let you create and update a relational database. Examples are as follows: 

- Oracle
- MySQL
- SQLite
- Microsoft Acces
- FoxPro

The data in RDMBS is stored in database tables. 

A table is a collection of related data entries and consists of columns and rows. 

A field is a column in a table that is designed to maintain specific information about every record (row) in the table. 

A record or row, is each individual entry that exists in the table. 


## What is a SQL Join? 

A join clause is used to combine rows from two or more tables based on a related column between them. 

Inner Join - Returns records that have matching values in bot h tables. 

Left Join - Returns all records from the left table and matched records from the right table

Right Join - Returns all records from teh right table and matched records from the left table. 

Full Join - returns all records when there is a match in either the right or left table. 

### Other good information to know

React Fiber is the next implementation of React's reconciliation algorithm. 



