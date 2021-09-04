# Redux - Functional Component
## index.js - setup Redux
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';

import './index.css';
import App from './App';
import store from './store/index';

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```
## App.js - display the component
```javascript
import Counter from './components/Counter';

function App() {
  return (
    <Counter />
  );
}

export default App;
```
## store/index.js - action/reducer
```javascript
import { createStore } from 'redux';

const initialState = { counter: 0, showCounter: true };

const counterReducer = (state = initialState, action) => {
  if (action.type === 'increment') {
    return {
      counter: state.counter + 1,
      showCounter: state.showCounter,
    };
  }

  if (action.type === 'increase') {
    return {
      counter: state.counter + action.amount,
      showCounter: state.showCounter,
    };
  }

  if (action.type === 'decrement') {
    return {
      counter: state.counter - 1,
      showCounter: state.showCounter,
    };
  }

  if (action.type === 'toggle') {
    return {
      showCounter: !state.showCounter,
      counter: state.counter,
    };
  }

  return state;
};

const store = createStore(counterReducer);

export default store;
```
## components/Counter.js
```javascript
import { useSelector, useDispatch } from 'react-redux';

import classes from './Counter.module.css';

const Counter = () => {
  const dispatch = useDispatch();
  const counter = useSelector((state) => state.counter);
  const show = useSelector((state) => state.showCounter);

  const incrementHandler = () => {
    dispatch({ type: 'increment' });
  };

  const increaseHandler = () => {
    dispatch({ type: 'increase', amount: 10 });
  };

  const decrementHandler = () => {
    dispatch({ type: 'decrement' });
  };

  const toggleCounterHandler = () => {
    dispatch({ type: 'toggle' });
  };

  return (
    <main className={classes.counter}>
      <h1>Redux Counter</h1>
      {show && <div className={classes.value}>{counter}</div>}
      <div>
        <button onClick={incrementHandler}>Increment</button>
        <button onClick={increaseHandler}>Increase by 10</button>
        <button onClick={decrementHandler}>Decrement</button>
      </div>
      <button onClick={toggleCounterHandler}>Toggle Counter</button>
    </main>
  );
};

export default Counter;
```
# Redux - Class-based Component
## index.js - setup Redux
```javascript
import ReactDOM from "react-dom";
import { createStore } from "redux";
import { Provider } from "react-redux";
import reducer from "./reducer";

import App from "./App";

const store = createStore(reducer);

const rootElement = document.getElementById("root");
ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  rootElement
);
```
## App.js - make the connection - connect(mapStateToProps, mapDispatchToProps)(App)
```javascript
import React from "react";
import { connect } from "react-redux"; 
import * as counterActions from "./action";

class App extends React.Component {
  render() {
    const { numberForApp, incHandler, decHandler } = this.props; 

    return (
      <div className="App">
        <h3>{numberForApp}</h3> 
        <button onClick={incHandler}>+</button> 
        <button onClick={decHandler}>-</button> 
      </div>
    );
  }
}

const mapStateToProps = (state) => ({ 
  numberForApp: state.counterReducer 
});

const mapDispatchToProps = (dispatch) => ({
  incHandler: () => dispatch({ type: "INCREMENT" }), 
  decHandler: () => dispatch(counterActions.decAction()) 
});

const ConnectedApp = connect( 
  mapStateToProps,
  mapDispatchToProps, 
)(App)

export default ConnectedApp
```
## action.js - define action functions will be used in switch statements
```javascript
const incAction = () => {
  return {
    type: "INCREMENT"
  }
}
const decAction = () => {
  return {
    type: "DECREMENT"
  }
}
export {
  incAction,
  decAction 
}
```
## reducer.js - reply on the input and local state to get a predictable output
```javascript
import { combineReducers } from "redux";

const INIT_STATE = 1;   

const counterReducer = (state = INIT_STATE, action) => { 
  switch (action.type) { 
    case "INCREMENT":  
      return state + 1; 
    case "DECREMENT":  
      return state - 1; 
    default:
      return state; 
  }
};

const rootReducer = combineReducers({   
  counterReducer
});
export default rootReducer;
```
