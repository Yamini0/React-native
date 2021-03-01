# Functional Components Vs Class Components

In React Native, there are two main types of components that make up an application: **functional components** and **class components**. These are structured the same as they would be in a regular React app for the web.

Let's start with **Class Components**.

## Class Components

Sometimes Class Components also known as Stateful Component.

Class components are JavaScript ES2015 classes that extend a base class from React called Component.

Class Component must have render() method returning html.It has complex UI Logic.In Class Component you pass props to class components and access them with this.props

    ```
    import React from 'react';
    import {Text } from 'react-native';
    class App extends Component {
    render () {
        return (
            <Text>Hello World!</Text>
            )
        }
    }
    ```

### Lifecycle method or Lifecycle hooks in Class Component

1. **Mounting():**

   - When an instance of a component is being created and inserted into the DOM.
   - It has 4 method constructor(),static getDerivedStateFromProps(),render() and componentDidMount().

     - **Constructor(props)**: A special function that will get called whenever a new component is created.
     - Initializing the state binding the event handler.
     - Super(props) that directly overites this.state .

     - **static getDerivedStateFromProps(props,state)**: when the state of the component depends on changes.

     - **render()**: we read props and state and return jsx.
     - **componentDidMount()**:invoked immediately after a component and all its children components have been redered to the DOM.

2. **Updating():**

   - When a component is being re-rendered as a result of chnage to either its props or state.
   - It has 5 lifecycle static getDerivedStateFromProps(),shouldComponentUpdate(),render(),getSnapshotUpdate() and componentDidupdate().
     - **getDerivedStateFromProps()**: This is the first method that is called when a component gets updated. This is still the natural place to set the state object based on the initial.
     - **shouldComponentUpdate()**: In this method you can return a Boolean value that specifies whether React should continue with the rendering or not. The default value is true.
     - **getSnapshotBeforeUpdate()**: The getSnapshotBeforeUpdate() method you have access to the props and state before the update, meaning that even after the update, you can check what the values were before the update. If the getSnapshotBeforeUpdate() method is present, you should also include the componentDidUpdate() method, otherwise you will get an error.
     - **componentDidUpdate()**: Thee componentDidUpdate() method is called after the component is updated in the DOM.

3. **UnMounting:**

   - Used when component is being removed from the DOM.
   - It has 1 lifecycle componentWillUnmount().

4. **Error Handeling:**

   - When there is an error during rendering.
   - It has 2 lifecycle static getDerivedStateFromProps() and componentDidCatch.

## Functional Components

Functional components are simpler. They don’t manage their own state or have access to the lifecycle methods provided by React Native. They are literally plain old JavaScript functions, and are sometimes called stateless components.

It is simple javascript functions that simply returns html UI. It is also called “stateless” components because they simply accept data and display them in some form that is they are mainly responsible for rendering UI.

It accept properties(props) in function and return html(JSX)
It gives solution without using state.

There is no render method used in functional components.
These can be typically defined using arrow functions but can also be created with the regular function keyword.

     ```
     import React from 'react';
     import { Text} from 'react-native';
     const App = () => {
    return (
        <Text>Hello World</Text>
        );
    }
    export default App;

````

### Lifecycle method or Lifecycle hooks in functional component

Component lifecycle method do not exist in functional component,because a functional component is just a plain JavaScript function, we cannot use setState() method inside component. That’s why they also get called functional stateless components.

We can use React Hooks in functional component,`useEffect()` hook can be used to replicate lifecycle behaviour, and `useState` can be used to store state in a functional component.

    ```
    const User = (props) => {
    const [values, setValues] = useState({
    email: “”,
    password: “”
    } );

    useEffect(() => {
    if(!props.fetched) {
    props.fetchData();
    }
    console.log(‘mount it!’);
    }, []);

    return(

     )
    }
```

NOTE: By passing an empty array as second argument in useEffect triggers the callback in useEffect only after the initial render thus replicating `componentDidMount` lifecycle behaviour.

### So, Why to use Functional Components instead of Class Component?

Benefits you get by using functional components in React-Native:
1. Functional component are much easier to read and test because they are plain JavaScript functions without state or lifecycle-hooks
2. It has less code which makes it more readable
3. It will get easier to separate container and presentational components because you need to think more about your component’s state if you don’t have access to setState() in your component

**Conclusion:**If you are writing a presentational component which doesn’t have its own state or needs to access a lifecycle hook,use functional component as much as possible. For state management you can use class component.
````
