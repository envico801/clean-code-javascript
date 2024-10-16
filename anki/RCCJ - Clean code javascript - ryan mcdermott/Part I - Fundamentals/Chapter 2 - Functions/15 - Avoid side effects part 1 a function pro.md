========== Question ==========  

### Avoid Side Effects (part 1)

A function produces a side effect if it does anything other than take a value in

and return another value or values. A side effect could be writing to a file,

modifying some global variable, or accidentally wiring all your money to a

stranger.

Now, you do need to have side effects in a program on occasion. Like the previous

example, you might need to write to a file. What you want to do is to

centralize where you are doing this. Don't have several functions and classes

that write to a particular file. Have one service that does it. One and only one.

The main point is to avoid common pitfalls like sharing state between objects

without any structure, using mutable data types that can be written to by anything,

and not centralizing where your side effects occur. If you can do this, you will

be happier than the vast majority of other programmers.

**Bad:**

```javascript
// Global variable referenced by following function.
// If we had another function that used this name, now it'd be an array and it could break it.
let name = 'Ryan McDermott';
function splitIntoFirstAndLastName() {
    name = name.split(' ');
}
splitIntoFirstAndLastName();
console.log(name); // ['Ryan', 'McDermott'];
```  

========== Answer ==========  

**Good:**

```javascript
function splitIntoFirstAndLastName(name) {
    return name.split(' ');
}
const name = 'Ryan McDermott';
const newName = splitIntoFirstAndLastName(name);
console.log(name); // 'Ryan McDermott';
console.log(newName); // ['Ryan', 'McDermott'];
```

========== Id ==========  
15

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#15-Avoid-side-effects-part-1-a-function-pro

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
