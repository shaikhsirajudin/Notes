![REDUX](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/Redux.PNG)

# What is Redux:?
Its a state container for your javascript applications.

# Redux - Basics Principal

•	. Single source of truth
•	. Read only state
•	. State transformed using pure functions.



# Why do you need a state container?
To manage the state of your application.

# What is the state of your application?
When you start writing  application from scratch things are simple, the of number of variables 
that you want to keep a track of is less and also probably they are static but as the complexity 
of your application starts growing you will see that you will make a lot of rest service calls, 
lots of third-party calls there's a chain of callbacks that's going on also the number of variables 
in your application keep on increasing now it become complex app, now you don’t have concrete way of 
managing your state then if something breaks in your application logic or rather if you see your UI 
and see that a particular piece of the UI is broken to figure out what piece of functionality actually 
it’s the hard thing, And answering to the question e.g.  If state of my application changes 
from A to B let's say what are the UI pieces that are affected due to it. What kind of side effects or 
other effects of that should I expect in my application such questions seem pretty difficult to be answered?

If you go down the Redux route it's like tailor-made for answering such questions and you should start thinking 
of building your application in this way so when I say the Redux. The way you start building an application 
is by thinking very first and foremost about the state of your application now in the case of a to-d-app.
Let’s start thinking of the state of a to-do application as an array of to do's right. 
So let’s go through these three commandments, if you want to know about Redux absolutely 
you should know about these things 

# Three Principles Redux
Redux can be described in three fundamental principles:

1) Single source of truth : The state of your whole application is stored in an object tree within a single store.
This makes it easy to create universal apps, as the state from your server can be serialized and hydrated into 
the client with no extra coding effort. A single state tree also makes it easier to debug or inspect an application; 
it also enables you to persist your app's state in development, for a faster development cycle. 
Some functionality which has been traditionally difficult to implement.

2) State is read-only :The only way to change the state is to emit an action, an object describing what happened.
This ensures that neither the views nor the network callbacks will ever write directly to the state. 
Instead, they express an intent to transform the state. Because all changes are centralized and 
happen one by one in a strict order, there are no subtle race conditions to watch out for. 
As actions are just plain objects, they can be logged, serialized, stored, and later replayed 
for debugging or testing purposes.

3)Changes are made with pure functions :To specify how the state tree is transformed by actions, 
you write pure reducers.
Reducers are just pure functions that take the previous state and an action, and return the next state. 
Remember to return new state objects, instead of mutating the previous state. You can start with a single reducer, 
and as your app grows, split it off into smaller reducers that manage specific parts of the state tree. 
Because reducers are just functions, you can control the order in which they are called, pass additional data, 
or even make reusable reducers for common tasks such as pagination.

# When should I use Redux?

In general, use Redux when you have reasonable amounts of data changing over time, you need a single source of truth, 
and you find that approaches like keeping everything in a top-level React component's state are no longer sufficient.

However, it's also important to understand that using Redux comes with tradeoffs. It's not designed to be the shortest or 
fastest way to write code. It's intended to help answer the question "When did a certain slice of state change, 
and where did the data come from?", with predictable behavior. It does so by asking you to follow specific 
constraints in your application: store your application's state as plain data, describe changes as plain objects, 
and handle those changes with pure functions that apply updates immutably. This is often the source of complaints 
about "boilerplate". These constraints require effort on the part of a developer, but also open up a number of 
additional possibilities (such as store persistence and synchronization).

If you're just learning React, you should probably focus on thinking in React first, then look at Redux once 
you better understand React and how Redux might fit into your application.

In the end, Redux is just a tool. It's a great tool, and there's some great reasons to use it, 
but there's also reasons you might not want to use it. Make informed decisions about your tools, 
and understand the tradeoffs involved in each decision.

# Can Redux only be used with React?

Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, 
but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. 
Redux simply provides a subscription mechanism which can be used by any other code. That said, 
it is most useful when combined with a declarative view implementation that can infer the UI updates from the state changes, 
such as React or one of the similar libraries available.

# Do I need to have a particular build tool to use Redux?

Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. 
You should be able to use it regardless of your JavaScript build process. 
Redux also offers a UMD build that can be used directly without any build process at all. 
The counter-vanilla example demonstrates basic ES5 usage with Redux included as a  <script>  tag. As the relevant pull request says:

The new Counter Vanilla example is aimed to dispel the myth that Redux requires Webpack, React, hot reloading, 
sagas, action creators, constants, Babel, npm, CSS modules, decorators, fluent Latin

# How do I share state between two reducers? Do I have to use  combineReducers ?

The suggested structure for a Redux store is to split the state object into multiple “slices” or “domains” by key, 
and provide a separate reducer function to manage each individual data slice. 
This is similar to how the standard Flux pattern has multiple independent stores, and Redux provides 
the  combineReducers  utility function to make this pattern easier. However, it's important to note 
that  combineReducers  is not required—it is simply a utility function for the common use case of 
having a single reducer function per state slice, with plain JavaScript objects for the data.

Many users later want to try to share data between two reducers, but find that  combineReducers  does not 
allow them to do so. There are several approaches that can be used:

•If a reducer needs to know data from another slice of state, the state tree shape may need to be reorganized so 
that a single reducer is handling more of the data.

•You may need to write some custom functions for handling some of these actions. 
This may require replacing  combineReducers  with your own top-level reducer function. 
You can also use a utility such as reduce-reducers to run  combineReducers  to handle most actions, 
but also run a more specialized reducer for specific actions that cross state slices.

•Async action creators such as redux-thunk have access to the entire state through  getState() . 
An action creator can retrieve additional data from the state and put it in an action, so that each reducer 
has enough information to update its own state slice.

In general, remember that reducers are just functions—you can organize them and subdivide them any way you want, 
and you are encouraged to break them down into smaller, reusable functions (“reducer composition”). 
While you do so, you may pass a custom third argument from a parent reducer if a child reducer needs 
additional data to calculate its next state. You just need to make sure that together they follow 
the basic rules of reducers:  (state, action) => newState , and update state immutably rather than mutating it directly.

# Do I have to use the  switch  statement to handle actions?

No. You are welcome to use any approach you'd like to respond to an action in a reducer. 
The  switch  statement is the most common approach, but it's fine to use  if  statements, a lookup table of functions, 
or to create a function that abstracts this away. In fact, while Redux does require that action objects contain a  type  field, 
your reducer logic doesn't even have to rely on that to handle the action. That said, 
the standard approach is definitely using a switch statement or a lookup table based on  type .

# Do I have to put all my state into Redux? Should I ever use React's  setState() ?

There is no “right” answer for this. Some users prefer to keep every single piece of data in Redux, 
to maintain a fully serializable and controlled version of their application at all times. 
Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, 
inside a component's internal state. 

Using local component state is fine. As a developer, it is your job to determine what kinds of state make up your application, 
and where each piece of state should live. Find a balance that works for you, and go with it.

Some common rules of thumb for determing what kind of data should be put into Redux:
•Do other parts of the application care about this data?
•Do you need to be able to create further derived data based on this original data?
•Is the same data being used to drive multiple components?
•Is there value to you in being able to restore this state to a given point in time (ie, time travel debugging)?
•Do you want to cache the data (ie, use what's in state if it's already there instead of re-requesting it)?

There are a number of community packages that implement various approaches for storing per-component state 
in a Redux store instead, such as redux-ui, redux-component, redux-react-local, and more. 
It's also possible to apply Redux's principles and concept of reducers to the task of updating local component state as well, 
along the lines of  this.setState( (previousState) => reducer(previousState, someAction)) .

# Can I put functions, promises, or other non-serializable items in my store state?

It is highly recommended that you only put plain serializable objects, arrays, and primitives into your store. 
It's technically possible to insert non-serializable items into the store, but doing so can break the ability 
to persist and rehydrate the contents of a store, as well as interfere with time-travel debugging.

If you are okay with things like persistence and time-travel debugging potentially not working as intended, 
then you are totally welcome to put non-serializable items into your Redux store. Ultimately, it's your application, 
and how you implement it is up to you. As with many other things about Redux, 
just be sure you understand what tradeoffs are involved.

# How do I organize nested or duplicate data in my state?
Data with IDs, nesting, or relationships should generally be stored in a “normalized” fashion: 
each object should be stored once, keyed by ID, and other objects that reference it should only store the ID rather 
than a copy of the entire object. It may help to think of parts of your store as a database, 
with individual “tables” per item type. Libraries such as normalizr and redux-orm can provide help and 
abstractions in managing normalized data.

# Can or should I create multiple stores? Can I import my store directly, and use it in components myself?

The original Flux pattern describes having multiple “stores” in an app, each one holding a different area of domain data. 
This can introduce issues such as needing to have one store “ waitFor ” another store to update. 
This is not necessary in Redux because the separation between data domains is already achieved by 
splitting a single reducer into smaller reducers.

As with several other questions, it is possible to create multiple distinct Redux stores in a page, 
but the intended pattern is to have only a single store. Having a single store enables using the Redux DevTools, 
makes persisting and rehydrating data simpler, and simplifies the subscription logic.

Some valid reasons for using multiple stores in Redux might include:
•Solving a performance issue caused by too frequent updates of some part of the state, 
when confirmed by profiling the app.
•Isolating a Redux app as a component in a bigger application, in which case you might want to 
create a store per root component instance.

However, creating new stores shouldn't be your first instinct, especially if you come from a Flux background. 
Try reducer composition first, and only use multiple stores if it doesn't solve your problem.

Similarly, while you can reference your store instance by importing it directly, this is not a recommended pattern in Redux. 
If you create a store instance and export it from a module, it will become a singleton. 
This means it will be harder to isolate a Redux app as a component of a larger app, if this is ever necessary, 
or to enable server rendering, because on the server you want to create separate store instances for every request.

With React Redux, the wrapper classes generated by the  connect()  function do actually look for  props.store  if it exists, 
but it's best if you wrap your root component in  <Provider store={store}>  and let React Redux worry about passing the store down. 
This way components don't need to worry about importing a store module, and isolating a Redux app or 
enabling server rendering is much easier to do later.

# Is it OK to have more than one middleware chain in my store enhancer? 
# What is the difference between  next  and  dispatch  in a middleware function?

Redux middleware act like a linked list. Each middleware function can either call  next(action)  
to pass an action along to the next middleware in line, call  dispatch(action)  to restart the processing at 
the beginning of the list, or do nothing at all to stop the action from being processed further.

This chain of middleware is defined by the arguments passed to the  applyMiddleware  function used when creating a store.
Defining multiple chains will not work correctly, as they would have distinctly different  dispatch  references and 
the different chains would effectively be disconnected.

# How do I subscribe to only a portion of the state? Can I get the dispatched action as part of the subscription?

Redux provides a single  store.subscribe  method for notifying listeners that the store has updated. 
Listener callbacks do not receive the current state as an argument—it is simply an indication that something has changed. 
The subscriber logic can then call  getState()  to get the current state value.

This API is intended as a low-level primitive with no dependencies or complications, and can be used to build 
higher-level subscription logic. UI bindings such as React Redux can create a subscription for each connected component. 
It is also possible to write functions that can intelligently compare the old state vs the new state, 
and execute additional logic if certain pieces have changed. Examples include redux-watch and redux-subscribe 
which offer different approaches to specifying subscriptions and handling changes.

The new state is not passed to the listeners in order to simplify implementing store enhancers such as the Redux DevTools. 
In addition, subscribers are intended to react to the state value itself, not the action. 
Middleware can be used if the action is important and needs to be handled specifically.

# Why should  type  be a string, or at least serializable? Why should my action types be constants?
As with state, serializable actions enable several of Redux's defining features, such as time travel debugging, 
and recording and replaying actions. Using something like a  Symbol  for the  type  value or using  instanceof  
checks for actions themselves would break that. Strings are serializable and easily self-descriptive, 
and so are a better choice. Note that it is okay to use Symbols, Promises, or other non-serializable values in an action 
if the action is intended for use by middleware. Actions only need to be serializable by the time they actually reach 
the store and are passed to the reducers.

We can't reliably enforce serializable actions for performance reasons, so Redux only checks that every action 
is a plain object, and that the  type  is defined. The rest is up to you, but you might find that keeping everything 
serializable helps debug and reproduce issues.

Encapsulating and centralizing commonly used pieces of code is a key concept in programming. While it is certainly possible 
to manually create action objects everywhere, and write each  type  value by hand, defining reusable constants makes 
maintaining code easier. If you put constants in a separate file, you can check your  import  statements against typos 
so you can't accidentally use the wrong string.

# Is there always a one-to-one mapping between reducers and actions?
No. We suggest you write independent small reducer functions that are each responsible for updates to a specific slice of state. 
We call this pattern “reducer composition”. A given action could be handled by all, some, or none of them. 
This keeps components decoupled from the actual data changes, as one action may affect different parts of the state tree, 
and there is no need for the component to be aware of this. Some users do choose to bind them more tightly together, 
such as the “ducks” file structure, but there is definitely no one-to-one mapping by default, 
and you should break out of such a paradigm any time you feel you want to handle an action in many reducers.

# How can I represent “side effects” such as AJAX calls? Why do we need things like “action creators”, “thunks”, 
# and “middleware” to do async behavior?

Any meaningful web app needs to execute complex logic, usually including asynchronous work such as making AJAX requests. 
That code is no longer purely a function of its inputs, and the interactions with the outside world are known as “side effects”

Redux is inspired by functional programming, and out of the box, has no place for side effects to be executed. In particular, 
reducer functions must always be pure functions of  (state, action) => newState . However, Redux's middleware makes 
it possible to intercept dispatched actions and add additional complex behavior around them, including side effects.

In general, Redux suggests that code with side effects should be part of the action creation process. While that logic 
can be performed inside of a UI component, it generally makes sense to extract that logic into a reusable function so that 
the same logic can be called from multiple places—in other words, an action creator function.

The simplest and most common way to do this is to add the Redux Thunk middleware that lets you write action creators 
with more complex and asynchronous logic. Another widely-used method is Redux Saga which lets you write more synchronous-looking 
code using generators, and can act like “background threads” or “daemons” in a Redux app. Yet another approach is Redux Loop, 
which inverts the process by allowing your reducers to declare side effects in response to state changes and 
have them executed separately. Beyond that, there are many other community-developed libraries and ideas,
each with their own take on how side effects should be managed.

# Should I dispatch multiple actions in a row from one action creator?

There's no specific rule for how you should structure your actions. Using an async middleware like Redux Thunk 
certainly enables scenarios such as dispatching multiple distinct but related actions in a row, dispatching actions to represent 
progression of an AJAX request, dispatching actions conditionally based on state, or even dispatching an action and 
checking the updated state immediately afterwards.

In general, ask if these actions are related but independent, or should actually be represented as one action.
 Do what makes sense for your own situation but try to balance the readability of reducers with readability of the action log. 
 For example, an action that includes the whole new state tree would make your reducer a one-liner, 
 but the downside is now you have no history of why the changes are happening, so debugging gets really difficult. 
 On the other hand, if you emit actions in a loop to keep them granular, it's a sign that you might want to 
 introduce a new action type that is handled in a different way.

Try to avoid dispatching several times synchronously in a row in the places where you're concerned about performance. 
There are a number of addons and approaches that can batch up dispatches as well.

# What are the benefits of immutability?
Immutability can bring increased performance to your app, and leads to simpler programming and debugging, 
as data that never changes is easier to reason about than data that is free to be changed arbitrarily throughout your app.

In particular, immutability in the context of a Web app enables sophisticated change detection techniques to be implemented 
simply and cheaply, ensuring the computationally expensive process of updating the DOM occurs only 
when it absolutely has to (a cornerstone of React’s performance improvements over other libraries).

# Why is immutability required by Redux?

•Both Redux and React-Redux employ shallow equality checking. In particular:
◦Redux's  combineReducers  utility shallowly checks for reference changes caused by the reducers that it calls.
◦React-Redux's  connect  method generates components that shallowly check reference changes to the root state, 
and the return values from the  mapStateToProps  function to see if the wrapped components actually need to re-render. 
Such shallow checking requires immutability to function correctly.

•Immutable data management ultimately makes data handling safer.
•Time-travel debugging requires that reducers be pure functions with no side effects, 
so that you can correctly jump between different states.

# Why does Redux’s use of shallow equality checking require immutability?

Redux's use of shallow equality checking requires immutability if any connected components are to be updated correctly. 
To see why, we need to understand the difference between shallow and deep equality checking in JavaScript.

# How do shallow and deep equality checking differ?

Shallow equality checking (or reference equality) simply checks that two different variables reference the same object; 
in contrast, deep equality checking (or value equality) must check every value of two objects' properties.

A shallow equality check is therefore as simple (and as fast) as  a === b , whereas a deep equality check involves 
a recursive traversal through the properties of two objects, comparing the value of each property at each step. 

It's for this improvement in performance that Redux uses shallow equality checking.

# How does Redux use shallow equality checking?
Redux uses shallow equality checking in its  combineReducers  function to return either a new mutated copy of 
the root state object, or, if no mutations have been made, the current root state object.

# How does  combineReducers  use shallow equality checking?
The suggested structure for a Redux store is to split the state object into multiple "slices" or "domains" by key, 
and provide a separate reducer function to manage each individual data slice.

 combineReducers  makes working with this style of structure easier by taking a  reducers  argument that’s defined as a 
 hash table comprising a set of key/value pairs, where each key is the name of a state slice, 
 and the corresponding value is the reducer function that will act on it.

So, for example, if your state shape is  { todos, counter } , the call to  combineReducers  would be:
 combineReducers({ todos: myTodosReducer, counter: myCounterReducer })

where:
•the keys  todos  and  counter  each refer to a separate state slice;
•the values  myTodosReducer  and  myCounterReducer  are reducer functions, with each acting on 
the state slice identified by the respective key.

 combineReducers  iterates through each of these key/value pairs. For each iteration, it:
•creates a reference to the current state slice referred to by each key;
•calls the appropriate reducer and passes it the slice;
•creates a reference to the possibly-mutated state slice that's returned by the reducer.

As it continues through the iterations,  combineReducers  will construct a new state object with 
the state slices returned from each reducer. This new state object may or may not be different from the current state object. 
It is here that  combineReducers  uses shallow equality checking to determine whether the state has changed.

Specifically, at each stage of the iteration,  combineReducers  performs a shallow equality check on 
the current state slice and the state slice returned from the reducer. If the reducer returns a new object, 
the shallow equality check will fail, and  combineReducers  will set a  hasChanged  flag to true. 

After the iterations have completed,  combineReducers  will check the state of the  hasChanged  flag. 
If it’s true, the newly-constructed state object will be returned. If it’s false, the current state object is returned.

This is worth emphasising: If the reducers all return the same  state  object passed to them, 
then  combineReducers  will return the current root state object, not the newly updated one.

# How does React-Redux use shallow equality checking?

React-Redux uses shallow equality checking to determine whether the component it’s wrapping needs to be re-rendered.

To do this, it assumes that the wrapped component is pure; that is, that the component will produce 
the same results given the same props and state.

By assuming the wrapped component is pure, it need only check whether the root state object or the values returned from 
 mapStateToProps  have changed. If they haven’t, the wrapped component does not need re-rendering.

It detects a change by keeping a reference to the root state object, and a reference to each value in the props object 
that's returned from the  mapStateToProps  function.

It then runs a shallow equality check on its reference to the root state object and the state object passed to it, 
and a separate series of shallow checks on each reference to the props object’s values and those 
that are returned from running the  mapStateToProps  function again.

# Why does React-Redux shallowly check each value within the props object returned from  mapStateToProp ?

React-Redux performs a shallow equality check on on each value within the props object, 
not on the props object itself.

It does so because the props object is actually a hash of prop names and their values 
(or selector functions that are used to retrieve or generate the values), such as in this example:
```
function mapStateToProps(state) {
  return { 
        todos: state.todos, // prop value
        visibleTodos: getVisibleTodos(state) // selector
    }
}

export default connect(mapStateToProps)(TodoApp)
```

As such, a shallow equality check of the props object returned from repeated calls to  mapStateToProps  would always fail, 
as a new object would be returned each time.

React-Redux therefore maintains separate references to each value in the returned props object. 

# How does React-Redux use shallow equality checking to determine whether a component needs re-rendering?

Each time React-Redux’s  connect  function is called, it will perform a shallow equality check on its stored reference to 
the root state object, and the current root state object passed to it from the store. If the check passes, 
the root state object has not been updated, and so there is no need to re-render the component, or even call  mapStateToProps .

If the check fails, however, the root state object has been updated, and so  connect  will call  mapStateToProps to see if 
the props for the wrapped component have been updated. 

It does this by performing a shallow equality check on each value within the object individually, and will only trigger a 
re-render if one of those checks fails.

In the example below, if  state.todos  and the value returned from  getVisibleTodos()  do not change on successive calls to  connect , 
then the component will not re-render .
```
function mapStateToProps(state) {
  return { 
        todos: state.todos, // prop value
        visibleTodos: getVisibleTodos(state) // selector
    }
}

export default connect(mapStateToProps)(TodoApp)
```

Conversely, in this next example (below), the component will always re-render, as the value of  todos  is always a new object, 
regardless of whether or not its values change:
```
// AVOID - will always cause a re-render
function mapStateToProps(state) {
  return { 
        // todos always references a newly-created object
        todos: {
            all: state.todos,
            visibleTodos: getVisibleTodos(state)
        }
    }
}

export default connect(mapStateToProps)(TodoApp)
```

If the shallow equality check fails between the new values returned from  mapStateToProps  and the previous values 
that React-Redux kept a reference to, then a re-rendering of the component will be triggered.

# Why will shallow equality checking not work with mutable objects?

Shallow equality checking cannot be used to detect if a function mutates an object passed into it if that object is mutable.

This is because two variables that reference the same object will always be equal, regardless of whether the object’s 
values changes or not, as they're both referencing the same object. Thus, the following will always return true:
```
function mutateObj(obj) {
    obj.key = 'newValue';
    return obj;
}

const param = { key: 'originalValue' };
const returnVal = mutateObj(param);

param === returnVal;
//> true
```

The shallow check of  param  and  returnValue  simply checks whether both variables reference the same object, 
which they do. mutateObj()  may return a mutated version of  obj , but it's still the same object as that passed in. 
The fact that its values have been changed within  mutateObj  matters not at all to a shallow check.

# Does shallow equality checking with a mutable object cause problems with Redux?

Shallow equality checking with a mutable object will not cause problems with Redux, but it will cause problems with libraries 
that depend on the store, such as React-Redux.

Specifically, if the state slice passed to a reducer by  combineReducers  is a mutable object, the reducer can modify 
it directly and return it. 

If it does, the shallow equality check that  combineReducers  performs will always pass, as the values of the state slice returned by 
the reducer may have been mutated, but the object itself has not - it’s still the same object that was passed to the reducer.

Accordingly,  combineReducers  will not set its  hasChanged  flag, even though the state has changed. If none of the other 
reducers return a new, updated state slice, the  hasChanged  flag will remain set to false, causing  combineReducers  to return 
the existing root state object.

The store will still be updated with the new values for the root state, but because the root state object itself is still the same object, 
libraries that bind to Redux, such as React-Redux, will not be aware of the state’s mutation, and so will 
not trigger a wrapped component’s re-rendering.

# Why does a reducer mutating the state prevent React-Redux from re-rendering a wrapped component?
If a Redux reducer directly mutates, and returns, the state object passed into it, the values of the root state object will change, 
but the object itself will not.

Because React-Redux performs a shallow check on the root state object to determine if its wrapped components need re-rendering or not, 
it will not be able to detect the state mutation, and so will not trigger a re-rendering.

# Why does a selector mutating and returning a persistent object to  mapStateToProps  prevent React-Redux 
# from re-rendering a wrapped component?

If one of the values of the props object returned from  mapStateToProps  is an object that persists across calls to  connect  
(such as, potentially, the root state object), yet is directly mutated and returned by a selector function, 
React-Redux will not be able to detect the mutation, and so will not trigger a re-render of the wrapped component.

As we’ve seen, the values in the mutable object returned by the selector function may have changed, but the object itself has not, 
and shallow equality checking only compares the objects themselves, not their values.

For example, the following  mapStateToProps  function will never trigger a re-render:
// State object held in the Redux store
```
const state = {
    user: {
        accessCount: 0,
        name: 'keith'
    }
};

// Selector function
const getUser = (state) => {
  ++state.user.accessCount; // mutate the state object
  return state;
}

// mapStateToProps
const mapStateToProps = (state) => ({
    // The object returned from getUser() is always
    // the same object, so this wrapped
    // component will never re-render, even though it's been
    // mutated
    userRecord: getUser(state)
});


const a = mapStateToProps(state);
const b = mapStateToProps(state);

a.userRecord === b.userRecord;
//> true
```

Note that, conversely, if an immutable object is used, the component may re-render when it should not.

# How does immutability enable a shallow check to detect object mutations?

If an object is immutable, any changes that need to be made to it within a function must be made to a copy of the object. 

This mutated copy is a separate object from that passed into the function, and so when it is returned, 
a shallow check will identify it as being a different object from that passed in, and so will fail.

# How can immutability in your reducers cause components to render unnecessarily?

You cannot mutate an immutable object; instead, you must mutate a copy of it, leaving the original intact.

That’s perfectly OK when you mutate the copy, but in the context of a reducer, if you return a copy that hasn’t been mutated, 
Redux’s  combineReducers  function will still think that the state needs to be updated, as you're returning an 
entirely different object from the state slice object that was passed in.

 combineReducers  will then return this new root state object to the store. The new object will have the same values as 
 the current root state object, but because it's a different object, it will cause the store to be updated, 
 which will ultimately cause all connected components to be re-rendered unnecessarily.

To prevent this from happening, you must always return the state slice object that’s passed into a reducer if 
the reducer does not mutate the state.

# How can immutability in  mapStateToProps  cause components to render unnecessarily?

Certain immutable operations, such as an Array filter, will always return a new object, even if 
the values themselves have not changed.

If such an operation is used as a selector function in  mapStateToProps , the shallow equality check that React-Redux 
performs on each value in the props object that’s returned will always fail, as the selector is returning a new object each time.

As such, even though the values of that new object have not changed, the wrapped component will always be re-rendered, 

For example, the following will always trigger a re-render:
// A JavaScript array's 'filter' method treats the array as immutable,
// and returns a filtered copy of the array.
```
const getVisibleTodos = (todos) => todos.filter(t => !t.completed);

const state = {
  todos: [
    {
      text: 'do todo 1',
      completed: false
    },
    {
       text: 'do todo 2',
      completed: true
    }]
}


const mapStateToProps = (state) => ({
    // getVisibleTodos() always returns a new array, and so the 
    // 'visibleToDos' prop will always reference a different array, 
    // causing the wrapped component to re-render, even if the array's
    // values haven't changed
    visibleToDos: getVisibleTodos(state.todos)
})

const a = mapStateToProps(state);
//  Call mapStateToProps(state) again with exactly the same arguments
const b = mapStateToProps(state);

a.visibleToDos;
//> { "completed": false, "text": "do todo 1" }

b.visibleToDos;
//> { "completed": false, "text": "do todo 1" }

a.visibleToDos === b.visibleToDos;
//> false
```

Note that, conversely, if the values in your props object refer to mutable objects, your component may not render 
when it should.

# What approaches are there for handling data immutably? Do I have to use Immutable.JS?

You do not need to use Immutable.JS with Redux. Plain JavaScript, if written correctly, is perfectly capable of
 providing immutability without having to use an immutable-focused library. 

However, guaranteeing immutability with JavaScript is difficult, and it can be easy to mutate an object accidentally, 
causing bugs in your app that are extremely difficult to locate. For this reason, using an immutable 
update utility library such as Immutable.JS can significantly improve the reliability of your app, 
and make your app’s development much easier.

# What are the issues with using plain JavaScript for immutable operations?

JavaScript was never designed to provide guaranteed immutable operations. Accordingly, there are several issues you 
need to be aware of if you choose to use it for your immutable operations in your Redux app.

# Accidental Object Mutation

With JavaScript, you can accidentally mutate an object (such as the Redux state tree) quite easily without realising it. 
For example, updating deeply nested properties, creating a new reference to an object instead of a new object, 
or performing a shallow copy rather than a deep copy, can all lead to inadvertent object mutations, 
and can trip up even the most experienced JavaScript coder. 

To avoid these issues, ensure you follow the recommended immutable update patterns for ES6.

# Verbose Code

Updating complex nested state trees can lead to verbose code that is tedious to write and difficult to debug.

# Poor Performance

Operating on JavaScript objects and arrays in an immutable way can be slow, particularly as your state tree grows larger.

Remember, to change an immutable object, you must mutate a copy of it, and copying large objects can be slow as every 
property must be copied.

In contrast, immutable libraries such as Immutable.JS can employ sophisticated optimization techniques such as structural sharing , 
which effectively returns a new object that reuses much of the existing object being copied from.

For copying very large objects, plain JavaScript can be over 100 times slower than an optimized immutable library.

# Why should I use an immutable-focused library such as Immutable.JS?
Immutable-focused libraries such as Immutable.JS have been designed to overcome the issues with immutability inherent within JavaScript, 
providing all the benefits of immutability with the performance your app requires. 

Whether you choose to use such a library, or stick with plain JavaScript, depends on how comfortable you are with adding another
 dependency to your app, or how sure you are that you can avoid the pitfalls inherent within JavaScript’s approach to immutability.

Whichever option you choose, make sure you’re familiar with the concepts of immutability, side effects and mutation. In particular, 
ensure you have a deep understanding of what JavaScript does when updating and copying values in order to guard against 
accidental mutations that will degrade you app’s performance, or break it altogether.

# Why should I choose Immutable.JS as an immutable library?

Immutable.JS was designed to provide immutability in a performant manner in an effort to overcome the limitations of immutability
with JavaScript. Its principle advantages include:

#Guaranteed immutability

Data encapsulated in an Immutable.JS object is never mutated. A new copy is always returned. This contrasts with JavaScript, 
in which some operations do not mutate your data (e.g. some Array methods, including map, filter, forEach, etc.), 
but some do (Array’s pop, push, concat, splice, etc.).

#Rich API

Immutable.JS provides a rich set of immutable objects to encapsulate your data (e.g. Maps, Lists, Sets, Records, etc.), 
and an extensive set of methods to manipulate it, including methods to sort, filter, and group the data, reverse it, 
flatten it, and create subsets.

# Performance

Immutable.JS does a lot work behind the scenes to optimize performance. This is the key to its power, 
as using immutable data structures can involve a lot of expensive copying. In particular, immutably manipulating large, 
complex data sets, such as a nested Redux state tree, can generate many intermediate copies of objects, 
which consume memory and slow down performance as the browser’s garbage collector fights to clean things up.

Immutable.JS avoids this by cleverly sharing data structures under the surface, minimizing the need to copy data. 
It also enables complex chains of operations to be carried out without creating unnecessary (and costly) cloned intermediate 
data that will quickly be thrown away. 

You never see this, of course - the data you give to an Immutable.JS object is never mutated. Rather, it’s the intermediate 
data generated within Immutable.JS from a chained sequence of method calls that is free to be mutated. 
You therefore get all the benefits of immutable data structures with none (or very little) of the potential performance hits.

# What are the issues with using Immutable.JS?

Although powerful, Immutable.JS needs to be used carefully, as it comes with issues of its own. Note, however, 
that all of these issues can be overcome quite easily with careful coding.

#Difficult to interoperate with

JavaScript does not provide immutable data structures. As such, for Immutable.JS to provide its immutable guarantees, 
your data must be encapsulated within an Immutable.JS object (such as a  Map  or a  List , etc.). Once it’s contained in this way, 
it’s hard for that data to then interoperate with other, plain JavaScript objects.

For example, you will no longer be able to reference an object’s properties through standard JavaScript dot or bracket notation. 
Instead, you must reference them via Immutable.JS’s  get()  or  getIn()  methods, which use an awkward syntax that accesses 
properties via an array of strings, each of which represents a property key.

For example, instead of  myObj.prop1.prop2.prop3 , you would use  myImmutableMap.getIn([‘prop1’, ‘prop2’, ‘prop3’]) . 

This makes it awkward to interoperate not just with your own code, but also with other libraries, such as lodash or ramda, 
that expect plain JavaScript objects.

Note that Immutable.JS objects do have a  toJS()  method, which returns the data as a plain JavaScript data structure, 
but this method is extremely slow, and using it extensively will negate the performance benefits that Immutable.JS provides

#Once used, Immutable.JS will spread throughout your codebase
Once you encapsulate your data with Immutable.JS, you have to use Immutable.JS’s  get()  or  getIn()  
property accessors to access it. 

This has the effect of spreading Immutable.JS across your entire codebase, including potentially your components, 
where you may prefer not to have such external dependencies. Your entire codebase must know what is, and what is not, 
an Immutable.JS object. It also makes removing Immutable.JS from your app difficult in the future, should you ever need to.

This issue can be avoided by uncoupling your application logic from your data structures, as outlined in 
the best practices section below.

#No Destructuring or Spread Operators

Because you must access your data via Immutable.JS’s own  get()  and  getIn()  methods, you can no longer use 
JavaScript’s destructuring operator (or the proposed Object spread operator), making your code more verbose.

#Not suitable for small values that change often

Immutable.JS works best for collections of data, and the larger the better. It can be slow when your data comprises lots of small, 
simple JavaScript objects, with each comprising a few keys of primitive values. 

Note, however, that this does not apply to the Redux state tree, which is (usually) represented as a large collection of data.

#Difficult to Debug

Immutable.JS objects, such as  Map ,  List , etc., can be difficult to debug, as inspecting such an object will reveal an 
entire nested hierarchy of Immutable.JS-specific properties that you don’t care about, while your actual data that you do 
care about is encapsulated several layers deep. 

To resolve this issue, use a browser extension such as the Immutable.js Object Formatter, which surfaces your data in Chrome Dev Tools,
and hides Immutable.JS’s properties when inspecting your data.

# Breaks object references, causing poor performance

One of the key advantages of immutability is that it enables shallow equality checking, 
which dramatically improves performance. 

If two different variables reference the same immutable object, then a simple equality check of the two variables is 
enough to determine that they are equal, and that the object they both reference is unchanged. The equality check never
 has to check the values of any of the object’s properties, as it is, of course, immutable.

However, shallow checking will not work if your data encapsulated within an Immutable.JS object is itself an object. 
This is because Immutable.JS’s  toJS()  method, which returns the data contained within an Immutable.JS object as a JavaScript value,
will create a new object every time it’s called, and so break the reference with the encapsulated data.

Accordingly, calling  toJS()  twice, for example, and assigning the result to two different variables will cause an equality 
check on those two variables to fail, even though the object values themselves haven’t changed.

This is a particular issue if you use  toJS()  in a wrapped component’s  mapStateToProps  function, as React-Redux shallowly 
compares each value in the returned props object. For example, the value referenced by the  todos  prop returned from  mapStateToProps  
below will always be a different object, and so will fail a shallow equality check.
```
// AVOID .toJS() in mapStateToProps
function mapStateToProps(state) {
  return { 
        todos: state.get('todos').toJS() // Always a new object
    }
}
```

When the shallow check fails, React-Redux will cause the component to re-render. Using  toJS()  in  mapStateToProps  in this way, 
therefore, will always cause the component to re-render, even if the value never changes, impacting heavily on performance.

# Is Using Immutable.JS worth the effort?

Frequently, yes. There are various tradeoffs and opinions to consider, but there are many good reasons to use Immutable.JS. 
Do not underestimate the difficulty of trying to track down a property of your state tree that has been inadvertently mutated.

Components will both re-render when they shouldn’t, and refuse to render when they should, and tracking down the bug causing 
the rendering issue is hard, as the component rendering incorrectly is not necessarily the one whose properties are 
being accidentally mutated.

This problem is caused predominantly by returning a mutated state object from a Redux reducer. With Immutable.JS, 
this problem simply does not exist, thereby removing a whole class of bugs from your app. 

This, together with its performance and rich API for data manipulation, is why Immutable.JS is worth the effort.

# What are some opinionated Best Practices for using Immutable.JS with Redux?

Immutable.JS can provide significant reliability and performance improvements to your app, but it must be used correctly. 
If you choose to use Immutable.JS (and remember, you are not required to, and there are other immutable libraries you can use), 
follow these opinionated best practices, and you’ll be able to get the most out of it, without tripping up on any of 
the issues it can potentially cause.

# Never mix plain JavaScript objects with Immutable.JS

Never let a plain JavaScript object contain Immutable.JS properties. Equally, never let an Immutable.JS 
object contain a plain JavaScript object.

# Make your entire Redux state tree an Immutable.JS object

For a Redux app, your entire state tree should be an Immutable.JS object, with no plain JavaScript objects used at all. 

•Create the tree using Immutable.JS’s  fromJS()  function. 


•Use an Immutable.JS-aware version of the  combineReducers  function, such as the one in redux-immutable, 
as Redux itself expects the state tree to be a plain JavaScript object.


•When adding JavaScript objects to an Immutable.JS Map or List using Immutable.JS’s  update ,  merge  or  set  methods, 
ensure that the object being added is first converted to an Immutable object using  fromJS() .

```
Example
// avoid
const newObj = { key: value};
const newState = state.setIn(['prop1’], newObj); // <-- newObj has been added as a plain
    // JavaScript object - NOT as an Immutable.JS Map

// recommend
const newObj = { key: value};
const newState = state.setIn(['prop1’], fromJS(newObj)); // <-- newObj is now an
    // Immutable.JS Map
```

# Use Immutable.JS everywhere except your dumb components

Using Immutable.JS everywhere keeps your code performant. Use it in your smart components, your selectors, 
your sagas or thunks, action creators, and especially your reducers. 

Do not, however, use Immutable.JS in your dumb components.

# Limit your use of  toJS() 

 toJS()  is an expensive function and negates the purpose of using Immutable.JS. Avoid its use.

# Your selectors should return Immutable.JS objects

Always.

# Use Immutable.JS objects in your Smart Components

Smart components that access the store via React Redux’s  connect  function must use the Immutable.JS values 
returned by your selectors. Make sure you avoid the potential issues this can cause with unnecessary component re-rendering. 
Memoize your selectors using a library such as reselect if necessary.

# Never use  toJS()  in  mapStateToProps

Converting an Immutable.JS object to a JavaScript object using  toJS()  will return a new object every time. 
If you do this in  mapSateToProps , you will cause the component to believe that the object has changed every time 
the state tree changes, and so trigger an unnecessary re-render.

# Never use Immutable.JS in your Dumb Components

Your dumb components should be pure; that is, they should produce the same output given the same input, 
and have no external dependencies. If you pass such a component an Immutable.JS object as a prop, 
you make it dependent upon Immutable.JS to extract the prop’s value and otherwise manipulate it.

Such a dependency renders the component impure, makes testing the component more difficult, 
and makes reusing and refactoring the component unnecessarily difficult.

# Use a Higher Order Component to convert your Smart Component’s Immutable.JS props to your Dumb Component’s JavaScript props

Something needs to map the Immutable.JS props in your Smart Component to the pure JavaScript props used in your Dumb Component. 
That something is a Higher Order Component (HOC) that simply takes the Immutable.JS props from your Smart Component, 
and converts them using  toJS()  to plain JavaScript props, which are then passed to your Dumb Component.

Here is an example of such a HOC:
```
import React from 'react';
import { Iterable } from 'immutable';

export const toJS = (WrappedComponent) =>
   (wrappedComponentProps) => {
       const KEY = 0;
       const **VALUE = 1;

       const propsJS = Object.entries(wrappedComponentProps)
            .reduce((newProps, wrappedComponentProp)  => {
                newProps[wrappedComponentProp[KEY]] = 
                    Iterable.isIterable(wrappedComponentProp[VALUE]) 
                        ? wrappedComponentProp[VALUE].toJS() 
                        : wrappedComponentProp[VALUE];
                return newProps;
            }, {});

       return <WrappedComponent {...propsJS} />
   };
```

And this is how you would use it in your Smart Component:
```
import { connect } from 'react-redux';

import { toJS } from `./to-js';

import DumbComponent from './dumb.component';

const mapStateToProps = (state) => {
   return {
      /**
      obj is an Immutable object in Smart Component, but it’s converted to a plain 
      JavaScript object by toJS, and so passed to DumbComponent as a pure JavaScript 
      object. Because it’s still an Immutable.JS object here in mapStateToProps, though, 
      there is no issue with errant re-renderings.
      */
       obj: getImmutableObjectFromStateTree(state)
   }
};

export default connect(mapStateToProps)(toJS(DumbComponent));
```

By converting Immutable.JS objects to plain JavaScript values within a HOC, we achieve Dumb Component portability,
but without the performance hits of using  toJS()  in the Smart Component.

Note: if your app requires high performance, you may need to avoid  toJS()  altogether, 
and so will have to use Immutable.JS in your dumb components. However, for most apps this will not be the case, 
and the benefits of keeping Immutable.JS out of your dumb components (maintainability, portability and easier testing) 
will far outweigh any perceived performance improvements of keeping it in.

In addition, using  toJS  in a Higher Order Component should not cause much, if any, performance degradation, 
as the component will only be called when the connected component’s props change. As with any performance issue, 
conduct performance checks first before deciding what to optimise.

# Use the Immutable Object Formatter Chrome Extension to Aid Debugging

Install the Immutable Object Formatter , and inspect your Immutable.JS data without seeing the noise of 
Immutable.JS's own object properties.

# What should my file structure look like? How should I group my action creators and reducers in my project? 
# Where should my selectors go?

Since Redux is just a data store library, it has no direct opinion on how your project should be structured. 
However, there are a few common patterns that most Redux developers tend to use:
•Rails-style: separate folders for “actions”, “constants”, “reducers”, “containers”, and “components”
•Domain-style: separate folders per feature or domain, possibly with sub-folders per file type
•“Ducks”: similar to domain style, but explicitly tying together actions and reducers, often by defining them in the same file

It's generally suggested that selectors are defined alongside reducers and exported, and then reused elsewhere 
(such as in  mapStateToProps  functions, in async action creators, or sagas) to colocate all the code that knows about 
the actual shape of the state tree in the reducer files.

While it ultimately doesn't matter how you lay out your code on disk, it's important to remember that actions and 
reducers shouldn't be considered in isolation. It's entirely possible (and encouraged) for a reducer defined in one folder 
to respond to an action defined in another folder.

# How should I split my logic between reducers and action creators? Where should my “business logic” go?

There's no single clear answer to exactly what pieces of logic should go in a reducer or an action creator. 
Some developers prefer to have “fat” action creators, with “thin” reducers that simply take the data in an action and 
blindly merge it into the corresponding state. Others try to emphasize keeping actions as small as possible, 
and minimize the usage of  getState()  in an action creator. (For purposes of this question, 
other async approaches such as sagas and observables fall in the "action creator" category.)

This comment sums up the dichotomy nicely:

Now, the problem is what to put in the action creator and what in the reducer, the choice between fat and thin action objects. 
If you put all the logic in the action creator, you end up with fat action objects that basically declare the updates to the state. 
Reducers become pure, dumb, add-this, remove that, update these functions. They will be easy to compose. 
But not much of your business logic will be there. If you put more logic in the reducer, you end up with nice, 
thin action objects, most of your data logic in one place, but your reducers are harder to compose 
since you might need info from other branches. You end up with large reducers or reducers that take additional 
arguments from higher up in the state.

Find the balance between these two extremes, and you will master Redux

# How well does Redux “scale” in terms of performance and architecture?
The work done by Redux generally falls into a few areas: processing actions in middleware and reducers 
(including object duplication for immutable updates), notifying subscribers after actions are dispatched, 
and updating UI components based on the state changes. While it's certainly possible for each of these to 
become a performance concern in sufficiently complex situations, there's nothing inherently slow or inefficient about 
how Redux is implemented. In fact, React Redux in particular is heavily optimized to cut down on unnecessary re-renders, 
and React-Redux v5 shows noticeable improvements over earlier versions.

Redux may not be as efficient out of the box when compared to other libraries. For maximum rendering performance in a React application, 
state should be stored in a normalized shape, many individual components should be connected to the store instead of just a few, 
and connected list components should pass item IDs to their connected child list items 
(allowing the list items to look up their own data by ID). This minimizes the overall amount of rendering to be done. 
Use of memoized selector functions is also an important performance consideration.

As for architecture, anecdotal evidence is that Redux works well for varying project and team sizes. 
Redux is currently used by hundreds of companies and thousands of developers, with several hundred thousand monthly installations from NPM.

# Won't calling “all my reducers” for each action be slow?

It's important to note that a Redux store really only has a single reducer function. The store passes the current state and 
dispatched action to that one reducer function, and lets the reducer handle things appropriately.

Obviously, trying to handle every possible action in a single function does not scale well, simply in terms of function size and readability, 
so it makes sense to split the actual work into separate functions that can be called by the top-level reducer. In particular, 
the common suggested pattern is to have a separate sub-reducer function that is responsible for managing updates to 
a particular slice of state at a specific key. The  combineReducers()  that comes with Redux is one of the many possible ways 
to achieve this. It's also highly suggested to keep your store state as flat and as normalized as possible. Ultimately, though, 
you are in charge of organizing your reducer logic any way you want.

However, even if you happen to have many different reducer functions composed together, and even with deeply nested state, 
reducer speed is unlikely to be a problem. JavaScript engines are capable of running a very large number of function calls per second, 
and most of your reducers are probably just using a  switch  statement and returning the existing state by default in response to most actions.

If you actually are concerned about reducer performance, you can use a utility such as redux-ignore or 
reduxr-scoped-reducer to ensure that only certain reducers listen to specific actions. You can also use 
redux-log-slow-reducers to do some performance benchmarking.

# Do I have to deep-clone my state in a reducer? Isn't copying my state going to be slow?

Immutably updating state generally means making shallow copies, not deep copies. Shallow copies are much faster than deep copies, 
because fewer objects and fields have to be copied, and it effectively comes down to moving some pointers around.

However, you do need to create a copied and updated object for each level of nesting that is affected. 
Although that shouldn't be particularly expensive, it's another good reason why you should keep your state normalized and shallow if possible.


Common Redux misconception: you need to deeply clone the state. Reality: if something inside doesn't change, 
keep its reference the same!

# How can I reduce the number of store update events?

Redux notifies subscribers after each successfully dispatched action (i.e. an action reached the store and was handled by reducers). 
In some cases, it may be useful to cut down on the number of times subscribers are called, particularly if 
an action creator dispatches multiple distinct actions in a row.

If you use React, note that you can improve performance of multiple synchronous dispatches by wrapping 
them in  ReactDOM.unstable_batchedUpdates() , but this API is experimental and may be removed in any React release 
so don't rely on it too heavily. Take a look at redux-batched-actions (a higher-order reducer that lets 
you dispatch several actions as if it was one and “unpack” them in the reducer), redux-batched-subscribe 
(a store enhancer that lets you debounce subscriber calls for multiple dispatches), or redux-batch 
(a store enhancer that handles dispatching an array of actions with a single subscriber notification).

# Will having “one state tree” cause memory problems? Will dispatching many actions take up memory?

First, in terms of raw memory usage, Redux is no different than any other JavaScript library. 
The only difference is that all the various object references are nested together into one tree, 
instead of maybe saved in various independent model instances such as in Backbone. Second, a typical Redux 
app would probably have somewhat less memory usage than an equivalent Backbone app because Redux encourages 
use of plain JavaScript objects and arrays rather than creating instances of Models and Collections. 
Finally, Redux only holds onto a single state tree reference at a time. Objects that are no longer referenced in 
that tree will be garbage collected, as usual.

Redux does not store a history of actions itself. However, the Redux DevTools do store actions so they can be replayed, 
but those are generally only enabled during development, and not used in production.

# Why isn't my component re-rendering, or my mapStateToProps running?

Accidentally mutating or modifying your state directly is by far the most common reason why components do not 
re-render after an action has been dispatched. Redux expects that your reducers will update their state “immutably”, 
which effectively means always making copies of your data, and applying your changes to the copies. 
If you return the same object from a reducer, Redux assumes that nothing has been changed, even if you made changes 
to its contents. Similarly, React Redux tries to improve performance by doing shallow equality reference 
checks on incoming props in  shouldComponentUpdate , and if all references are the same, returns  false  to skip actually 
updating your original component.

It's important to remember that whenever you update a nested value, you must also return new copies of anything above 
it in your state tree. If you have  state.a.b.c.d , and you want to make an update to  d , 
you would also need to return new copies of  c ,  b ,  a , and  state . 
This state tree mutation diagram demonstrates how a change deep in a tree requires changes all the way up.

Note that “updating data immutably” does not mean that you must use Immutable.js, although that is certainly an option. 
You can do immutable updates to plain JS objects and arrays using several different approaches:
•Copying objects using functions like  Object.assign()  or  _.extend() , and array functions such as  slice()  and  concat() 
•The array spread operator in ES6, and the similar object spread operator that is proposed for a future version of JavaScript
•Utility libraries that wrap immutable update logic into simpler functions

# Why is my component re-rendering too often?

React Redux implements several optimizations to ensure your actual component only re-renders when actually necessary. 
One of those is a shallow equality check on the combined props object generated by the  mapStateToProps  and  
mapDispatchToProps  arguments passed to  connect . Unfortunately, shallow equality does not help in cases where new array or 
object instances are created each time  mapStateToProps  is called. A typical example might be mapping over an array 
of IDs and returning the matching object references, such as:
```
const mapStateToProps = (state) => {
  return {
    objects: state.objectIds.map(id => state.objects[id])
  }
}
```

Even though the array might contain the exact same object references each time, the array itself is a different reference, 
so the shallow equality check fails and React Redux would re-render the wrapped component.

The extra re-renders could be resolved by saving the array of objects into the state using a reducer, 
caching the mapped array using Reselect, or implementing  shouldComponentUpdate  in the component by hand and 
doing a more in-depth props comparison using a function such as  _.isEqual . Be careful to not make your custom  shouldComponentUpdate()  
more expensive than the rendering itself! Always use a profiler to check your assumptions about performance.

For non-connected components, you may want to check what props are being passed in. A common issue is having a parent component 
re-bind a callback inside its render function, like  <Child onClick={this.handleClick.bind(this)} /> . 
That creates a new function reference every time the parent re-renders. It's generally good practice to only bind callbacks 
once in the parent component's constructor.

# How can I speed up my  mapStateToProps ?

While React Redux does work to minimize the number of times that your  mapStateToProps  function is called, 
it's still a good idea to ensure that your  mapStateToProps  runs quickly and also minimizes the amount of work it does. 
The common recommended approach is to create memoized “selector” functions using Reselect. 
These selectors can be combined and composed together, and selectors later in a pipeline will only run if their inputs have changed. 
This means you can create selectors that do things like filtering or sorting, and ensure that the real work only happens if needed.

# Why don't I have  this.props.dispatch  available in my connected component?

The  connect()  function takes two primary arguments, both optional. The first,  mapStateToProps , 
is a function you provide to pull data from the store when it changes, and pass those values as props to your component. 
The second,  mapDispatchToProps , is a function you provide to make use of the store's  dispatch  function, 
usually by creating pre-bound versions of action creators that will automatically dispatch their actions as soon as they are called.

If you do not provide your own  mapDispatchToProps  function when calling  connect() , React Redux will provide a default version, 
which simply returns the  dispatch  function as a prop. That means that if you do provide your own function,  
dispatch  is not automatically provided. If you still want it available as a prop, you need to explicitly return 
it yourself in your  mapDispatchToProps  implementation.

# Should I only connect my top component, or can I connect multiple components in my tree?

Early Redux documentation advised that you should only have a few connected components near the top of your component tree. 
However, time and experience has shown that that generally requires a few components to know too much about the data 
requirements of all their descendants, and forces them to pass down a confusing number of props.

The current suggested best practice is to categorize your components as “presentational” or “container” components, 
and extract a connected container component wherever it makes sense:


Emphasizing “one container component at the top” in Redux examples was a mistake. Don't take this as a maxim. 
Try to keep your presentation components separate. Create container components by connecting them when it's convenient. 
Whenever you feel like you're duplicating code in parent components to provide data for same kinds of children, 
time to extract a container. Generally as soon as you feel a parent knows too much about “personal” data or actions of its children, 
time to extract a container.

In fact, benchmarks have shown that more connected components generally leads to better performance than fewer connected components.

In general, try to find a balance between understandable data flow and areas of responsibility with your components.

# How can I implement authentication in Redux?

Authentication is essential to any real application. When going about authentication you must keep in mind 
that nothing changes with how you should organize your application and you should implement authentication in 
the same way you would any other feature. It is relatively straightforward:

1.Create action constants for  LOGIN_SUCCESS ,  LOGIN_FAILURE , etc.


2.Create action creators that take in credentials, a flag that signifies whether authentication succeeded, a token, 
or an error message as the payload.


3.Create an async action creator with Redux Thunk middleware or any middleware you see fit to fire a network request 
to an API that returns a token if the credentials are valid. Then save the token in the local storage or show a response 
to the user if it failed. You can perform these side effects from the action creators you wrote in the previous step.


4.Create a reducer that returns the next state for each possible authentication case ( LOGIN_SUCCESS ,  LOGIN_FAILURE , etc).

































