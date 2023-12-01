
```JAVASCRIPT
const incrementEl = document.getElementById('increment');
const decrementEl = document.getElementById('decrement');
const viewEl = document.getElementById('view');

  
const INCREMENT = "counter/increment";
const DECREMENT = "counter/decrement";


const initialState = {
    counter: 0,
}


const actions = []

const counterReducer = (state = initialState, action) => {
    if (action.type === INCREMENT) {
        return {
            ...state,
            counter: state.counter + action.value
        }

    } else if (action.type === DECREMENT ) {
        return {
            ...state,
            counter: state.counter - action.value
        }
    } else {
        return state
    }

}

  

let store = {
    counter: 0
}


incrementEl.onclick = () => {
    actions.push({
        type:INCREMENT,
        value:1
    })
    const result = actions.reduce(counterReducer, initialState)
    store = {
        ...store,
        counter: result.counter
    }
    
    render()
}



decrementEl.onclick = () => {
    actions.push({
        type:DECREMENT,
        value:1
    })
    const result = actions.reduce(counterReducer, initialState)
    store = {
        ...store,
        counter: result.counter
    }
    
    render()

}

  
  

const render = () => {
   const count = store.counter;
   viewEl.innerText = count
}

render()

```


#redux #howReduxWorks

