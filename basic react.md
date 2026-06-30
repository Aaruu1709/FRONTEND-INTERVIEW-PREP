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
