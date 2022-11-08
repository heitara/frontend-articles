# The Component Lifecycle

**Each component has several “lifecycle methods” that you can override to run code at particular times in the process.**

#
1. **`Mounting`**
> When an instance of a component is being created and inserted into the DOM

**Commonly Used Lifecycle Methods:**
- constructor()
  - The constructor for a React component is called before it is mounted. When implementing the constructor for a React.Component subclass, you should call super(props) before any other statement. Otherwise, this.props will be undefined in the constructor, which can lead to bugs.<br>Typically, in React constructors are only used for initializing local state by assigning an object to this.state or binding event handler methods to an instance. 
- static getDerivedStateFromProps()
  - getDerivedStateFromProps is invoked right before calling the render method, both on the initial mount and on subsequent updates. It should return an object to update the state, or null to update nothing.
- render()
  - The render() method is the only required method in a class component. When called, it should examine this.props and this.state and return one of many different types (like Booleans,null, string, numbers, etc.)<br> This function should be pure, meaning that it does not modify component state, it returns the same result each time it’s invoked, and it does not directly interact with the browser.
- componentDidMount()
  - componentDidMount() is invoked immediately after a component is mounted.

#
2. Updating
> When a component is being re-rendered as a result of changes to either It's props or state.

**Commonly Used Lifecycle Methods:**
- static getDerivedStateFromProps()
  - This method is invoked right before calling the render method, both on the initial mount and on subsequent updates. It should return an object to update the state, or null to update nothing.
- shouldComponentUpdate()
  - This method is invoked before rendering when new props or state are being received. Defaults to true.<br>It lets React know if a component’s output is not affected by the current change in state or props.
- render()
- getSnapshotBeforeUpdate()
  - This method is invoked right before the most recently rendered output is committed to e.g. the DOM. It enables your component to capture some information from the DOM (e.g. scroll position) before it is potentially changed. Any value returned by this lifecycle method will be passed as a parameter to componentDidUpdate().
- componentDidUpdate()
  - componentDidUpdate() is invoked immediately after updating occurs. This method is not called for the initial render.

#
3. Unmounting
> When a compoenent is being removed from the DOM.

**Commonly Used Lifecycle Methods:**
- componentWillUnmount()
  - This method is invoked immediately before a component is unmounted and destroyed. Perform any necessary cleanup in this method, such as invalidating timers, canceling network requests, or cleaning up any subscriptions that were created in componentDidMount().

#
4. Error Handling
> When there is an error during rendering, in a lifecycle method, or in the constructor of any child component.

**Commonly Used Lifecycle Methods:**
- static getDerivedStateFromError()
  - This lifecycle is invoked after an error has been thrown by a descendant component. It receives the error that was thrown as a parameter and should return a value to update state.
- componentDidCatch()
  - This lifecycle is invoked after an error has been thrown by a descendant component. It receives two parameters -  The `error` that was thrown and an object with a componentStack key containing information about which component threw the error.


