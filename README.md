# Object-Manipulation - The JavaScript object cheatsheet
This is a work in progress cheatsheet for JS objects. Please, feel free to comment if this helped you or give any feedback or suggestion for improvements.

- [Create an empty object](#creating)
- [Add propreties and values](#adding)
- [Accessing the data](#accessing)
- [Manipulating the data](#manipulating)
- [Looping through an object](#looping)
- [Cloning an object properties](#cloning-keys)
- [Cloning an object values](#cloning-values)

## Creating
```javascript
var objectName = {};
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
```
## Accessing
```javascript
// dot notation
objectName.name; // "Rabah"

// bracket notation
objectName["name"]; // "Rabah"
```
## Manipulating
```javascript
objectName.age = 25;

objectName["age"]  // 25
```
## Looping
```javascript
for (var property in objectName) {
  if (property === ...) {
    // Do things her
  }
}
```
## Cloning keys
```javascript
var objectKeys = [];

for (var property in objectName) {
  objectKeys.push(property);
}
```
## Cloning values
```javascript
var objectValues = [];

for (var property in objectName) {
  objectValues.push(objectName[property]);
}
```
