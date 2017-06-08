# Are you familiar with Flux?
Flux is an architectural pattern that enforces unidirectional data flow — 
its core purpose is to control derived data so that multiple components can interact with 
that data without risking pollution.

The Flux pattern is generic; it’s not specific to React applications, 
nor is it required to build a React app. However, Flux is commonly used by React developers because 
React components are declarative — the rendered UI (View) is simply a function of state (Store data).
![FLUX](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/FLUX.PNG)

# Description of Flux

In the Flux pattern, the Store is the central authority for all data; any mutations to the data must occur 
within the store. Changes to the Store data are subsequently broadcast to subscribing Views via events. 
Views then update themselves based on the new state of received data.

To request changes to any Store data, Actions may be fired. These Actions are controlled by a central Dispatcher; 
Actions may not occur simultaneously, ensuring that a Store only mutates data once per Action.

The strict unidirectional flow of this Flux pattern enforces data stability, reducing data-related 
runtime errors throughout an application.

# Flux vs MVC

MVC architectures frequently encounter two main problems:
• Poorly defined data flow: The cascading updates which occur across views often lead to 
    a tangled web of events which is difficult to debug.
• Lack of data integrity: Model data can be mutated from anywhere, yielding unpredictable results across the UI.

For example, imagine we have a “master/detail” UI in which the user can select a record from a list (master view) 
and edit it using an auto-populated form (detail view).

With an MVC architecture, the data contained within the Model is shared between both the master and detail Views. 
Each of these views might have its own Controller delegating updates between the Model and the View. 
At any point the data contained within the Model might be updated — and 
it’s difficult to know where exactly that change occurred. Did it happen in one of the Views sharing that Model, or 
in one of the Controllers? Because the Model’s data can be mutated by any actor in the application, 
the risk of data pollution in complex UIs is greater than we’d like.

With a Flux architecture, the Store data is similarly shared between multiple Views. 
However this data can’t be directly mutated — all of the requests to update the data must pass through 
the Action > Dispatcher chain first, eliminating the risk of random data pollution. 
When updates are made to the data, it’s now much easier to locate the code requesting those changes.

# What are stateless components?

If React components are essentially state machines that generate UI markup, then what are stateless components?

Stateless components (a flavor of “reusable” components) are nothing more than pure functions 
that render DOM based solely on the properties provided to them.
```
const StatelessCmp = (props) => {
    return (
        <div className=”my-stateless-component”>
            {props.name}: {props.birthday}
        </div>
    );
};

// ---
ReactDOM.render(
    <StatelessCmp name=”Art” birthday=”10/01/1980” />,
    document.getElementById(“main”)
);
```
As you can see, this component has no need for any internal state — let alone a constructor or lifecycle handlers. 
The output of the component is purely a function of the properties provided to it.

# What is Flux concept in ReactJS? Explain various flux elements including Action, Dispatcher, Store and View. 
# Give a simple practical example of installing and using Flux in an application?

Flux is the architecture of an application that Facebook uses for developing client-side web applications. 
Facebook uses internally when working with React. It is not a framework or a library. 
This is simply a new technique that complements React and the concept of Unidirectional Data Flow.

Facebook dispatcher library is a sort of global pub/sub handler technique which broadcasts payloads to registered callbacks.

Flux can be better explained by defining its individual components:
◾Actions – They are helper methods that facilitate passing data to the Dispatcher.
◾Dispatcher – It is Central hub of app, it receives actions and broadcasts payloads to registered callbacks.
◾Stores – It is said to be Containers for application state & logic that have callbacks registered to the dispatcher. 
    Every store maintains particular state and it will update  when it is needed. 
    It wakes up on a relevant dispatch to retrieve the requested data. It is accomplished by registering with 
    the dispatcher  when constructed. They are  similar to  model in a traditional MVC (Model View Controller), 
    but they manage the state of many objects —  it does not represent a single record of data like ORM models do.
◾Controller Views – React Components  grabs the state from Stores and pass it down through props 
    to child components to view to render application.
# How to use Events in ReactJS? Give an example of using events?

React identifies every events so that it must  have common and consistent behavior  across all the browsers. 
Normally, in normal JavaScript or other frameworks, the onchange event is triggered after 
we have typed something into a Textfield and then “exited out of it”. In  ReactJS we cannot do it in this way.

The explanation is typical and  non-trivial:

<input type=”text” value=”dataValue”> renders an input textbox initialized with the value, “dataValue”.

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
# Key points to member in reacts.
```
state needs to be updated to achieve dynamic UI updates in reactjs.
render API is a MUST for every ReactJS component.
props is used to pass the data from parent to child.
JSX transformer is not compulsory to work with ReactJS.
ReactJS renders HTML tags if the element is defined in lowercase.
ReactJS renders Components (classes) if the element is defined in Uppercase.
To use native javascript as an attribute value, the expression should be wrapped within curly-braces{}
state is used to trigger a UI update.
A component can't mutate its properties as and when required.
An owner component defines its children component within render method.
A parent component could access or read its children components properties.
Data flow from owner to owned components using props.
Change or update to large number of nodes is optimized using Batching and Change detection. 
getDefaultProps  method defines the default values for properties, props.
PropTypes is used for Validation.
Mixins are used to take care of cross-cutting concerns.
Life cycle methods of a components fall under Mounting, Updating, Unmounting categories.
Pre and post lifecycle methods of components are represented using Will, Did.  
getInitialState, componentWillMount mounting methods is/are invoked before the component is inserted into DOM.
forceUpdate , setState  methods change the state of the component.
The default value of input field could be set using defaultValue attribute.
Input field that does not supply a value is called as Uncontrolled component. 
The value of textarea is not set using its children in the same way like HTML. 
```

# How to use Forms in ReactJS? Give an example of using Forms in ReactJS by developing a User Registration Form?
In React’s virtual DOM, HTML Input element presents an interesting problem. With the others DOM environment, 
we can  render the input or textarea and thus allows the browser maintain its   state that is (its value). 
we can then get and set the value implicitly with the DOM API.
In HTML, form elements such as <input>, <textarea>, and <select> itself  maintain 
their own state and update its state  based on the input provided by user .In React, components’ mutable state is handled by 
the state property  and is only updated by setState().
◾HTML <input> and <textarea> components use the value attribute.
◾HTML <input> checkbox and radio components, checked attribute is used.
◾<option> (within <select>) components, selected attribute is used for select box.

```
var AccountFields = React.createClass({

  render: function() {
    return ( <div>
     <div> <label>Name</label> </div>
     <div> <input type="text"
             ref="name"
             defaultValue='Imran' /></div>

      <div> <label>Password</label></div>
      <div><input type="password"
             ref="password"
             defaultValue='' /></div>
      <div> <label>Email</label></div>
      <div><input type="email"
             ref="email"
             defaultValue='test.example.com' /></div>
      <button onClick={ this.saveAndContinue }>Save and Continue</button></div>
    )
  },

  saveAndContinue: function(e) {

  console.log(this.refs);
  }
});

ReactDOM.render(  <AccountFields />,   document.getElementById('content') );

```
