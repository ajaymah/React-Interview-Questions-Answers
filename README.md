# React-Interview-Questions-Answers

## 1-What is React
React is a JavaScript library that is used for building UI components, user interfaces, especially for single-page applications.
React is  created by Facebook.

## 2-What are the major features of React?
- **Component-Based Architecture**   
- **Virtual DOM** - Virtual DOM instead of Real DOM considering that Real DOM manipulations are expensive.  
- **JSX (JavaScript XML)** - JSX syntax, a syntax extension of JS that allows developers to write HTML in their JS code  
- **Unidirectional Data Flow** - Follows Unidirectional or one-way data flow or data binding. 
- **Reusable Components** - reusable/composable UI components to develop the view.
- **React Ecosystem**
- **Server-Side Rendering (SSR)** - Supports server-side rendering which is useful for Search Engine Optimizations(SEO).  
- **Context API**
- **Hooks**
  
 ## 3-What is JSX? ##
- JSX stands for JavaScript XML.
- JSX allows us to write HTML in React.
- JSX makes it easier to write and add HTML in React.
- JSX allows us to write HTML elements in JavaScript and place them in the DOM without any createElement()  and/or appendChild() methods.

## 4-What is the Difference between Element and Component ?##
An Element is an object that represents a DOM node it is a part of DOM structure, while a *component is a reusable block of code* that contains logic, states, and also returns the Element.
> [!NOTE]
> component is a reusable block of code that contains logic, states, and also returns the Element

## 5-How to create components in React? ##
Components are the building blocks of creating User Interfaces(UI) in React. There are two possible ways to create a component. 

***Function Components:*** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the one and only one parameter and return React elements to render the output:  

***Class Components:*** You can also use ES6 class to define a component. The above function component can be written as a class component:  

## 6-What is the Difference UI Rendring methode ?##
***Client-Side Rendering (CSR)***

Client-Side Rendering(**CSR**) is a technique, In which web pages are rendered on the client’s browser by useing JavaScript to change the DOM element. 
This method with CSR frameworks including Vue.js, React, and Angular. A simple HTML page is first loaded, and future content updates are fetched and rendered dynamically using API requests.

>CSR provides a responsive and interactive user experience by allowing real-time updates

>Frontend and backend developers to work independently

> [!NOTE]
>*_When to use CSR*_
>-Building highly interactive applications that require real-time updates, such as social media platforms, dashboards.
>-Requiring a single-page application (SPA) architecture for a superb user experience without page reloads.

***Server-Side Rendering (SSR)***

web pages rendering on the server before sending them to the client’s browser.
This process of rendering web pages on the server before sending them to the client’s browser that is called SSE
Next js enable developers to build JavaScript code that runs on both the server and the client.

> [!NOTE]
>**Advantages: -** Search engines can easily crawl and index the fully rendered HTML, that help for  better search rankings
> 
> **When to use:** - Content-based websites, blogs, e-commerce platforms where SEO is a first priority.

***Static Site Generation (SSG)***

Generating static HTML files for each page and  developers to create high-performance websites that can be served directly from a Content Delivery Network (CDN).

**Advantages**  -- static HTML files can be cached and served directly, resulting in fast page rendering and reduced server load.
**When to use** -- Building content-heavy websites, blogs, or documentation sites where content updates are infrequent.

***Universal Rendering(UR)***

when the browser requests a URL with universal (server-side + client-side) rendering enabled, the server returns a fully rendered HTML page to the browser. Whether the page has been generated in advance and cached 

All are different approaches to rendering web content

## 7- Top 5 acid tests for your website! ##
1 - Crawling - google search console
2 - Indexing 
3 - Ranking and Serving

## 8- How browsers read JSX? ##
Browsers is not capable of reading JSX code, only can read JavaScript code.   
The browsers read JSX with the help of a transpiler. Transpilers are used to convert JSX into JavaScript. The transpiler used is called Babel.  

## 9- What is higher-order component in React? ##
Hoc is a function that takes a component and return a new component with enhanceed behaviour or additionl props  
like it as a weaper component that add functionality to a component without modifying the original component  
we can reusing the component functionality logic  
**use case**
   code reuse, Access controll, inject props or data
> [!NOTE]
> Dont modify the orignal code, always ppass props down

## 10- What is Context API in React? ##  
React context api is a way to share data across component without passing pross manually. 
> [!NOTE]
> when it use -- Avoiding props drilling  
***Example:***
```
import  { createContext } from 'react';  
export const UserContext = createContext();
  
export cont UserProvider = ({children})=>{  
   return (  
      <UserContext.Provider value = {"Ajay"}>  
        {children}  
      </UserContext.provider>  
    )  
}
///////////////////////////////////////

import { UserProvider }  from 'UserContext'

function App (){
  return (
    <Header/>
    <Section/>
  ) 
}

// consume //  

import { useContext } from 'react';
import { UserContext } from 'UserContext';

const Header = ()=> {  
    const  user = useContext(UserContext);  
    <p>{user}</p>  
}  
```
### 11- What are Pure Components in React? ###  
Pure Component is similar to React component, but it automatically implements ShouldComponentUpdate() with shallow props and state comparison.  
> [!NOTE]  
> when use -- component renderd the same output.  
> Shallow compare  
   Primitive types (number, string, boolean) compare by value  
   object and array: compare by refrence, it triger a re-render

### 12- What are hooks in React? ###
Hooks are special function in React js **(v16.8+)** that let you use state and other React feature in functional component without writing a class component  
**1- useState** - Add state to functional component  
**2- useEffect** - perform side effects (this will work with lifcycle mount, updating and unmount)  
**3- useContext** - we can set global state, aboide props drilling  
**4- useRef** - get refrence to Dom or staore mutable value  
**5- useMemo** - memoizes expensive calculation  
**6-useCallback** - memoizes function to avoide re-creatingthem on every render  
**7- useReducer** - complex state logic  
> [!NOTE]
> Rules  
 **Call Hooks at top lavel** - not inside loop, conditions, or nested function

### what is the difference between a custom hook and a function ###  
**JavaScript function** is a set of statements that perform a specific task. Functions are the basic building blocks of any JavaScript program, and they can be used in various ways, such as defining reusable code, organizing your code,  
**React Hooks** are specifically designed to interact with the React component lifecycle and state management.

### What React Query ###
React Query of TanStack Query, is a powerful data-fetching and state management library for React applications. It simplifies the process of fetching, caching, synchronizing, and updating server state.  
**Declarative Data Fetching:**  
It utilizes hooks like **useQuery** for fetching data and **useMutation** for performing data modifications (e.g., creating, updating, deleting). This declarative approach leads to cleaner and more organized code.  
**Error Handling and Loading States:**  
It provides clear mechanisms for handling loading states, errors, and other query statuses, making it easier to build robust and user-friendly interfaces.  
```
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import {QueryClient, QueryClientProvider} from '@tanstack/react-query';
import {ReactQueryDevTools} from "@tanstack/react-query-devtool"

const root = ReactDOM.createRoot(
  document.getElementById('root') as HTMLElement
);
const queryClient = new QueryClient()
root.render(
  <React.StrictMode>
<QueryClientProvider client={queryClient}>
    <App />
    <ReactQueryDevTools initialIsopen={false}/>
<QueryClientProvider/>
  </React.StrictMode>
);
```

```
import {useQuery} from '@tanstack/react-query'
function App(){
   const {data:postData, isloading, isError, error, status} = useQuery({
      queryKey:["post"],
	  queryfn: fetchPost
   })
   
}
```

```
post data
import { useMutation } from 'react-query';
const postData = async (newData) => {
      const response = await fetch('/api/your-endpoint', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(newData),
      });
      if (!response.ok) {
        throw new Error('Failed to post data');
      }
      return response.json();
    };

const { mutate, isLoading, isError, isSuccess, error } = useMutation(postData, {
      onSuccess: (data) => {
        // Handle successful mutation, e.g., invalidate queries, show a success message
        console.log('Data posted successfully:', data);
      },
      onError: (error) => {
        // Handle error, e.g., show an error message
        console.error('Error posting data:', error);
      },
    });


const handleSubmit = (event) => {
      event.preventDefault();
      const dataToPost = { name: 'John Doe', email: 'john@example.com' }; // Example data
      mutate(dataToPost);
    }
```

### 13- Principles of Accessibility ###
Four Principles of Accessibility  
1 **.Perceivable(Noticeable)** - Information and user interface components must be presentable to users in ways they can understand.  
2 **Operable** - User interface components and navigation must be operable. (users must be able to operate the interface)  
3 **Understandable** - Information and the operation of user interface must be understandable.
4 **Robust** - Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.

### 13 - how react works in browser ###
Instead of directly updating the entire DOM when data changes, React first creates a virtual representation of the DOM in memory. It then calculates the most efficient way to update the actual DOM, reducing the need for full page reloads and improving  

**Here's a breakdown of how it works:**  
**Initial Load:**  
**Virtual DOM Creation**
**Initial Render:**  
**State and Prop Changes & Reconciliation:**  
**Efficient DOM Updates:**  

### 14 -  how can improve react application performance ###
**Optimizing Component Rendering:**  
Memoization with React.memo   
useCallback and useMemo Hooks:  
Unique Keys in Lists:  
Avoid Inline Function Definitions:  
**Optimizing Resource Loading:**  
React.lazy and Suspense  
Image Optimization: - Implement lazy loading for images and optimize image sizes
Virtualization for Long Lists: - Use libraries like react-window or react-virtualized to render only the visible items in long lists,


### 15 - react-window or react-virtualized ###


### 15- what is lazy loading in react ###
Lazy loading in React is a performance optimization technique   
Lazy loading allows for code splitting and on-demand loading of specific parts of the application.   
**Key concepts of lazy loading in React:**  
**Code Splitting**: - The application's code is divided into smaller, independent chunks or bundles.  
**Dynamic Imports:** -  React.lazy() function, in conjunction with dynamic import(), enables the asynchronous loading of components. Instead of traditional static imports at the top of a file,  
**Suspense:** - The Suspense component from React is used to wrap lazy-loaded components. It provides a fallback UI (e.g., a loading spinner) that is displayed while the lazy-loaded component is being fetched and rendered.  
**Benefits of lazy loading:** Reduced Initial Load Time,

### How to sanitize JS and HTML in inputs ###
Validate input (frontend)  -  Ensure that the data conforms to what you expect before submission  
Sanitize input (backend)  -  Employ means on the backend to escape or remove unsafe characters before it reaches your application's storage layer  
Escape output (backend)  -  As an additional safety measure, before outputting, be sure to escape anything coming from a 3rd party source  

### Reconciliation ###
Reconciliation is a process in React that helps it update the UI efficiently. Whenever something changes in your app, like the data or state, React needs to update the web page to reflect those changes  
**Reconciliation** - Reconciliation in React.js is the process React uses to efficiently update  
insteed of direct manipulations of the actual Document  
**How Reconciliation Works:**  
1- _Virtual DOM:_ - When a component's state or props change, React doesn't immediately update the real DOM. Instead, it creates a new "Virtual DOM" tree,  
which is a lightweight, in-memory representation of the UI.  
2- _Diffing Algorithm:_ - React then compares this new Virtual DOM tree with the previous Virtual DOM tree using a "diffing algorithm."  
3- _Minimal DOM Updates:_ - React calculates the most efficient set of changes required to update the real DOM. It only modifies the specific parts of the DOM that have   actually changed, rather than re-rendering the entire page.  
4- _Fiber Reconciler:_ - 

### React Component Recurson ###
```
const orgData = [{
  name: "CEO",
  children: [
    {
      name: "CTO",
      children: [
        {
          name: "Dev Manager",
          children: [{ name: "Developer 1" }, { name: "Developer 2" }],
        },
      ],
    },
    { name: "CFO"},
    {
      name: "COO",
      children: [{ name: "Operations Manager" }],
    },
  ],
}];
//////////////////////////////////////
const RecursiveList = ({ items }) => {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>
          {item.name}
          {item.children && item.children.length > 0 && (
            <RecursiveList items={item.children} />
          )}
        </li>
      ))}
    </ul>
  );
};
///////////////////////////////
<RecursiveList items={orgData} />
```
### react unused variable how can remove ###
1  Manual Removal  
2  Using ESLint
3  Using IDE Features: VS Code - Extensions like "CleanDeadCode" 

**Tools for Unused Dependencies:**
**depcheck**: This tool helps identify unused dependencies in your package.json file, allowing you to remove them and keep your project dependencies lean.










