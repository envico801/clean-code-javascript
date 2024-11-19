========== Question ==========  

### Are you using Async/Await for even cleaner code?

Async/await is a modern JavaScript feature that makes asynchronous code look and behave more like synchronous code. It provides the best readability while maintaining all the benefits of Promises, making code easier to understand and maintain.

**Bad:**

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

========== Answer ==========  

Using async/await makes the code read like synchronous code while maintaining asynchronous behavior. The try/catch block provides familiar error handling syntax, making it more intuitive for developers.

**Good:**

```javascript
import { get } from 'request-promise';
import { writeFile } from 'fs-extra';

async function getCleanCodeArticle() {
    try {
        const body = await get(
            'https://en.wikipedia.org/wiki/Robert_Cecil_Martin',
        );
        await writeFile('article.html', body);
        console.log('File written');
    } catch (err) {
        console.error(err);
    }
}

getCleanCodeArticle();
```

========== Id ==========  
38

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 7 - Concurrency

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#38-Are-you-using-async-await-for-even-cleaner

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
