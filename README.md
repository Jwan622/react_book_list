Notes:

react/redux

- if something is just getting data from a parent and doesn’t have to talk to redux, it’s a component, not a container.

-a reducer is just a function that returns a piece of application state.

-application state is just a plain js object.

- a container is a component with access to the state managed by redux. also known as smart component.  most parent component that cares about state should be a container.

- to form a connection between react and redux which are two totally diff projects, containers are needed. redux is the data store, react is the view.

-whatever is returned from mapStateToProps will show up as props inside BookList,. state, the argument passed to mapStateToProps, is the entire application state.

- connect is the thing that actually creates a container. connect function takes the component and function and returns a container. connect produces the container. now if the application state changes, the container will rerender.this is due to connect.

- the index.js in reducers will add a key to the global application state, where the ke is whatever we want, and the value is whatever is returned from the reducer that we specify. 

-when we refresh, the reducer starts it all off and sets the state of the container. since state was changed, the container rerenders and the book-list is shown. remember, the reducer just is a function that returns here an array of books. there are no actions involved yet.

- if we want to select a book, we need an action to change the application state with actions. actions help with dynamic application state.

- an action creator is just a function that returns an object which then flows through ALL of the different reducers, which have switch statements to detect the right action.

- tie actioncreator with redux.

-dispathc is a function and is wha connects the action creators to reducers. It takes the return value of the action creator and sends it to the reducers. dispatch is a function. What’s strange is that the wiring between the action creators and the reducers takes place in the container. 

-reducers are only called when actions are called.

- mapDispatchToProps, anything returned from the function will wind up as props. the key we defined ourselves and the value is the return value of the action creator. the key is accessible by this.props.selectBook anytime this.props.actionCreator is called, the result will then flow through the reducer. In this case, anytime a book is selected, we wnat out selectBook action to be called.

- if no use of state, then it’s a functional component, not a class based component.

- to make third party libraries work, like google maps in the react tutorial, we use react refs which are ways to reference a dom element and then place the third party element inside the react dom element. In the tutorial, we placed a google maps directly inside the react ref.

- google controlled field- formelement where value if input is set by state of component, not the other way around. It’s declarative, not imperatively.

- React is all about keeping things simple by using declarative styles to describe UIs. React describes the UI, its end stage, and how it should look.

- application state is changed by reducers and actions. to load our weather data, we dispatch an action, or call an action creator which makes teh ajax request. this is in the weather data react app.


to reach out to redux, need to connect search bar container to redux using connect method from react-redux library.

-in the ocmponent, you get access to the action creator through this.props.actionCreator through

- middleware like redux promise have the ability to stop or manipulate any action before it hits the reducer. So… it does stuff like let ajax promises resolve so that by the time the promise goes to the reducer, it is no longer a promise but data that we can use.

- to connect a container to redux, first import connect from Redux at the top of the container, define a function mapStateToProps and then:

function mapStateToProps({ weather }) { 
  return { weather };
}

