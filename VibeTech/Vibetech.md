
```javascript 

import PrimaryHeader from "../components/Header/PrimaryHeader/PrimaryHeader";


const HEADER_CONFIG = {
  isSticky: true,
  styleVariant: false,
  logoVarient: "LIGHT",
  className: "bg-color-black",
  button: {
    isVisible: true,
    text: "Get a quote",
    classNames: "white-border",
    path: "/contact-us",

  },
  menu : {
    align : "end",
    classNames : ""
  }
};

  

const MyComponent = () => {
  return (
      <PrimaryHeader {...HEADER_CONFIG} />
  );
};


export default  MyComponent;

``` 





```javascript

const DEFAULT_HEADER_CONFIG = {
  isSticky: true,
  styleVariant: "two",
  logoVarient: "LIGHT",
  className: "",
  button: {
    isVisible: true,
    text: "Get a quote",
    classNames: "",
    path: "/contact",
  },
  menu: {
    align: "end",
    classNames: "",
  },
};
```



```jsx

// Example 1: Regular heading 

<SectionTitle 
 variant="one" 
 className="custom-heading" 
 headingTitle={{ text: "Main Title", className: "title-style" }} 
 heading={{ text: "Sub-heading", className: "sub-heading-style" }} 
 headingDescription={{ text: "Description goes here", className: "desc-style" }} 
 /> 



// Example 2: Stroked heading with stroke variant 

<SectionTitle 
 variant="two" 
 strokeVariant="one" 
 className="custom-heading" 
 headingTitle={{ text: "Stroked Title", className: "stroked-title-style" }} 
 heading={{ text: "Sub-heading", className: "sub-heading-style" }} 
/>

```


```JSX 
<div data-aos="flip-up" data-aos-anchor-placement="bottom-bottom" 
data-aos-duration="1500" > Title </div>

<li data-aos="fade-right" data-aos-duration="1500" data-aos-delay="100" 
 className="fade_left">  Business Process Optimization </li>

<img  data-aos="flip-left"  data-aos-duration="3000" className="w-100"src="./images/history-img-1.png" alt="photo" />           

<div data-aos="fade-right" data-aos-duration="1500" > Fade left </div>
              
```
