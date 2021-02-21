# react-fundamentals

## Immutability
1. Immutability makes complex features much easier to implement.
    1. Avoiding direct data mutation lets us keep previous versions of the game’s history intact, and reuse them later.
2. Detecting Changes: Detecting changes in mutable objects is difficult because they are modified directly. This detection requires the mutable object to be compared to previous copies of itself and the entire object tree to be traversed.
    1. Detecting changes in immutable objects is considerably easier. If the immutable object that is being referenced is different than the previous one, then the object has changed.
3. Determining When to Re-Render in React:
    1. The main benefit of immutability is that it helps you build **pure components** in React. Immutable data can easily determine if changes have been made, which helps to determine when a component requires re-rendering.

# Function Components