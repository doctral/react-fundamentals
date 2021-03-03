# react-fundamentals

## Introducing JSX 
1. JSX is a syntax extension to JavaScript. JSX produces React elements.
2. JSX prevents injection attacks: By default, React DOM escapes any values embedded in JSX before rendering them. This helps prevent XSS attacks. 
3. Babel compiles JSX down to React.createElement() calls. 

## Rendering Elements
1. React elements are **immutable**. Once you create an element, you can’t change its children or attributes.
2. The only way to update the UI is to create a new element, and pass it to ReactDOM.render().
3. In practice, most React apps only call ReactDOM.render() once. 
4. React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.

## Components and Props
1. Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.
2. Function Component vs Class Components
    1. Function Component: a JavaScript function that accepts a single "props" object argument with data and returns a React element.  
    2. Class Component: a class that extends React.Component using ES6
3. Always start components names with a capital letter
    1. React treats components starting with lowercase letters as DOM tags. For example, <div> represents an HTML div tag, but <Welcome> represents a component and requires Welcome to be in scope.
4. **All React components must act like pure functions with respect to their props**.
    1. **Props are Read-Only**.

## State and Lifecycle
1. The **componentDidMount()** method runs after the component output has been rendered to the DOM.
2. If the component is ever removed from the DOM, React calls the **componentWillUnmount()** lifecycle method.
3. Using State correctly:
    1. Do Not Modify State Directly, instead, use **setState()**. The only place you can assign **this.state** is the constructor

## Handling Events
1. React events are named using camelCase, rather than lowercase.
2. With JSX you pass a function as the event handler, rather than a string.
3. You cannot return false to prevent default behavior in React. You must call preventDefault explicitly.

## Immutability
1. Immutability makes complex features much easier to implement.
    1. Avoiding direct data mutation lets us keep previous versions of the game’s history intact, and reuse them later.
2. Detecting Changes: Detecting changes in mutable objects is difficult because they are modified directly. This detection requires the mutable object to be compared to previous copies of itself and the entire object tree to be traversed.
    1. Detecting changes in immutable objects is considerably easier. If the immutable object that is being referenced is different than the previous one, then the object has changed.
3. Determining When to Re-Render in React:
    1. The main benefit of immutability is that it helps you build **pure components** in React. Immutable data can easily determine if changes have been made, which helps to determine when a component requires re-rendering.

## Function Components
1. In React, **function components** are a simpler way to write components that only contain a render method and don’t have their own state. Instead of defining a class which extends React.Component, we can write a function that takes props as input and returns what should be rendered. Function components are less tedious to write than classes, and many components can be expressed this way.

## key
1. **key** is a special and reserved property in React (along with ref, a more advanced feature). When an element is created, React extracts the key property and stores the key directly on the returned element. Even though key may look like it belongs in props, key cannot be referenced using this.props.key. React automatically uses key to decide which components to update. A component cannot inquire about its key.
2. **It’s strongly recommended that you assign proper keys whenever you build dynamic lists.**
3. If no key is specified, React will present a warning and use the array index as a key by default. Using the array index as a key is problematic when trying to re-order a list’s items or inserting/removing list items. Explicitly passing key={i} silences the warning but has the same problems as array indices and is not recommended in most cases.
4. Keys used within arrays should be unique among their siblings. However they don’t need to be globally unique.