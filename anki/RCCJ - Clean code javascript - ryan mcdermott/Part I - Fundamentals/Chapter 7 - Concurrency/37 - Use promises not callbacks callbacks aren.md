========== Question ==========  

### Use Promises, not callbacks

Callbacks aren't clean, and they cause excessive amounts of nesting. With ES2015/ES6,

Promises are a built-in global type. Use them!

**Bad:**

```javascript
import { get } from 'request';
import { writeFile } from 'fs';
get(
    'https://en.wikipedia.org/wiki/Robert_Cecil_Martin',
    (requestErr, response, body) => {
        if (requestErr) {
            console.error(requestErr);
        } else {
            writeFile('article.html', body, (writeErr) => {
                if (writeErr) {
                    console.error(writeErr);
                } else {
                    console.log('File written');
                }
            });
        }
    },
);
```  

========== Answer ==========  

**Good:**

```javascript
import { get } from 'request-promise';
import { writeFile } from 'fs-extra';
get('https://en.wikipedia.org/wiki/Robert_Cecil_Martin')
    .then((body) => {
        return writeFile('article.html', body);
    })
    .then(() => {
        console.log('File written');
    })
    .catch((err) => {
        console.error(err);
    });
```

========== Id ==========  
37

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 7 - Concurrency

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#37-Use-promises-not-callbacks-callbacks-aren

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
