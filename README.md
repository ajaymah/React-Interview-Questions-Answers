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





