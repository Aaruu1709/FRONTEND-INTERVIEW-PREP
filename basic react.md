```
What is a Component in React?
A component is a small, independent piece of UI.
We divide a big webpage into small parts, and each part becomes a component.
Example:
Header Component
Navbar Component
Employee List Component
Footer Component
Instead of writing everything in one file, we create separate components.

Why are Components Reusable?
Because we create the code once and use it many times.
Example:

function Button() {
    return <button>Submit</button>;
}

Now we can use it anywhere:

<Button />
<Button />
<Button />
No need to write the button code again and again.
Why do we use reusable components?
Less code duplication.
Easy to maintain.
Easy to update.
Better code readability.
Faster development.
```
------------------------------------------------------------
```
What is Virtual DOM?

Virtual DOM is a lightweight copy of the Real DOM stored in memory.

React first updates the Virtual DOM, compares it with the old one, and then updates only the changed parts in the Real DOM.
When does Virtual DOM update?

Virtual DOM updates whenever:

setState() is called
useState() value changes
Props change
Parent component re-renders

Example:

const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
    Increment
</button>

When setCount() runs:

React creates a new Virtual DOM.
It compares it with the old Virtual DOM (Diffing).
It finds what changed.
It updates only that part in the Real DOM.
User clicks button
        ↓
setState() is called
        ↓
React creates new Virtual DOM
        ↓
React compares old and new Virtual DOM (Diffing)
        ↓
React finds the changed element
        ↓
Only that part is updated in Real DOM

This process is called Reconciliation
```
