
[GitHub ](https://github.com/devesabbir/advanced-redux)
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




#### Project Folder structure

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
|-- app
|   |-- store.js
|-- features
|   |-- features1
|   |   |-- thunk
|   |   |   |-- featuresApi.js
|   |   |-- featuresSlice.js    
|   |-- features2
|       |-- thunk
|       |   |-- featuresApi.js
|       |-- featuresSlice.js 
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

#redux #redux-toolkit 


#### RTK-Query

```js
import { createApi, fetchBaseQuery } from "@reduxjs/toolkit/query/react";

  

export const apiSlice = createApi({
  reducerPath: "api",
  baseQuery: fetchBaseQuery({
    baseUrl: "http://localhost:9000",
  }),
  tagTypes: ["Videos", "Video", "RelatedVideos"],
  endpoints: (builder) => ({
    // get all videos
    getVideos: builder.query({
      query: () => "/videos",
      providesTags: () => ["Videos"],
    }),

    // get single video
    getSingleVideo: builder.query({
      query: (id) => "/videos/" + id,
      providesTags: (result, error, arg) => {
        return [{ type: "Video", id: arg }];
      },
    }),

  
    // get related videos
    getRelatedVideos: builder.query({
      query: ({ id, title }) => {
        // ?title_like=code
        const tags = title?.split(" ");
        const likes = tags?.map((t) => `title_like=${t}`);
        const queryString = `/videos?${likes?.join("&")}&id_ne=${id}&_limit=4`;
        return queryString;
      },
      providesTags: (result, error, arg) => [
        { type: "RelatedVideos", id: arg.id },
      ],
    }),


    // add video
    addVideo: builder.mutation({
      query: (data) => ({
        url: "/videos",
        method: "POST",
        body: data,
      }),
      invalidatesTags: () => ["Videos"],
    }),

  
    // delete video
    deleteVideo: builder.mutation({
      query: (id) => ({
        url: "/videos/" + id,
        method: "DELETE",
      }),
      invalidatesTags: (result, error, arg) => ["Videos"],
      
    }),


    // edit a video
    editVideo: builder.mutation({
      query: ({ id, data }) => ({
        url: "/videos/" + id,
        method: "PUT",
        
      }),
  
      invalidatesTags: (result, error, arg) => [
        "Videos",
        { type: "Video", id: arg },
        { type: "RelatedVideos", id: arg },
      ],
    }),
  }),
});

  
export const {
  useGetVideosQuery,
  useGetSingleVideoQuery,
  useGetRelatedVideosQuery,
  useAddVideoMutation,
  useDeleteVideoMutation,
  useEditVideoMutation,
} = apiSlice;
```

#### Store Setup

```js
import { configureStore } from "@reduxjs/toolkit";
import { apiSlice } from "../features/api/apiSlice";


export const store = configureStore({
  reducer: {
    [apiSlice.reducerPath]: apiSlice.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware().concat([apiSlice.middleware]),
  devTools: true,
});
```