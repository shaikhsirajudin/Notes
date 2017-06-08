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

