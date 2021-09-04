# Functional React Boilerplate
## index.js 
ReactDOM.render(what to show, where to show it);
``` javascript
import React from "react";
import ReactDOM from "react-dom";
import App from "./components/App";

ReactDOM.render(<App />, document.getElementById("root"));
```
## App.js
``` javascript
import React from "react"; 

function App() {
  return (
      <div>
      <h2>Let's get started!</h2>
    </div>
  )
}

export default App;
```
## index.html
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>React App</title>
    <link rel="stylesheet" href="styles.css" />   //css file
  </head>
  <body>
    <div id="root"></div>
    <script src="../src/index.js"></script> 
  </body>
</html>
```
# Class-based Component
```javascript
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {};
  }

  render() {
    return (
      <div className="App">
        <h1>Hello World</h1>
      </div>
    );
  }
}

export default App;
```
