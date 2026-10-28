# Practical: Creating a Single Page Website Using React

**Aim:** To create a Single Page Website using React concepts such as Hooks, State, Props, and Router.

---

## Step 1–6: Terminal Commands (Project Setup)

Check Node.js and npm versions:

```bash
node --version
```

```bash
npm --version
```

Create a new Vite React project (Select Framework: **React**, Variant: **JavaScript**):

```bash
npm create vite@latest react-single-page
```

Navigate into the project directory, install packages, and install React Router:

```bash
cd react-single-page
```

```bash
npm install
```

```bash
npm install react-router-dom
```

Open the project in VS Code and run the development server:

```bash
code .
```

```bash
npm run dev
```

---

## Complete Website Code (`src/App.jsx`)

Replace the code inside `src/App.jsx` with the following:

```jsx
import {
  BrowserRouter,
  Routes,
  Route,
  Link
} from "react-router-dom";
import { useState } from "react";

function Home() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>Home Page</h1>
      <p>
        Welcome to our React Single Page Website.
      </p>
      <h2>Counter: {count}</h2>
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

function About() {
  return (
    <div>
      <h1>About Page</h1>
      <p>
        This website is created using React.
      </p>
    </div>
  );
}

function Contact() {
  return (
    <div>
      <h1>Contact Page</h1>
      <p>
        Email: student@example.com
      </p>
    </div>
  );
}

function Welcome(props) {
  return (
    <h2>
      Welcome, {props.name}!
    </h2>
  );
}

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link>
        {" | "}
        <Link to="/about">About</Link>
        {" | "}
        <Link to="/contact">Contact</Link>
      </nav>

      <Welcome name="Student"/>

      <Routes>
        <Route element="{<Home" path="/"/>}
        />
        <Route element="{<About" path="/about"/>}
        />
        <Route element="{<Contact" path="/contact"/>}
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

---

## Optional Step-by-Step Examples

### 1. State Example Only (Step 7 - `src/App.jsx`)

```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>Counter</h1>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default App;
```

### 2. Props Example Only (Step 12 - `src/App.jsx`)

```jsx
function Welcome(props) {
  return (
    <h2>
      Welcome, {props.name}!
    </h2>
  );
}

function App() {
  return (
    <div>
      <h1>My React Website</h1>
      <Welcome name="Student"/>
    </div>
  );
}

export default App;
```
