
#### React query

- [ ] What ?
   - A library for fetching data in a react application
- [ ] Why ?
   - Since React is a UI library, there is no specific pattern for data fetching. 
   - useEffect hook for data fetching and useState hook to maintain component state like loading error or resulting data.
   - If the date is needed throughout the app, we tend to use state management libraries.
   - Most of the state management libraries are good for working with client state.
   - State management libraries are not great for working with asynchronous or server state.


###### Project setup

**Install**
```shell
  npm i @tanstack/react-query
```

```jsx
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";
import { ReactQueryDevtools } from "@tanstack/react-query-devtools";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";


// Create a client
const queryClient = new QueryClient();

  
ReactDOM.createRoot(document.getElementById("root")).render(
  // <React.StrictMode>
  <QueryClientProvider client={queryClient}>
    <App />
    <ReactQueryDevtools initialIsOpen={true} />
  </QueryClientProvider>
  // </React.StrictMode>,

);
```

```jsx
import { useQuery } from "@tanstack/react-query";  

const HomePage = () => {
  const { isLoading, data } = useQuery({
    queryKey: ["users"],
    queryFn: async () => {
      const res = await fetch("http://localhost:3000/data", { method: "GET" });
      const data = await res.json();
      return data;
    },
  });

  

  if (isLoading) {
    return <>Loading...</>;
  }
  

  if (!isLoading && data?.length > 0) 
    return (
      <>
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      </>
    );
  }
};

  

export default HomePage;
```