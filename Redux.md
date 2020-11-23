<!--
 * @Author: your name
 * @Date: 2020-11-12 10:26:50
 * @LastEditTime: 2020-11-20 14:53:17
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \react-note\Redux.md
-->

# Redux

## Store

### state

- 与 action 无关的 UI 字段要如何存放

```javascript
const state = {
  device: {},
};
```

### reducer

```javascript
const add = (state, action) => {};
const del = (state, action) => {};
const mod = (state, action) => {};

const deviceReducer = (state = initialState, action) => {
  switch (acton.type) {
    case ADD:
      add(state, action);
      break;
    case DEL:
      del(state, action);
      break;
    case MOD:
      mod(state, action);
      break;
    default:
      return state;
  }
};

export default deviceReducer;
```

### action

```javascript
const ADD = 'ADD';
const DEL = 'DEL';
const MOD = 'MOD';

function add(payload) {
  return {
    type: ADD,
    payload,
  };
}
function del(payload) {
  return {
    type: DEL,
    payload,
  };
}
function mod(payload) {
  return {
    type: MOD,
    payload,
  };
}

export { add, del, mod };
```

### store

```javascript
import { combineReducers } from 'redux';
import deviceReducer from './deviceReducer';
const rootReducer = {
  deviceReducer,
};

const store = createStore(rootReducer);
store.subscribe(() => console.log(store.getState()));
export default store;
```

### dispath

```javascript
import store from './store';
import add from './addAction';
store.dispath(add(payload));
```
