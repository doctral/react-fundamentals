# react-fundamentals

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