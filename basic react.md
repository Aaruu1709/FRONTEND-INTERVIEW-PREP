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

```
Difference between npm start and npm run dev
Both commands start a development server, but the actual behavior depends on what is written in package.json.

| `npm start`                                                        | `npm run dev`                                             |
| ------------------------------------------------------------------ | --------------------------------------------------------- |
| Used in traditional React projects (Create React App)              | Used in modern tools like Vite, Next.js, Nuxt             |
| Runs the `start` script from `package.json`                        | Runs the `dev` script from `package.json`                 |
| Usually starts the development server on port 3000                 | Usually starts the development server on port 5173 (Vite) |
| `npm start` is a special command, so you don't need to write `run` | For other scripts, you must use `npm run`                 |
```


```
"Which libraries does React use internally?"

1. react
Core React library.
Used to create components, hooks, and UI logic.
2. react-dom
Connects React with the browser DOM.
Renders React components on the web page.
3. react-router-dom
Used for navigation and routing between pages.

Example:

/home
/about
/contact

4. axios (or Fetch API)
Used to call backend APIs.
"The main React libraries are react for building components, react-dom for rendering them in the browser, react-router-dom for page navigation, and axios or Fetch API for calling backend services."
```

```
Why were Functional Components called "Stateless"?

Before React Hooks (React 16.8):
Functional components could not store state
They only received props and displayed UI.
That's why they were called stateless components.

After Hooks (useState, useEffect, etc.) were introduced, functional components can manage state.
Now, functional components are stateful too.

functional components were called stateless components because they could not maintain their own state. They only received data through props and rendered the UI. If we needed state or lifecycle methods, we had to use class components

After React Hooks like useState and useEffect were introduced, functional components also became stateful, so today they are no longer considered truly stateless.


Stateless means the component does not store or manage its own data.
Stateful means the component stores and manages its own data using state.

```

```
"Props are used to pass data from a parent component to a child component, and they are read-only. State is used to store and manage data within a component, and it can be updated using hooks like useState. Props are controlled by the parent, whereas state is controlled by the component itself.
```



