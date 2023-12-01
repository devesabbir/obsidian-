# State Management with raw javaScript 

```HTML
  <div id="displayCount"> 0 </div>
  <div> 
     <button id="incrementBtn" > Increment </button> 
     <button id="decrementBtn" > Decrement </button>
  </div>
  
 ```

```JAVASCRIPT
const inrementBtn = document.getElementById('inrementBtn');
const decrementtBtn = document.getElementById('idecrementBtn');
const displayCount = document.getElementById('displayCount');

let count = 0;

// increment event handlers
inrementBtn.addEventListener('click', function(){
    count++; 
    displayCount.innerText = count;
})

// decrement event handlers
decrementBtn.addEventListener('click', function(){
    if (count > 0)  count--; displayCount.innerText = count;
})


```

#StateManagementWithRawJavaScript



```JAVASCRIPT 
const inrementBtn = document.getElementById('inrementBtn');
const decrementBtn = document.getElementById('decrementBtn');
const displayCount = document.getElementById('displayCount');


 /** 
   The Vanila Redux Flow
 */
 
 // initial state
 const initialState = {counter: 0}

 // Reducer Function
 const counterReducer = (state = initialState, action) => {
    switch (action.type) {
      case 'INCREMENT':
      return {
         ...state,
         counter: state.counter + 1
      }
      case 'DECREMENT':
        return {
         ...state,
          counter: state.counter - 1
         }
      default:
      return state;
    }
 }

 // Combine reducers into a root reducer
 const rootReducer = Redux.combineReducers({counterReducer});

 // create store
 const store = Redux.createStore(rootReducer)

 // render function
 const render = () => {
   const counter = store.getState().counterReducer.counter
   displayCount.innerText = counter;
 }

 // subscribe render funtion to store
 store.subscribe(render)
 
 // initial render in dom
 render()

// dispatch increment action
inrementBtn.addEventListener('click', () => {
   store.dispatch({type:'INCREMENT'})
})

// dispatch decrement action
decrementBtn.addEventListener('click', () => {
   store.dispatch({type:'DECREMENT'})
})


```



```JAVASCRIPT 
// select dom element
const addNewMatchBtn = document.querySelector('#addNewMatch')
const matchContainer = document.querySelector('#matchContainer')
const resetBtn = document.querySelector('#resetBtn')

// Initial State Object
const initialState = {
    matches:[{id:1, score:0}]
}
// matche reducers
function matchReducer(state = initialState, action) {
    switch (action.type) {
     case 'ADDMATCH':
     return {
        ...state,
        matches: [...state.matches, action.payload]
     }
     case 'DELETE':
      return {
         ...state,
         matches: state.matches.filter(item => item.id !== action.payload)
      }
     case 'INCREMENT':
       return {
         ...state,
         matches: state.matches.map(item => {
            if (item.id === action.payload.id) {
                return {
                   ...item,
                    score: item.score + action.payload.value
                }
            }
            return {...item}
         })
       }

     case 'DECREMENT':
        return {
            ...state,
            matches: state.matches.map(item => {
                if (item.id === action.payload.id) {
                    return {
                        ...item,
                        score: item.score > 0 && !((item.score - action.payload.value)                           < 0) ? item.score - action.payload.value : item.score
                    }
                }
               return {...item}
            })
        }

     case 'RESET':
        return {
            ...state,
            matches:state.matches.map( item => {
                return {
                    ...item,
                    score: 0
                }
            })                                        
        }

     default:
         return state;
   }  

}

  

const rootReducer = Redux.combineReducers({matchReducer})

// create store
const store = Redux.createStore(rootReducer)
const render = () => {
   const matches = store.getState().matchReducer.matches
   let match = '';
  
   matches.forEach( m => {
      match += `<div class="match">
      <div class="wrapper">
          <button onclick="handleDeleteMatch(${m?.id})" class="lws-delete">
              <img src="./image/delete.svg" alt="" />
          </button>
          <h3 class="lws-matchName">Match ${m?.id}</h3>
      </div>
      <div class="inc-dec">
          <form onsubmit="incrementScore(event, ${m?.id})" id="incrementForm" class="incrementForm">
              <h4>Increment</h4>
              <input
                  type="number"
                  name="increment"
                  class="lws-increment"
              />
          </form>
          <form onsubmit="decrementScore(event, ${m?.id})" id="decrementForm" class="decrementForm">
              <h4>Decrement</h4>
              <input
                 type="number"
                  name="decrement"
                  class="lws-decrement"
              />
         </form>
      </div>
      <div class="numbers">
         <h2 class="lws-singleResult">${m?.score}</h2>
      </div>
      </div>`
   });

   matchContainer.innerHTML = match;

}

  
// initial render dom
render()
// render when state changes
store.subscribe(render)
  
// Generate a new ID based on the last index number
function generateNewId(matches) {
      return matches.length === 0 ? 1 : matches[matches.length - 1].id + 1;
  }

// add new matche
addNewMatchBtn.addEventListener('click', () => {
   let matches = store.getState().matchReducer.matches
   const newMatchObj = {id:generateNewId(matches), score:parseInt(0)}
   store.dispatch({type:'ADDMATCH', payload:newMatchObj})
})

   
const handleDeleteMatch = (id) => {
   store.dispatch({type:'DELETE', payload:id})
}

  
const incrementScore = (event, id) => {
   event.preventDefault()
   const target = event.target
   const value = target.querySelector('.lws-increment').value
   store.dispatch({type:'INCREMENT', payload:{id:id, value:parseInt(value)}})

}

  
const decrementScore = (event, id) => {
   event.preventDefault()
   const target = event.target
   const value = target.querySelector('.lws-decrement').value
   store.dispatch({type:'DECREMENT', payload:{id:id, value:parseInt(value)}})

}

resetBtn.addEventListener('click', () => {
    store.dispatch({type:'RESET'})
})

```

#redux #vanilaRedux

