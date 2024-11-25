---
title: JavaScript Tips and Tricks
description: A collection of useful JavaScript tips and tricks for everyday development.
pubDatetime: 2024-03-15T16:30:00Z
tags: ["javascript", "development", "tips"]
---

# JavaScript Tips and Tricks

## Array Operations

### 1. Quick Array Deduplication
```javascript
const array = [1, 2, 2, 3, 3, 4];
const unique = [...new Set(array)];
// Result: [1, 2, 3, 4]
```

### 2. Array Flattening
```javascript
const nested = [1, [2, 3], [4, [5, 6]]];
const flat = nested.flat(Infinity);
// Result: [1, 2, 3, 4, 5, 6]
```

## Object Manipulation

### 1. Object Property Shorthand
```javascript
const name = 'John';
const age = 30;
const user = { name, age };
// Same as: { name: name, age: age }
```

### 2. Object Destructuring with Aliases
```javascript
const data = { a: 1, b: 2 };
const { a: first, b: second } = data;
// first = 1, second = 2
```

## Function Tricks

### 1. Default Parameters
```javascript
function greet(name = 'Guest') {
    return `Hello, ${name}!`;
}
```

### 2. Rest Parameters
```javascript
function sum(...numbers) {
    return numbers.reduce((a, b) => a + b, 0);
}
```

## Modern Features

### 1. Optional Chaining
```javascript
const user = {
    details: {
        // address might not exist
        address: {
            street: '123 Main St'
        }
    }
};

const street = user?.details?.address?.street;
```

### 2. Nullish Coalescing
```javascript
const value = null;
const defaultValue = value ?? 'default';
// Different from: value || 'default'
// as it only falls back on null or undefined
```

## Async Operations

### 1. Async/Await with Error Handling
```javascript
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}
```

### 2. Promise.all with Named Results
```javascript
const promises = {
    users: fetch('/api/users'),
    posts: fetch('/api/posts'),
    comments: fetch('/api/comments')
};

const results = await Object.fromEntries(
    await Promise.all(
        Object.entries(promises).map(
            async ([key, promise]) => [
                key,
                await (await promise).json()
            ]
        )
    )
);
```

Remember that these are just examples, and there are many more JavaScript features and tricks to explore!
