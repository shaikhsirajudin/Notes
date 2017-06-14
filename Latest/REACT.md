
# In React we have two types of components
1) Presentational Components.

•	. How things look (markup, styles)
•	. It don’t know about Redux, its dumb components
•	. In terms of functionality it read data from props
•	. On data changes invoke callbacks from props to smart components



2) Container components.
•	It’s know about Redux, It’s the one that is actively listening to the changes of state and 
its going to react.
•	How things work (data fetching, state updates)
•	Its smart components it dispatches action. So for every presentational components 
there is container components

# What happens when you call setState?
The first thing React will do when setState is called is merge the object you passed 
into setState into the current state of the component. This will kick off a process called reconciliation. 
The end goal of reconciliation is to, in the most efficient way possible, update 
the UI based on this new state. To do this, React will construct a new tree of React elements 
(which you can think of as an object representation of your UI). Once it has this tree, 
in order to figure out how the UI should change in response to the new state, 
React will diff this new tree against the previous element tree. By doing this, 
React will then know the exact changes which occurred, and by knowing exactly what changes occurred, 
will able to minimize its footprint on the UI by only making updates where absolutely necessary.

# What’s the difference between an Element and a Component in React?
A React element describes what you want to see on the screen. 
Not so simply put, a React element is an object representation of some UI.

A React component is a function or a class which optionally accepts input and returns a React element 
(typically via JSX which gets transpiled to a createElement invocation).

# When would you use a Class Component over a Functional Component?
If your component has state or a lifecycle method(s), use a Class component. Otherwise, 
use a Functional component.

# What are refs in React and why are they important?
Refs are an escape hatch which allow you to get direct access to a DOM element or an instance of a component. 
In order to use them you add a ref attribute to your component whose value is a callback function 
which will receive the underlying DOM element or the mounted instance of the component as its first argument.
```
class UnControlledForm extends Component {
  handleSubmit = () => {
    console.log("Input Value: ", this.input.value)
  }
  render () {
    return (
      <form onSubmit={this.handleSubmit}>
        <input
          type='text'
          ref={(input) => this.input = input} />
        <button type='submit'>Submit</button>
      </form>
    )
  }
}

```
Above notice that our input field has a ref attribute whose value is a function. 
That function receives the actual DOM element of input which we then put on the instance 
in order to have access to it inside of the handleSubmit function.

It’s often misconstrued that you need to use a class component in order to use refs, 
but refs can also be used with functional components by leveraging closures in JavaScript.

```
function CustomForm ({handleSubmit}) {
  let inputElement
  return (
    <form onSubmit={() => handleSubmit(inputElement.value)}>
      <input
        type='text'
        ref={(input) => inputElement = input} />
      <button type='submit'>Submit</button>
    </form>
  )
}

```
# What are keys in React and why are they important?
Keys are what help React keep track of what items have changed, been added, or been removed from a list.
```
render () {
  return (
    <ul>
      {this.state.todoItems.map(({task, uid}) => {
        return <li key={uid}>{task}</li>
      })}
    </ul>
  )
}
```

It’s important that each key be unique among siblings. We’ve talked a few times already about reconciliation 
and part of this reconciliation process is performing a diff of a new element tree with the most previous one. 
Keys make this process more efficient when dealing with lists because React can use the key on a child element 
to quickly know if an element is new or if it was just moved when comparing trees. 
And not only do keys make this process more efficient, but without keys, 
React can’t know which local state corresponds to which item on move. 
So never neglect keys when mapping.



# If you created a React element like Twitter below, what would the component definition of Twitter look like?

```
<Twitter username='tylermcginnis33'>
  {(user) => user === null
    ? <Loading />
    : <Badge info={user} />}
</Twitter>

import React, { Component, PropTypes } from 'react'
import fetchUser from 'twitter'
// fetchUser take in a username returns a promise
// which will resolve with that username's data.

class Twitter extends Component {
  // finish this
}
```

If you’re not familiar with the render callback pattern, this will look a little strange. 
In this pattern, a component receives a function as its child. Take notice of what’s inside 
the opening and closing <Twitter> tags above. Instead of another component as 
you’ve probably seen before, the Twitter component’s child is a function. 
What this means is that in the implementation of the Twitter component, 
we’ll need to treat props.children as a function.
```
Here’s how I went about solving it.
import React, { Component, PropTypes } from 'react'
import fetchUser from 'twitter'

class Twitter extends Component {
  state = {
    user: null,
  }
  static propTypes = {
    username: PropTypes.string.isRequired,
  }
  componentDidMount () {
    fetchUser(this.props.username)
      .then((user) => this.setState({user}))
  }
  render () {
    return this.props.children(this.state.user)
  }
}
```

Notice that, just as I mentioned above, I treat props.children as a function by invoking it 
and passing it the user.

What’s great about this pattern is that we’ve decoupled our parent component from our child component. 
The parent component manages the state and the consumer of the parent component can decide in which way 
they’d like to apply the arguments they receive from the parent to their UI.

To demonstrate this, let’s say in another file we want to render a Profile instead of a Badge, 
because we’re using the render callback pattern, we can easily swap around the UI without 
changing our implementation of the parent (Twitter) component.
```
<Twitter username='tylermcginnis33'>
  {(user) => user === null
    ? <Loading />
    : <Profile info={user} />}
</Twitter>
```
# What is the difference between a controlled component and an uncontrolled component?
A large part of React is this idea of having components control and manage their own state. 
What happens when we throw native HTML form elements (input, select, textarea, etc) into the mix? 
Should we have React be the “single source of truth” like we’re used to doing with React or 
should we allow that form data to live in the DOM like we’re used to typically doing with HTML form elements? 
These two questions are at the heart of controlled vs uncontrolled components.

A controlled component is a component where React is in control and is the single source of truth for the form data. 
As you can see below, username doesn’t live in the DOM but instead lives in our component state. 
Whenever we want to update username, we call setState as we’re used to.
```
class ControlledForm extends Component {
  state = {
    username: ''
  }
  updateUsername = (e) => {
    this.setState({
      username: e.target.value,
    })
  }
  handleSubmit = () => {}
  render () {
    return (
      <form onSubmit={this.handleSubmit}>
        <input
          type='text'
          value={this.state.username}
          onChange={this.updateUsername} />
        <button type='submit'>Submit</button>
      </form>
    )
  }
}
```

An uncontrolled component is where your form data is handled by the DOM, 
instead of inside your React component.

You use refs to accomplish this.
```
class UnControlledForm extends Component {
  handleSubmit = () => {
    console.log("Input Value: ", this.input.value)
  }
  render () {
    return (
      <form onSubmit={this.handleSubmit}>
        <input
          type='text'
          ref={(input) => this.input = input} />
        <button type='submit'>Submit</button>
      </form>
    )
  }
}
```

Though uncontrolled components are typically easier to implement since you just grab 
the value from the DOM using refs, it’s typically recommended that you favor 
controlled components over uncontrolled components. 
The main reasons for this are that controlled components support instant field validation, 
allow you to conditionally disable/enable buttons, enforce input formats, and are more “the React way”.

# In which lifecycle event do you make AJAX requests and why?

AJAX requests should go in the componentDidMount lifecycle event.

There are a few reasons for this,

•Fiber, the next implementation of React’s reconciliation algorithm, will have the ability to start and 
stop rendering as needed for performance benefits. One of the trade-offs of this is that componentWillMount, 
the other lifecycle event where it might make sense to make an AJAX request, will be “non-deterministic”. 
What this means is that React may start calling componentWillMount at various times whenever 
it feels like it needs to. This would obviously be a bad formula for AJAX requests.


•You can’t guarantee the AJAX request won’t resolve before the component mounts. 
If it did, that would mean that you’d be trying to setState on an unmounted component, 
which not only won’t work, but React will yell at you for. Doing AJAX in componentDidMount 
will guarantee that there’s a component to update.


# What does shouldComponentUpdate do and why is it important?

Above we talked about reconciliation and what React does when setState is called. 
What shouldComponentUpdate does is it’s a lifecycle method that allows us to opt out of this reconciliation process 
for certain components (and their child components). Why would we ever want to do this? As mentioned above, 
“The end goal of reconciliation is to, in the most efficient way possible, update the UI based on new state”. 
If we know that a certain section of our UI isn’t going to change, there’s no reason to have React go through 
the trouble of trying to figure out if it should. By returning false from shouldComponentUpdate, 
React will assume that the current component, and all its child components, will stay the same as they currently are.



# How do you tell React to build in Production mode and what will that do?

Typically you’d use Webpack’s DefinePlugin method to set NODE_ENV to production. 
This will strip out things like propType validation and extra warnings. On top of that, 
it’s also a good idea to minify your code because React uses Uglify’s dead-code elimination to strip out 
development only code and comments, which will drastically reduce the size of your bundle.



# Why would you use React.Children.map(props.children, () => ) instead of props.children.map(() => )

It’s not guaranteed that props.children will be an array.

Take this code for example,
```
<Parent>
  <h1>Welcome.</h1>
</Parent>
```

Inside of Parent if we were to try to map over children using props.children.map 
it would throw an error because props.children is an object, not an array.

React only makes props.children an array if there are more than one child elements, like this
```
<Parent>
  <h1>Welcome.</h1>
  <h2>props.children will now be an array</h2>
</Parent>
```

This is why you want to favor React.Children.map because its implemention takes into account 
that props.children may be an array or an object.



# Describe how events are handled in React.

In order to solve cross browser compatibility issues, your event handlers in React will be passed instances 
of SyntheticEvent, which is React’s cross-browser wrapper around the browser’s native event. 
These synthetic events have the same interface as native events you’re used to, 
except they work identically across all browsers.

What’s mildly interesting is that React doesn’t actually attach events to the child nodes themselves. 
React will listen to all events at the top level using a single event listener. 
This is good for performance and it also means that React doesn’t need to worry about keeping 
track of event listeners when updating the DOM.



# What is the difference between createElement and cloneElement?

createElement is what JSX gets transpiled to and is what React uses to create React Elements 
(object representations of some UI). 
cloneElement is used in order to clone an element and pass it new props. They nailed the naming on these two.



# What is the second argument that can optionally be passed to setState and what is its purpose?

A callback function which will be invoked when setState has finished and the component is re-rendered.

Something that’s not spoken of a lot is that setState is asynchronous, 
which is why it takes in a second callback function. 
Typically it’s best to use another lifecycle method rather than relying on this callback function, 
but it’s good to know it exists.
```
this.setState(
  { username: 'tylermcginnis33' },
  () => console.log('setState has finished and the component has re-rendered.')
)

```


# What is wrong with this code?
```
this.setState((prevState, props) => {
  return {
    streak: prevState.streak + props.count
  }
})
```

Nothing is wrong with it 🙂. It’s rarely used and not well known, 
but you can also pass a function to setState that receives the previous state and props and returns a new state, 
just as we’re doing above. And not only is nothing wrong with it, 
but it’s also actively recommended if you’re setting state based on previous state.

# What is React? How is it different from other JS frameworks?
. What is React?

React is an open-source JavaScript library created by Facebook for building complex, 
interactive UIs in web and mobile applications.

The key purpose is to build UI components; it is often referred to as just the “V” (View) in an “MVC” architecture. 
Therefore it has no opinions on the other pieces of your technology stack and 
can be seamlessly integrated into any application.
. How is React different?
Because React is a small library focused on building UI components, 
it is necessarily different than a lot of other JavaScript frameworks. 

For example, AngularJS (1.x) approaches building an application by extending HTML markup and injecting various constructs 
(e.g. Directives, Controllers, Services) at runtime. As a result, AngularJS is very opinionated about 
the greater architecture of your application — these abstractions are certainly useful in some cases, 
but in many situations, they come at the cost of flexibility.

By contrast, React focuses exclusively on the creation of components, and has few (if any) opinions 
about an application’s architecture. 
This allows a developer an incredible amount of flexibility in choosing the architecture they deem “best” — 
though it also places the responsibility of choosing (or building) those parts on the developer.

# What happens during the lifecycle of a React component?
High-Level Component Lifecycle

At the highest level, React components have lifecycle events that fall into three general categories:
1.Initialization
2.State/Property Updates
3.Destruction

For example, a component may need to add event listeners to the DOM when it first mounts. However, 
it should probably remove those event listeners when the component unmounts from the DOM so 
that irrelevant processing does not occur.

```
class MyComponent extends React.Component {
    // when the component is added to the DOM...
    componentDidMount() {
        window.addEventListener(‘resize’, this.onResizeHandler);
    }

    // when the component is removed from the DOM...
    componentWillUnmount() {
        window.removeEventListener(‘resize’, this.onResizeHandler);
    }

    onResizeHandler() {
        console.log(‘The window has been resized!’);
    }
}
```

![Low-Level Component Lifecycle](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/ComponentLifecycle.PNG)

Within these three general buckets exist a number of specific lifecycle hooks — essentially abstract methods — 
that can be utilized by any React component to more accurately manage updates. 
Understanding how and when these hooks fire is key to building stable components and will enable you 
to control the rendering process (improving performance).

Take a look at the diagram above. The events under “Initialization” only happen when a component is 
first initialized or 
added to the DOM. Similarly, the events under “Destruction” only happen once 
(when the component is removed from the DOM). 
However, the events under “Update” happen every time the properties or state of the component change.

For example, components will automatically re-render themselves any time their properties or 
state change. 
However, in some cases a component might not need to update — so preventing the component 
from re-rendering might improve 
the performance of our application.
```
class MyComponent extends React.Component {

    // only re-render if the ID has changed!
    shouldComponentUpdate(nextProps, nextState) {
        return nextProps.id === this.props.id;
    }
}
```

# What can you tell me about JSX?
When Facebook first released React to the world, they also introduced a new dialect of JavaScript called 
JSX that embeds raw HTML templates inside JavaScript code. 
JSX code by itself cannot be read by the browser; it must be transpiled into traditional 
JavaScript using tools like Babel and webpack. 
While many developers understandably have initial knee-jerk reactions against it, 
JSX (in tandem with ES2015) has become the defacto method of defining React components.
```
class MyComponent extends React.Component {
    render() {
        let props = this.props;

        return (
            <div className=”my-component”>
                <a href={props.url}>{props.name}>/a>
            </div>
        );
    }
}
```

Developers do not have to use JSX (and ES2015) to write an application in React?

This is certainly true. Having said that, many React developers prefer to use JSX as its syntax 
is far more declarative and reduces overall code complexity. 
Facebook certainly encourages it in all of their documentation!

Adopting JSX allows the developer to simultaneously adopt ES2015 — 
giving immediate access to some wonderful syntactic sugar.

ES2015 introduced a variety of new features to JavaScript that makes writing large applications 
far easier than ever before: 
classes, block scoping via let, and the new spread operator are just a small portion of the additions.
```
import AnotherClass from ‘./AnotherClass’;

class MyComponent extends React.Component {
    render() {
        let props = this.props;

        return (
            <div className=”my-component”>
                <AnotherClass {...props} />
            </div>
        );
    }
}

}
```
But while ES2015 is becoming more and more widespread, it still is far from widely supported by 
the major browsers — so you’ll need to use a tool like Babel or webpack to convert everything into legacy ES5 code.

If you have built a React application using JSX and ES2015, 
be sure to speak about some specific pros or cons you encountered:

# Why ReactJS is used?
 React is used to handle the view part of Mobile application and Web application.

# Does ReactJS use HTML?
 No, It uses JSX which is simiar to HTM.

# What are the feature of ReactJS?
1) JSX: JSX is JavaScript syntax extension.
2) Components : React is all about components.
3) One direction flow: React implements one way data flow which makes it easy to reason about your app

# What are the Advantages of ReactJS?
1) React uses virtual DOM which is JavaScript object. This will improve apps performance
2) It can be used on client and server side
3) Component and Data patterns improve readability.
4) Can be used with other framework also.

# How to embed two components in One component?

```
import React from 'react';
class App extends React.Component {
   render() {
      return (
         <div>
            <Header/>
            <Content/>
         </div>
      );
   }
}

class Header extends React.Component {
   render() {
      return (
         <div>
            <h1>Header</h1>
         </div>
      );
   }
}

class Content extends React.Component {
   render() {
      return (
         <div>
            <h2>Content</h2>
            <p>The content text!!!</p>
         </div>
      );
   }
}

export default App;
```
# How to use Events in ReactJS? Give an example of using events?

React identifies every events so that it must  have common and consistent behavior  
across all the browsers. Normally, in normal JavaScript or other frameworks, 
the onchange event is triggered after we have typed something into a Textfield and then “exited out of it”. 
In  ReactJS we cannot do it in this way.

The explanation is typical and  non-trivial:

*”<input type=”text” value=”dataValue”> renders an input textbox initialized with the value, “dataValue”.

When the user changes the input in text field, the node’s value property will update and change. 
However, node.getAttribute(‘value’) will still return the value used at initialization time that is dataValue.

Form Events:
◾onChange: onChange event  watches input changes and update state accordingly.
◾onInput: It is triggered on input data
◾onSubmit: It is triggered on submit button.

Mouse Events:
◾onClick: OnClick of any components event is triggered on.
◾onDoubleClick: onDoubleClick of any components event is triggered on.
◾onMouseMove: onMouseMove of any components, panel event is triggered on.
◾onMouseOver: onMouseOver of any components, panel, divs event is triggered on.

Touch Events:
◾onTouchCancel: This event is for canceling an events.
◾onTouchEnd: Time Duration attached to touch of a screen.
◾onTouchMove: Move during touch device .
◾onTouchStart: On touching a device event is generated.
```
import React from 'react';
import ReactDOM from 'react-dom';

var StepCounter = React.createClass({
                    getInitialState: function() { return {counter: this.props.initialCounter }; },
                    handleClick: function() {             
                        this.setState({counter: this.state.counter + 1});  },
               render: function() {
               return <div onClick={this.handleClick}> OnClick Event, Click Here: {this.state.counter }</div>;
            }
});

ReactDOM.render(< StepCounter initialCounter={7}/>, document.getElementById('content'));

```

# How to set up routing in ReactJS. Explain with the help of step by step approach?

Routing is the  key features of web applications (and even other platforms) 
could not be left out in React. We can develop full featured single page applications (SPA) with React, 
one of the key feature is routing.

We use library called React-Router for routing in reactJS.
React goodness is  to keep things as simple as possible and that is why the core library exactly 
does what React is about, components. Routing, DOM rendering and other logics are abstracted to a different library.

We need to install library by command to initialization router
```
$ user@administrator:/var/www/html/reactjs$  npm install react react-dom react-router –save
```

# Can Browsers read JSX? If not, Why?
JSX is not valid Javascript. Web broswers can't read it! If a JavaScript file contains JSX code, 
then that file will have to be compiled. That means that before the file reaches a web browser, 
a JSX compiler will translate any JSX into regular JavaScript.

# Write small code that will render a JSX expression?

ReactDom.render(<h1>Hello world</h1>,document.getElementById('app');
)

# Can you nest JSX elements inside of other JSX elements?
Yes! you can nest JSX elements just like you can od with HTML elements.

# If a JSX expression takes up more than one line, what should you do?

You should wrap the multi-line JSX expression in parentheses.

# A JSX expression must have exactly how many outermost elements?
It must have exactly one outermost element.

# In JSX why you can't use "class" word?
In JSX, you can't use the word class. You have to use className instead because JSX gets translated 
into Javascript, and class is a reserved word in Javascript.

# Why would I use React over AngularJS?

AngularJS and ReactJS have several different aspects:
•Componentization. AngularJS is based on the three layers — Model, View, Controller, 
and provides many standard services, factories, controllers, and directives. 
We divide app code into several files and can reuse template or component in a different part of the website. 
ReactJS helps us update the View for the user and, with Flux, can control the application workflow. 
React offers freedom, but it comes at the cost of additional time spent designing the structure of an application.

•Data Binding. Angular uses two-way data binding, it helps us write less boilerplate code to 
create interactions between components (the View and the Model). 
But Angular automatically creates a watcher for each binding and we may come to a point 
when an app is packed with too many watchers for bound elements. 
React uses one-way data binding and an application architecture called Flux controls 
the flow of data to components through one control point – the dispatcher. 
It's easier to debug self-contained components of large ReactJS apps than 
it is with similarly large AngularJS applications.

•Performance. Angular creates a watcher for each binding to track changes in the DOM. 
Once the View updates (becomes “dirty"), Angular compares the new value with the initial (bound) 
value and runs the $digest loop. The $digest loop then checks not only values that have actually changed, 
but also all others values that are tracked through watchers. 
This is why performance will decrease a lot if your application has too many watchers. 
Also AngularJS applies changes in the real DOM in the browser. When it gets updated, the browser 
has to change many internal values to represent a new DOM. This also has a negative impact on 
application performance. But it doesn't mean we cannot create a fast application in AngularJS. 
React’s virtual DOM is one of the greatest advantages: ReactJS creates a lightweight DOM; 
with new data new virtual DOM is created and compared with previous one; rebuilds the virtual DOM once again, 
but with new changed HTML.

•Resolving Dependencies. AngularJS uses a basic OOP pattern called dependency injection, 
when we write dependencies in a separate file. Dependency injection inherits any standard functions 
that we declare for an Angular factory or service. We only pass dependencies as parameters 
in any order in our functions. React doesn’t offer any concept of a built-in container for dependency injection. 
You can use Browserify, RequireJS, EcmaScript 6 modules which we can use via Babel, 
ReactJS-di to inject dependencies automatically.

•Directives and Templates. With AngularJS we access the DOM only through directives - standard and self-created ones. 
Own directives are a powerful way to work with the DOM and to insert data into templates. 
ReactJS doesn’t offer division into templates and directives or template logic. 
The template logic should be written in the template itself. To see what this looks like, open an example from GitHub

# What is virtual DOM diffing?

When component rendering for the second time Virtual DOM checks what element get changed and print the changed element to the page, other elements remain untouched.
The Virtual DOM diffing allows React to minimize changes to the DOM as a result of user actions, therefore increasing browser performance. This is why it's fast!

# What's a difference between a DOM object and a virtual DOM object?

A virtual DOM object can update much faster than a regular DOM object.
A virtual DOM object can't directly affect HTML.
A virtual DOM object will be updated if ANY JSX elements renders.

# What is th module loader of choice for React developers?

Webpack

# Why do we capitalize components?

Because they are a constructor. It is not a renderred DOM element Yet, 
it just has the capacity to render out a DOM element whenever we print it (with something like <Header />)

# What is a state? How to use state?
State handles data changes. State is a Javascript object that lives inside each component. We can access it via this.state. In React we modify the DOM indirectly, by updating each components state and letting React handle updates to the DOM.
The state is a vital part of REact apps, making user interfaces interactive.
Represents data that changes over time.
We declare an initial state in the component's constructor. 
As first line call the super function.(to communicate with other components). In order to create the initial state for a component, we must declare the property this.state as an object in the class consturctor function.
We update state by calling this.setState(), this causes our component to re-render.

#  How you will update a component's state?
We update stat by calling this.setState(),this causes our component to re-render.
this,setState({showComments:true})
Will only update the properties an argument, not replace the entire state object.

# How can you access something inside state?

this.state.--- inside JSX{} inside render if 
this.state = {name:"test"}; then ... {this.state.name}

# What are Synthetic events?

In order to ensure events have consistent properties across different browsers, 
React wraps the browser's native events into "synthetic events", consolidating browser behaviors into one API. Synthetic events are a cross browser wrapper around the broswer's native events system.

# Explain what happens with React's "virtual DOM" whenever render fires, and why it's so great.

Whenever React renders the component tree, it looks for changes from the virtual DOM to the actual DOM. 
If there are changes, it will update only the affected nodes in the most efficent way. 
If there are no changes, it doesn't even touch the webpage.
This is great because Javascript is so fast, but the DOM is so slow. 
Whenever we have to actually go to the DOM and update elements, that's the slow part of any webpage. 
By having a virtual DOM where everything is updated behind 
the scenes and only changed in the actual DOM if there's differences, 
it allows our applications to become super fast.

# How can you set state initially(within the consturctor() mehtod)?

constructor(){
  super();
  this.state={name:"some"};
}

# What is the primary type in React? It's a light, stateless, immutable, virtual rep of a DOM elements?

ReactElement

# What is one of the core types in React?

ReactNode

# How to assign form values to properties on the component object?

We can use refs to assign form values to properties on the component object. 
input: dom element passed in the function
```
<input ref={(input)=> this._name=input} />

```

# Explain the concept of ownership in ReactJS?
Understand the concepts of ownership and children in ReactJS
When we do:
```
var MyContainer = React.createClass({
  render: function() {
    return <MyChild value={this.props.value} />
  }
});
// Or in ES6
const MyContainer = (props) => <MyChild value={props.value} />


 ➔ <MyContainer>  is the owner of  <MyChild> 
➔ <MyChild>  is the ownee of  <MyContainer> 

We don’t talk about parent/child, which refers to the DOM relationships.

If we wrap a  <div>  around  <MyChild> :

var MyContainer = React.createClass({
  render: function() {
    return <div><MyChild value={this.props.value} /></div>
  }
});
// Or in ES6
const MyContainer = (props) => <div><MyChild value={props.value} /></div>


 <MyContainer>  is not the parent of  <MyChild>  (the  <div>  is in between), 
 but it’s more generally its owner.

In the DOM hierarchy, the  <div>  is the representation of  <MyContainer>  
which is the parent of whatever  <MyChild>  can represent.
```
# Explain Virtual DOM?

In React, for every DOM object, there is a corresponding "virtual DOM object." A virtual DOM object is 
a representation of a DOM object, like a lightweight copy. Think of manipulating the 
virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.

# Explain what is Prop?

When we use our defined components, we can add attributes called props. These attributes are 
available in our component as this.props and can be used in our render method to render dynamic data.
```
var MyComponent = React.createClass({

render:function(){
  return(<h1>Hello, {this.props.name}!</h1>);
}
})
```
# What is the different between Reactjs and Angularjs
# ![What is the different between Reactjs and Angularjs](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/ReactAngular.PNG)

# What are the feature of ReactJS?

JSX: JSX is JavaScript syntax extension.

2) Components : React is all about components.

3) One direction flow: React implements one way data flow which makes it easy to reason about your app

# How could you use state and props together when passing data between components?
set a default value with state(in the consturctor)
```
constructor(){
  super();
  this.state={title:"welcome"}
}

-- inject that into a child with this.state

render(){
  return(<div> <Header title={this.state.title} /> </div>);
}


-- access it in any child component with this.props
-- in Header.js

render(){
  return(<div><Title title={this.props.title} </div>);
}

```

# What if you want an 
```
<input> that allows us to change a <Title /> component (within a <Header /> component) 
as we type through "two way binding"?

 What is the general thought process?

As the user enters text in the <input> (within the <Header /> component), 
we want to take that "change" and trigger some type of "event" on the overall <Layout /> parent component.
```
That "event" will say to update the "state", which will then cause the whole React-style rendering process to begin because a state changed.

# When dealing with events in Javascript, how do you grab the value? 
Pass in the javascript event(e) and call e.target.value

```
handleChange(e){
  var title=e.target.value;
  this.props.changeTitle(title);
}

```
# How event handling works in React?
We use React's event system to capture user input including from submissions and button clicks.
"Refs" allow us to reference DOM elements in our code after the component has been rendered.
Parent components can pass callback functions as props to child components to allow two-way communication.
In order to ensure events have consistent properties across different broswers, React wraps the browser's native envents 
into "synthetic events", consolidating broswer behaviors into one API. Synthetic events are a cross-broswer wrapperr around 
the broswer's native event system.

# What is a Flux action?
It's a javascript object that describes what we want to do, and the data we need to do it.

# What does "handling state" mean? What exactly are we trying to handle?
The data that comes from the server.

# What are the main problems with traditional MVC frameworks(Backbone,Angular...)
Manipulating the DOM (slow and inefficient)
Creating a very complicated metal model around our data and vies because of circular dependencies.

# Describe what happens whenever state changes(in user, posts, UI state, etc)
React goes through the component tree and re-renders everything" the state has changed, so let's pass 
it down and see what needs to be updated"

# Within a component, how can you access props that have been injected from parent component?
this.props

# What are Lifecycle methods?
Functions that called while the component is rendered for the first time (mount), or about to be removed from the DOM (unmount).
constructor()

1. componentWillMount()// called before component rendered
2. render()// comment box is mounted
3. Component waits for API response and when it's received, setState() is called, causing render() to be called again.
4. componentDidMount()// called when component done rendering. this._fetchComments() triggered evey 5 seconds
5. componentWillUnmount()// caleed when the component is about to be removed from the DOM, and clears the fetchComment timeout.

Whenever a component instance updates, it automatically calls all five of there methods, inorder.

# Describe the difference between imperative code(Backbone?Angular) and declarative code (React)

Imperative: is "how" to do something. When a model updates, you tell the view to listen to that model, and then in 
the view you tell the HTML what to do.

Declarative: is "What" to do. It takes away the "how" allowing you to focus on what's most important.

# How does a prop relate to state?
A prop is a portion of state passed down from a parent component to a child component.

# What is redux?
A method of handling the state(or the data) of an app.

# How does the React Router work?
It will render out the <Router /> to the page, and then it dictates which components should (or should not) render.

# How can you access the currently selected React component in the console?
$r

# What is polling?

In order to check whether new comments are added, we can periodically check the server for updates. Use setInterval on 
componentDisMount every 5 secon call the _FetchComment function.
This might sound expensive, but it's not. React optimizes the rendering process by only updating the DOM when changes 
are dtelected on the resulting markup.

# Whaht is refs isn Reactjs? When might you use refs?
The ref is used to return a reference to your element. Refs should be avoided in most cases but they can be useful 
when you need DOM measurements or to add methods to your components

# Rewrite this without using JSX:
```
<div className="ui items" >
Hello, friend! I am a basic REact Component.
<\div>

React.createElement('div',{className:'ui items'},
React.createElement('p',null,'Hello, friend! I am a basic React component.') )

```
# How to pass props from a parent component to a child component?

Use syntax [prop_name]={prop_value} in the JSX for the child component within the parent component's render method.

# How child components communicate with parent components? 
Inverse data flow- children communicate with parents by calling functions that are handed to them via props. 
In the ProductHunt app, when an up-vote was clicked Product didnt do any data management. It was not the owner of its state. 
Instead, it called a function given to it by ProductList, passing in its id.
ProductList was then able to manage state accordingly

# [react-survey](https://github.com/aisensiy/react-survey)
# [project examples](https://mobx.js.org/faq/examples.html)