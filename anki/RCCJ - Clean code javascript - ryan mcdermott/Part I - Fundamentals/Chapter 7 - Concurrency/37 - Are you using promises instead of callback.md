========== Question ==========  

### Are you using Promises instead of callbacks?

Promises provide a cleaner way to handle asynchronous operations compared to callbacks. They help avoid "callback hell" (deeply nested callbacks) and provide better error-handling mechanisms. Promises make asynchronous code more readable and maintainable.

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

Using Promises creates a flat chain of operations that's easier to read and maintain. Error handling is consolidated into a single .catch() block, making the code more concise and clearer.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#37-Are-you-using-promises-instead-of-callback

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
