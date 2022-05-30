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
	- Provide life cycle hooks
