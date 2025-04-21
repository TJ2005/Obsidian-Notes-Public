---
Title: React Effects hook
Status: 
marker:
  - "[[Programming]]"
  - "[[Programming in JS]]"
  - "[[React]]"
tags: 
Date: 2025.01.13
Time: 11:39
---

# Understanding `useEffect` Hook

### What is `useEffect`?
- `useEffect` is a hook in React that lets us perform side effects in our function components.
- Side effects are operations that affect things outside the scope of the function, like fetching data or manually changing the DOM.

### How does it work in the Typing Effect example?

1. **State Initialization**:
   - `text` starts as an empty string and `index` starts at 0.

2. **Dependency Array**:
   - The array `[text, index, onComplete]` means that the effect runs whenever `text`, `index`, or `onComplete` changes.

3. **Typing Effect Logic**:
   - If `index` is less than the length of `fullText`:
     - `setTimeout` waits for 80 milliseconds and then:
       - Updates `text` by adding the next character from `fullText`.
       - Increases `index` by 1.
     - The cleanup function `clearTimeout` makes sure we don't leave any old timeouts running.
   - When `index` matches the length of `fullText`:
     - Another `setTimeout` waits for 1 second and then calls `onComplete`.
     - Again, `clearTimeout` ensures no old timeouts are left running.

### Why use `useEffect`?
- It helps us manage side effects cleanly and ensures our effects run at the right times.
- It's especially useful for:
  - Integrating third-party libraries.
  - Attaching/detaching event listeners.
  - Handling animations.
  - Managing focus.

### Key Takeaway
- By using `useEffect` with a dependency array, we can monitor specific values and perform actions when they change.

---

# References


###### Information
- date: 2025.01.13
- time: 11:39