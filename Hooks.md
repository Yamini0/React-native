# What is Hooks?

Hooks are a new addition in React. They let you use state and other React features without writing a class. It mainly uses to handle the state and side effects in react functional component. React Hooks are a way to use stateful functions inside a functional component. Hooks don’t work inside classes — they let you use React without classesReact provides a few built-in Hooks like useState and useEffect.

- It Enforces best practices
- Easy to under understand
- Easy to test
- It increases the performance and so on.

# Why we use React Hook?

The first main reason is the Introduce state in a functional component. You know that the states cannot be used in functions. But with hooks, we can use states.

Another reason is the handle side effect in react component. It means, now you can use newly introduced state such as `useEffect`.
But do you know for some scenarios, there are 3 places where react fails. While Reuse logic between components

- Has Huge components
- Confusing

## useEffect Hook And useState

We can say that useEffect Hook as componentDidMount, componentDidUpdate, and componentWillUnmount combined.
By default, useEffect runs both after the first render and after every update.
We can return a function(could be an arrow function) from our effect for adding and removing subscriptions.
Here we can set the states by `-const [count, setCount] = useState(0);`

`const [count, setCount] `: the current state and a function that updates it.

`useState(0):` Here we initialize the count as 0.

    ```
    function FriendStatusWithCounter(props) {
    const [count, setCount] = useState(0);
    useEffect(() => {
        document.title = `You clicked ${count} times`;
    });
    const [isOnline, setIsOnline] = useState(null);
    useEffect(() => {
        function handleStatusChange(status) {
        setIsOnline(status.isOnline);
        }
        ChatAPI.subscribeToFriendStatus(props.friend.id,
    handleStatusChange);
    return () => {
        ChatAPI.unsubscribeFromFriendStatus(props.friend.id,             handleStatusChange);
        };
    });
    if (isOnline === null) {
        return 'Loading...';
    }
    return isOnline ? 'Online' : 'Offline';
    }
    ```

## useCallback :

useCallback hooks returns a `memorized` callback.
useCallback will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders.

    ```
    const memoizedCallback = useCallback(
    () => {
        doSomething(a, b);
    },
    [a, b],
    );
    ```

Make sure you add that array as a second parameter to useCallback() with the state needed.

**useEffect vs useCallback:**
The problem of using useEffect is that any time the counter is updated, all the functions are re-created again.
Now if you use usecallback to click one of the counters, only the functions related to the state that changes are going to be re-instantiated.

## useMemo:

useMemo hooks returns `memorized `value.
useMemo will only recompute the memoized value when one of the dependencies has changed. This optimization helps to avoid expensive calculations on every render.

Remember that the function passed to useMemo runs during rendering. Don’t do anything there that you wouldn’t normally do while rendering.

You may rely on useMemo as a performance optimization, not as a semantic guarantee. In the future, React may choose to “forget” some previously memoized values and recalculate them on next render, e.g. to free memory for offscreen components. Write your code so that it still works without useMemo — and then add it to optimize performance.

    ```
    const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
    ```

**useMemo and useCallback:**
`useCallback(fn, deps) is equivalent to useMemo(() => fn, deps)`.

The useCallback hook is similar to useMemo, but it returns a memoized function, while useMemo has a function that returns a value.

If your dependencies array is empty, there is no possibility of memoization, and it will compute a new value on every render. You could use the useRef hook in that instance. The advantage useMemo offers over useRef is a re-memoizing if the dependencies change.

You won’t want to have useMemo fire off any side effects or any asynchronous calls. In those instances, you should use useEffect.

## useRef:

useRef returns a mutable ref object whose .current property is initialized to the passed argument (initialValue). The returned object will persist for the full lifetime of the component.

useRef is like a “box” that can hold a mutable value in its .current property.
useRef() is useful for more than the ref attribute. It’s handy for keeping any mutable value around similar to how you’d use instance fields in classes.
This works because useRef() creates a plain JavaScript object. The only difference between useRef() and creating a {current: ...} object yourself is that useRef will give you the same ref object on every render.

Keep in mind that useRef doesn’t notify you when its content changes. Mutating the .current property doesn’t cause a re-render. If you want to run some code when React attaches or detaches a ref to a DOM node, you may want to use a callback ref instead.

## Rules of Hooks:

- Only Call Hooks at the Top Level
- Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function. By following this rule, you ensure that Hooks are called in the same order each time a component renders. That’s what allows React to correctly preserve the state of Hooks between multiple useState and useEffect calls. (If you’re curious, we’ll explain this in depth below.)
- Only Call Hooks from React Functions
- Don’t call Hooks from regular JavaScript functions. Instead, you can:
- Call Hooks from React function components.
- Call Hooks from custom Hooks
