### Redux Toolkit

##### Why Toolkit?
 Because of Redux requires too much `boilerplate code`
 
      - Action types
      - Action creators 
      - Switch statements in reducer
      - Too much modular file structure  

 Too much third-party need to be install
 
      - redux-thunk
      - redux-devtools


#### Fundamental of Redux-Toolkit


```javascript


  const { createSlice, configureStore } = require("@reduxjs/toolkit");
  
  const initialState = {
   count: 0,
  };

  const counterSlice = createSlice({
      name: "counter",
      initialState,

      reducers: {
      increment: (state, action) => {
         state.count += 1;
      },
     decrement: () => {},
     countByAmount: (state, action) => {
      state.count += action.payload;
    },

    extraReducers: {
       ["anotherAction/anotherSliceName"] : (state, action) => {
         console.log(state)
       }
    } 
   // Or 
    extraReducers: (builder) => {  
      builder.addCase(fetchUserById.fulfilled, (state, action) => {  
        console.log(action.payload)
      })  
  },

  },

});

  

const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
  },
});

  
store.subscribe(() => {
  console.log(store.getState());
});


store.dispatch(counterSlice.actions.countByAmount(20));
store.dispatch(counterSlice.actions.countByAmount(30));
store.dispatch(counterSlice.actions.countByAmount(40));

```




