
title: "Modern JavaScript ES6+"
date: 2024-01-25
draft: false
description: "Learn new JavaScript features"
categories: ["Programming", "JavaScript"]
tags: ["javascript", "es6", "tutorial"]

Modern JavaScript: From ES6 to Today
Variables: let and const
javascript
// Old
var name = "Ali";

// Modern
let age = 30;
const PI = 3.14;
Arrow Functions
javascript
// Old
function add(a, b) {
    return a + b;
}

// Modern
const add = (a, b) => a + b;
Template Literals
javascript
const name = "Ali";
console.log(`Hello ${name}!`); // Hello Ali!
Destructuring
javascript
const person = { name: "Ali", age: 30 };
const { name, age } = person;
Modules
javascript
// export
export const PI = 3.14;
export function calculate() { ... }

// import
import { PI } from './math.js';
Async/Await
javascript
async function fetchData() {
    try {
        const response = await fetch(url);
        const data = await response.json();
        return data;
    } catch (error) {
        console.error(error);
    }
}
Conclusion
Modern JavaScript makes code cleaner and more readable.
