
```javascript
  // Original array of objects
	const originalArray = [
	  { id: 1, name: 'John' },
	  { id: 2, name: 'Jane' },
	  { id: 3, name: 'Doe' }
	];
	
	// Creating a deep copy using JSON.parse and JSON.stringify
	const newArray = JSON.parse(JSON.stringify(originalArray));
	
	// Now, newArray is a completely independent copy with different       references
	console.log(newArray);

```


```javascript
// Original array of objects
const originalArray = [
  { id: 1, name: 'John' },
  { id: 2, name: 'Jane' },
  { id: 3, name: 'Doe' }
];

// Creating a deep copy using map and object spread
const newArray = originalArray.map(obj => ({ ...obj }));

// Now, newArray is a completely independent copy with different references
console.log(newArray);

```


```javascript
  // Original array of objects
const originalArray = [
  { id: 1, name: 'John' },
  { id: 2, name: 'Jane' },
  { id: 3, name: 'Doe' }
];

// Creating a deep copy using Object.assign
const newArray = originalArray.map(obj => Object.assign({}, obj));

// Now, newArray is a completely independent copy with different references
console.log(newArray);

```


```javascript
   // Assuming lodash is available in your project
const _ = require('lodash');

// Original array of objects
const originalArray = [
  { id: 1, name: 'John' },
  { id: 2, name: 'Jane' },
  { id: 3, name: 'Doe' }
];

// Creating a deep copy using lodash's cloneDeep
const newArray = _.cloneDeep(originalArray);

// Now, newArray is a completely independent copy with different references
console.log(newArray);

```