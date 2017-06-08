
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
