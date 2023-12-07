#### Packages 
1. Redux
2. react-redux 
3. thunk

##### Folder Structure 

```javascript
// Folder Structure for redux react-redux
src
|-- components
|   |-- Component1
|   |   |-- index.js
|   |   |-- styles.css
|   |-- Component2
|       |-- index.js
|       |-- styles.css
|-- containers
|   |-- Container1
|   |   |-- index.js
|   |   |-- styles.css
|   |-- Container2
|       |-- index.js
|       |-- styles.css
|-- redux
|   |-- feature1
|   |     |-- actions
|   |     |    |-- index.js
|   |     |    |-- types.js
|   |     |-- reducers
|   |         |-- index.js
|   |         |-- reducer.js         
|   |-- feature2
|   |   |-- actions
|   |   |   |-- index.js
|   |   |   |-- types.js
|   |   |-- reducers
|   |       |-- index.js
|   |       |-- reducer.js
|   |-- rootReducer
|   |   |-- rootReducer.js
|   |-- store
|       |-- configureStore.js
|-- App.js
|-- index.js
|-- index.css
|-- serviceWorker.js
|-- assets
|-- utils
|-- constants
|-- routes
|-- tests

```

#redux #react-redux #folder-structure-for-redux


#### Actions 


```JAVASCRIPT
// action type
export const INCREMENT = 'counter/increment';
export const DECREMENT = 'counter/decrement';


// action creators
export const increment = () => {
    return {
        type: INCREMENT
    }

export const decrement = () => {
    return {
        type: DECREMENT
    }
}
```

#actions #redux 

#### Reducer


```Javascript
import { DECREMENT, INCREMENT } from "../actions/counterAction"

  
// Initial State for counter
const initialState = {
    count: 0,
}

  
const counterReducer = (state = initialState, action) => {
    switch (action.type) {
        case INCREMENT:
            return {
                ...state,
                count: state.count + 1
            }
        case DECREMENT:
            return {
                ...state,
                count: state.count - 1
            }  

        default:
            return state
    }

}

  
export default counterReducer;

```

#reducer #redux #react-redux 


#### Combine Reducers

```JAvascript 
import { combineReducers } from 'redux';
import counterReducer from '../counter/reducers/counterReducer';
  

const rootReducer = combineReducers({
    counterReducer: counterReducer
})


export default rootReducer;
```

#combinereducers #rootReducer #redux 


#### Store

```Javascript
import { createStore, applyMiddleware } from 'redux';=
import { composeWithDevTools } from 'redux-devtools-extension';
import thunk from 'redux-thunk';

import rootReducer from "../rootReducer/rootReducer";

export const store = createStore(
rootReducer,
composeWithDevTools(applyMiddleware(thunk)
)

```

#Redux #Redux-Store


#### Provider

```JSX
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'
import { Provider } from 'react-redux'
import { store } from './redux/store/store.js'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
      <Provider store={store} >
          <App />
      </Provider>
  </React.StrictMode>,
)

```

#redux #provider-with-store #React-redux


#### Connect API (HOC)

```jsx

// Redux connect API
import { connect } from 'react-redux'
import { decrement, increment } from '../../src/redux/counter/actions/counterAction'

const Counter = ({count, increment, decrement}) => {
  return (
    <div>
        <h2>{count}</h2>
        <button onClick={() => increment()} > ++ </button>
        <button onClick={() => decrement()} > -- </button>
    </div>
  )
}

/**
 *
 * @param {redux state} state
 * @param {component Props} ownProps
 * @returns
 */

const mapStateToProps = (state, ownProps = {}) => {
    return {
       count: state.counterReducer.count
    }
}

/**
 *
 * @param {redux dispatch func} dispatch
 * @param {component Props} ownProps
 * @returns
 */

const mapDispatchToProps = (dispatch, ownProps = {}) => {
    return {
        increment: () => dispatch(increment()),
        decrement: () => dispatch(decrement())
    }
}

export default connect(mapStateToProps, mapDispatchToProps)(Counter)

```

#connect #redux #connectAPI 


#### Redux Middleware

```Javascript
import { createStore, applyMiddleware } from 'redux';
import { composeWithDevTools } from 'redux-devtools-extension';
import thunk from 'redux-thunk';
import rootReducer from "../rootReducer/rootReducer";

// Custom Middleware 
const  myLogger = (store) => (next) => (action) =>{
   return next(action)
}

export const store = createStore(rootReducer, composeWithDevTools(applyMiddleware(myLogger,thunk)))

```

#multiple-midleware #Custom_middleware #redux 
