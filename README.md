# CS568 - Assignment 2 - React elements and components
## Thinking in React
1. Read https://react.dev/learn/thinking-in-react. Write what you learned in your own words in **200** words in the README.md file.
2. Implement the "Table" example on the page. Fill it with the **Student** data instead of **Fruits** and **Vegetables**.

FILTER

CS568
| Code      | Name |
| ----------- | ----------- |
| 985431      | John       |
| 985231   | Bat        |

CS516
| Code      | Name |
| ----------- | ----------- |
| 185431      | Sara       |
| 185431   | Cat        |

## Microtasks
1. Create an element with the React.createElement.
2. Create a functional component. Declare a variable in the function and display it using the embedded expression on the page.
3. Create a custom class-based component. Render the functional component in it.
```
App (root component)
├─ Class component
│  └─ Functional component
```
4. Return multiple elements using either Fragment, div, or an array. Implement the Table, Column example in the slide.
5. Implement the Advanced Hello example, both class and functional way.
6. Implement below. Just log out the component names in the "p" tag for now. We will implement the rest starting tomorrow.
```
App (root component)
├─ TodoList (component)
│  └─ TodoItem (component)
│     ├─ TodoDeleteButton (component)
│     └─ TodoEditButton (component)
└─ TodoFooter (component)
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
