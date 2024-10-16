========== Question ==========  

### Don't write to global functions

Polluting globals is a bad practice in JavaScript because you could clash with another

library and the user of your API would be none-the-wiser until they get an

exception in production. Let's think about an example: what if you wanted to

extend JavaScript's native Array method to have a `diff` method that could

show the difference between two arrays? You could write your new function

to the `Array.prototype`, but it could clash with another library that tried

to do the same thing. What if that other library was just using `diff` to find

the difference between the first and last elements of an array? This is why it

would be much better to just use ES2015/ES6 classes and simply extend the `Array` global.

**Bad:**

```javascript
Array.prototype.diff = function diff(comparisonArray) {
    const hash = new Set(comparisonArray);
    return this.filter((elem) => !hash.has(elem));
};
```  

========== Answer ==========  

**Good:**

```javascript
class SuperArray extends Array {
    diff(comparisonArray) {
        const hash = new Set(comparisonArray);
        return this.filter((elem) => !hash.has(elem));
    }
}
```

========== Id ==========  
17

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#17-Don-t-write-to-global-functions-polluting

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
