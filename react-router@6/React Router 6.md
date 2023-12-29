
#### installation 

```shell
npm i react-router-dom
```

#### Routing (BrowserRouter)

**main.jsx** 
```JSX
import { BrowserRouter } from "react-router-dom"
import App from "./App"

function Main () {
   return (
     <BrowserRouter>
         <App />
     </BrowserRouter>
   )
}

export default Main;
```

**App.jsx**
```jsx
import { route, routes } from "react-router-dom" 
import Home from "./Home"
import Books from "./Books"
import NotFound from "./NotFound"

function App () {
  return (
    <Routes> 
       <Route path="/" element={<Home />} />
       <Route path="/books" element={<Books />} />
       // Dynamic Routing
       <Route path="/books/:id" element={<Book />} />
       <Route path="*" element={<NotFound />} />
    </Routes>
  )
}

export default App;
```

*Or*

```jsx
import { route, routes } from "react-router-dom" 
import Home from "./Home"
import BookLayout from "./BookLayout"
import Books from "./Books"
import NotFound from "./NotFound"

function App () {
  return (
    <Routes> 
       <Route path="/" element={<Home />} />
       <Route path="/books" element={<BookLayout />} > 
           // Inside the BookLayout use <Outlet />*
           <Route index element={<Books />} />
          // Dynamic Routing
           <Route path=":id" element={<Book />} />
       </Route>
       <Route path="*" element={<NotFound />} />
    </Routes>
  )
}

export default App;

```


**BookLayout.jsx**

```jsx
import { Outlet } from "react-router-dom"

function BookLayout () {
  return (
   <>
     <h1> Book layout </h1> 
     <Ooutlet context={{hello:'Hello'}} />
   </>
  )
}

```

**Home.jsx**
```jsx
import { Link } from "react-router-dom"
 function Home () {
   return (
     <>
       <Link to="/books">Books</Link>
     </>
   )
 }
```

**Books.jsx**
```jsx 
function () {
 return (
   <>
     <h1>Books</h1>
     <Link to="/books/1" > Book 1 </Link>
     <Link to="/books/2" > Book 1 </Link>
   </>
 )
}
```

***Dynamic Route***
**Book.jsx**
```jsx
import { useParams, useOutletContext } from "react-router-dom"


function Book () {
  const params = useParams()
  const obj = useOutletContext()
  
  return (
    <>
      Book: {params.id}
      { obj.hello }
    </>
  )
}
```




#### Routing (createBrowserRouter)

**App.jsx**
```jsx
import { createBrowserRouter,  createRoutesFromElements, RouterProvider, route, routes } from "react-router-dom" 
import Home from "./Home"
import BookLayout from "./BookLayout"
import Books from "./Books"
import NotFound from "./NotFound"


const allRoutes = createBrowserRouter(
   createRoutesFromElements(
       <Route path="/" element={<Home />} />
       <Route path="/books" element={<BookLayout />} > 
           // Inside the BookLayout use <Outlet />*
           <Route index element={<Books />} />
          // Dynamic Routing
           <Route path=":id" element={<Book />} />
       </Route>
   )
)

function App () {
  return (
    <RouterProvider router={allRoutes} />
  )
}

export default App;```