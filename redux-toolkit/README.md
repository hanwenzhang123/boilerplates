# @reduxjs/toolkit
npm install @reduxjs/toolkit\
npm install react-redux
## index.js
```javascript
import ReactDOM from "react-dom";
import { Provider } from "react-redux";

import store from "./store/index";
import "./index.css";
import App from "./App";

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById("root")
);
```
## store/index.js
```javascript
import { configureStore } from "@reduxjs/toolkit";

import uiSlice from "./ui-slice";

const store = configureStore({ 
  reducer: { ui: uiSlice.reducer },
});

export default store;
```
## store/ui-slice.js
```javascript
import { createSlice } from "@reduxjs/toolkit";

const uiSlice = createSlice({ 
  name: "ui",
  initialState: { cartIsVisible: false },
  reducer: {
    toggle(state) {
      state.cartIsVisible = !state.cartIsVisible;
    },
  },
});

export const uiAction = uiSlice.actions;

export default uiSlice;
```
## store/index.js - all in one file
```javascript
import { createSlice, configureStore } from '@reduxjs/toolkit';

const initialCounterState = { counter: 0, showCounter: true };

const counterSlice = createSlice({
  name: 'counter',
  initialState: initialCounterState,
  reducers: {
    increment(state) {
      state.counter++;
    },
    decrement(state) {
      state.counter--;
    },
    increase(state, action) {
      state.counter = state.counter + action.payload;
    },
    toggleCounter(state) {
      state.showCounter = !state.showCounter;
    },
  },
});

const initialAuthState = { 
  isAuthenticated: false,
};

const authSlice = createSlice({
  name: 'authentication',
  initialState: initialAuthState,
  reducers: {
    login(state) {
      state.isAuthenticated = true;
    },
    logout(state) {
      state.isAuthenticated = false;
    },
  },
});

const store = configureStore({
  reducer: { counter: counterSlice.reducer, auth: authSlice.reducer },
});

export const counterActions = counterSlice.actions;
export const authActions = authSlice.actions;

export default store;
```
