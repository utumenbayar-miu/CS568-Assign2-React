# CS568 - Assignment 2 - React elements and components
1. Create a React app with the create-react-app.
2. Create an element with the React.createElement.
3. Create a custom functional component with props. Display the prop using the embedded expression in JSX.
4. Create a custom class-based component. Render the functional component in it.
```
App (root component)
├─ Class component
│  └─ Functional component
```
6. Return multiple elements using either Fragment, div, or an array.
7. Implement below
```
App (root component)
├─ TodoList
│  └─ TodoItem
│     ├─ TodoDeleteButton
│     └─ TodoEditButton
└─ TodoFooter
   ├─ TodoClearButton
   └─ TodoStatistics
```

Refer code below

*Class-based component*

```
import React from "react";

export default class Welcome extends React.Component {
  render() {
    return <p>Welcome!</p>;
  }
}
```

*App.js*

```
import React from "react";
// import Welcome from "./components/Welcome";

function Welcome({ data }) {
  const { name } = data;
  return <p>Weclome {name || "Stranger"}!</p>;
}

function App() {
  function getName() {
    return "name from function";
  }
  const name = "My Name";
  const name2 = "Name 2";
  const number = 5;
  const elementToRender = number > 2 ? name : name2;

  const element = (
    <>
      <div id="myId" className="myClass">
        <p>This is {getName()}.</p>
      </div>
      <div id="myId" className="myClass">
        <p>This is {getName()}.</p>
      </div>
    </>
  );

  const data = {
    attr1: "asd",
    attr2: "asd",
    name: "Unubold",
    attr3: "asd",
  };

  return <Welcome data={data} id="1"></Welcome>;
}

export default App;
```
