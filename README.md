# Object-Manipulation - The JavaScript object cheatsheet
This is a work in progress cheatsheet for JS objects. Please, feel free to comment if this helped you or give any feedback or suggestion for improvements.

- [Create an empty object](#creating)
- [Add propreties and values](#adding)
- [Accessing the data](#accessing)
- [Manipulating the data](#manipulating)
- [Looping through an object](#looping)
- [Cloning an object properties](#cloning-keys)
- [Cloning an object values](#cloning-values)
- [The **`in`** operator](#in-operator)
- [Defining methods (functions) in objects](#defining-methods)
- [Using those methods (functions)](#using-methods)
- [Using **`this`** for objects](#this-keyword)

## Creating
```javascript
const objectName = {};
```
## Adding
#### 1. Using `.` dot notation:
```javascript
objectName.name = "Rabah";
objectName.age = 18;
```
#### 2. Using `[]` bracket notation:
```javascript
objectName["name"] = "Rabah";
objectName["age"] = 18;

// another way with variables
const newProp = 'location';
objectName[newProp] = 'FL'

/*
objectName = {
  name: "Rabah",
  age: 18,
  location: "FL"
}
*/


```
## Accessing
```javascript
// dot notation
objectName.name; // "Rabah"

// bracket notation
objectName["name"]; // "Rabah"

// extra variation
const propName = "location";
objectName[propName] // "FL"
```
## Manipulating
```javascript
objectName.age = 25;

objectName["age"] = 30 // 30 
// objectName = {...otherProps, age: 30}
```
## Looping
```javascript
for (let property in objectName) {
  if (property === ...) {
    // Do things here
  }
}

for (let i = 0; i < 10; i++) {
  // Do something here
}

while(condition) { // condition needs to be false at some point
  // Do something here
}
```
## Cloning keys
```javascript
const objectKeys = [];

for (let property in objectName) {
  objectKeys.push(property);
}

console.log(objectKeys) // ["name", "age", "location"

// alternatively
const keys = Object.keys(objectName); 
console.log(keys) // ["name", "age", "location"]
```
## Cloning values
```javascript
const objectValues = [];

for (let property in objectName) {
  objectValues.push(objectName[property]);
}

console.log(objectValues) // ["Rabah", 25, "FL"]

// alternatively
const values = Object.values(objectName);
console.log(values) // ["Rabah", 25, "FL"]
```
## `in` operator
```javascript
if ("favoriteColor" in objectName) { // if the property favoriteColor exists in objectName
  // do something if true
} else {
  // do something otherwise
}
```
## Defining methods
```javascript
// The same way we add properties
objectName.sayBonjour = function(name) {
  console.log(`Bonjour ${name}.`);
}
```
## Using methods
```javascript
objectName.sayBonjour("Peggy"); // "Bonjour Peggy."
```
## `this` keyword
```javascript
  // Let's add a new method
  objectName.sayMyAge = function() {
    this.sayBonjour('Mathieu');
    console.log(`I'm ${this.age} years old.`);
  }
```  
### Explanation:
  ```javascript
  // Now our object looks like this
  objectName = {
    name: "Rabah",
    age: 25,
    location: "FL",
    sayBonjour: function(name) {
      console.log(`Bonjour ${name}.`);
    },
    sayMyAge: function() {
    
      this.sayBonjour('Mathieu');
      // Since the method 'sayBonjour' it's outside of this method scope, 
      // which is inside the objectName. so to refer to it and use it by calling it, we have to use the 'this' keyword.
      // Using the 'this.sayBonjour()' keyword is the same thing as saying:
      // objectName.sayBonjour()
       
      console.log(`I'm ${this.age} years old.`);
      // The same thing happening here. We're saying '`I'm ${objectName.age} years old.'
      
    }
  }   
  ```
  //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
  ```javascript
  sayMyAge();   // "Bonjour Mathieu."
                // "I'm 25 years old."
  ```
