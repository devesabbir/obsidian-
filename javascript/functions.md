
#### Curry Function

```javascript

// normal function
const multiplier = (a , b, c) => {
   return a * b * c
}


// curry function
const curryfunc = (a) => {
  return (b) => {
    return (c) => {
      return a * b * c 
    }
  }
}

// calling curry function 
curryfunc(2)(3)(4)(5)

// convert any function to curry function 
 const curryConverter = (fn) => {
      return function curried(...args) {
        if (args.length >= fn.length) {
          return fn(...args);
        } else {
          return function (...args2) {
            return curried(...args, ...args2);
         };
       }
    };
 };

const curried = curryConverter(multiplier)

console.log(curried(2)(3)(4))
console.log(curried(2,3)(4))

```


#javascript  #function #curry_function
