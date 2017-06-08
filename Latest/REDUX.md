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

