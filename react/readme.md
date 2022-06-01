## Introduction
- React is an opensource library used for building User Interfaces (UI).
- It is responsible only for building UI.
- Created and maintained by Facebook.
- Has huge community support with high demand for skillset.
- It has a component based architeture which allows breakdown down your application into small encapsulated parts which can then be composed to make complex apps
	- Components makes it possible to make reusable code
- React is declarative : tell react what you want and it will build the actual UI.
- Js Requirements: ' this ' keyword , filter , map and reduce 
- ES6 - let & const , arrow functions , template literals , default parameters , object literals , rest and spread operators and destructuring assignment.

## HelloWorld
- Install nodejs, vscode or use any editor of your choice.

- To create a project run
	  1. `npx create-react-app hello-world(npx approach)`
	  2. `cd hello-world`
	  3. `npm start`
- To get started edit app.js inside src folder of hello-world.
- what is npx : it is a npm package runner
- install react globally
	1. `npm install create-react-app -g`
	2. `create-react-app <project-name>`
  
  ## Folder Structure:
- package.json :- contains the script and dependancies required for the project
- node_modules :- contains all the dependencies required by react when you run npx create-react-app appname
- public/index.html :- is the file that get served up you don't need to edit this file.
- src/index.js :- is the file that renders the id = root DOM element of the index.html using app.js
- src/app.js :- is the app component which represent the view we see in the browser it is what we work on.
- src/serviceWorker.js :- is for progressive web app(not for a beginner).

## Component Types

- Stateless functional Components

```Javascript
function welcome(props){
    return <h1> Hello, {props.name}</h1>;
}
```

- Statefull Class Components

```Javascript
class Welcome extends React.Component{
    render(){
        return <h1>Hello, {this.props.name}</h1>;
    }
}
```

## Functional vs Class components

## Functional Components
This is a javascript funtions that accepts objects of properties known as props. It accepts an input of properties and return the UI.

- Funtional components should be used as much as possible over the class based component
	- Reasons
		- Absence of this
		- Solution without using state
		- Mainly responsible for the UI

## Class Components
- They are basically ES6 Classes, they can optionally recieve props as import and return html.
- They can also maintain a private internal state (maintain info and use it to decribe UI).


- Class Component are:
	- Feature rich
	- Maintain their own private data
	- Complex UI Logic

## Hooks
Hooks let you use state and other React features without writing a class.

## JSX
JavaScript XML (JSL) - is an extension of the JavaScript language syntax. It allows you write XML-like code for element and components.
	- it has a tag name, attribute and children
	- makes react code simpler and elegant
	- translates to pure JavaScript
	- Even you while using JSX you require to import react as it converts you jsx file to javascript file through React.createElement()
differences with regular html like - 
	- class : className
	- for : htmlFor
	- camelCase property naming convention • onclick - > onClick • tabindex - > tabindex

## Props
- Props is short for properties
- It is the optional input your component can accept which allows the component to be dynamic.
- We specify props as attributes
- props are immutable
- They get passed to the component
- A parent passes props down to the children

```Javascript
function welcome(props){
    return (
    <div>
    <h1> Hello, {props.name}</h1>;
    {props.children};// <welcome name = "Brue"><p>This is Children<p></welcome> // <p> will be rendered for this particular decalration of component
    <div>
    }
}
```
Output
> Hello, Brue 
> This is Children
- this.props is used to access props

## Props vs State

### Props

- props get passed to the component
- Function parameters
- props are immutable (readonly)
  - props - Functional Components
  - this.props - Class Components

### State

- state is managed within the component
- variables declared in the function body
- state can be changed
  - useState Hook - Functional Components
  - this.state - Class Components
## setState
Use setState to modify a component state.
- Always make use of setState and never modify the state directly.As it will update the state value but React will not know the update made so it will not reRender the component to make the change visible.
- Code has to executed after the state has been updated? Place that code in the the callback function which is the second argument to the setState method.
As if you write that code below that setState it will go in the manner of Synchronus behavior but you want to to execute it after words change have been made so better use it in the callBack function to see the desired results. 
- When you have to update state based on the previous state value, pass in a function as an argument instead of the regular object.
As whenever you call the setState object several time in a row react will sum of all the calls to a single call and hence key values remain uneffected as thought so better pass in a function.
```javascript
this.setState((prevState)=> {
	count: prevState.count + 1; 
})
```

## Binding Event Handlers

-There's no need to bind functions/callbacks in functional components since there's no this in functions. In classes, it was important to bind this because we want to ensure that the this in the callbacks referred to the component's instance itself. However, doing .bind in the constructor has another useful property of creating the functions once during the entire lifecycle of the component and a new callback wasn't created in every call of render(). To do only initialize the callback once using React hooks, you would use useCallback.

```javascript
class Foo extends Component {
  constructor(props) {
    super(props);
    this.handleClick = this.handleClick.bind(this);
  }
  }
```

## Methods As Props
```javascript
// child.js
function childComponent(props){
return(
	<div>
	<button onClick = {()=>props.greetHandler(<you can also use this technique to pass in the parameter>)}> Greet Parent</button>
	</div>
)}
// parent.js
constructor (props ){

super ( props )
this.state = { parentName : ' Parent ' } 
this.greetParent = this.greet Parent.bind ( this ) } 
greet Parent ( ) { alert ( Hello $ { this.state.parentName } ' ) }
render ( ) { 
return(
<div>
<childComponent greetHandler = {this.greetParent}/>
</div>
)  } }

```
## Conditional Rendering
- if/else : 
	- don't work inside the JSX
	- adding if/else statements within the JSX is not valid

- Element variables
	- This a better approach which uses Javascript variables to store elements.
	- Helps render the entire component or just a part of the component.
- Ternary conditional operator
	- Even more simpler, can be used inside the JSX
- Short circuit operator
	- Uses the && logical operator to evaluate both the right hand and left hand side if either the right or left hand side is false nothing with be returned.
[For detailed examples](https://reactjs.org/docs/conditional-rendering.html)
