Final Scope (Industry-Level but Practical):

| Page                   | Purpose                   | Skills Covered                               |
| ---------------------- | ------------------------- | -------------------------------------------- |
| 🔐 Login               | Authentication UI         | Forms, validation, layout                    |
| 📊 Dashboard           | Analytics & quick actions | Cards, responsive grid, navigation           |
| 👨 Employee Management | Main CRUD screen          | Table, search, filter, sort, pagination      |
| ➕ Add/Edit Employee    | Employee form             | Controlled inputs, validation, reusable form |
| 👤 Employee Details    | View employee             | Cards, responsive layout                     |
| 🏢 Department          | Department CRUD           | Table reuse, forms, modals                   |
| 📅 Attendance          | Attendance list           | Tables, filters, status badges               |
| 🌴 Leave Management    | Leave requests            | Tables, actions, badges                      |
| ⚙️ Settings/Profile    | Small but realistic       | Forms, toggles                               |
| ❌ 404 Page             | Error handling            | Routing                                      |

---------------------------------------------------------------------------------

🚀 Sprint 1 - Project Planning

Before opening VS Code, every company has a planning phase.

Let's pretend this is our first team meeting.

Business Requirement

Build an HR Employee Management Dashboard.

The HR manager should be able to:

View dashboard statistics
Manage employees
Manage departments
Track attendance
Manage leave requests
View employee profiles
Use the application on desktop, tablet, and mobile
Tech Stack

Since this is a frontend-focused project, we'll keep it modern but not overly complex.

React (Vite)
React Router
CSS (no Bootstrap/Tailwind initially)
Fetch API
Mock JSON data first, then connect to APIs
Git for version control (optional but recommended)
Development Roadmap

We'll work in this order:

Phase 1 – Foundation
Create React project
Clean up default files
Organize folder structure
Install React Router
Create application layout
Add Navbar and Sidebar
Make the layout responsive
Phase 2 – Reusable UI Components

We'll build components that can be reused everywhere:

Button
Input
SearchBox
Card
Table
Modal
Loader
Pagination
Badge
Empty State
Error State
Phase 3 – Pages
Dashboard
Employee Management
Add/Edit Employee
Employee Details
Department
Attendance
Leave Management
Profile
Settings
404
Phase 4 – Data & API
Fetch employee data
Add employee
Edit employee
Delete employee
Search/filter/sort
Loading and error handling

Phase 5 – Polish
Responsive improvements
Better spacing and typography
Smooth hover effects
Final UI review

-------------------------------------------------------------------
What is BrowserRouter?

Your answer:

BrowserRouter enables client-side routing in a React application. It listens to URL changes and renders the appropriate component without reloading the page.

Why AppRoutes?
-------------------------------------------------------------------------------------------

To separate routing logic from App.jsx and keep the project modular and maintainable.

Why MainLayout?
-------------------------------------------------------------------------------------------

To avoid repeating common UI elements like Navbar and Sidebar across multiple pages.

What is Outlet?
-------------------------------------------------------------------------------------------

Outlet is a placeholder where React Router renders the matched child route.

What is Nested Routing?
-------------------------------------------------------------------------------------------

Nested routing allows child pages to share a common layout while displaying different content inside the Outlet.

Why menuItems array?
-------------------------------------------------------------------------------------------

Instead of hardcoding every menu item, we store them in an array and use .map() to render them dynamically. This makes the sidebar easier to maintain and extend.

-------------------------------------------------------------------------------------------
