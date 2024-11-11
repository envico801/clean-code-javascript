========== Question ==========  

### Async/Await are even cleaner than Promises

Promises are a very clean alternative to callbacks, but ES2017/ES8 brings async and await which offer an even cleaner solution. All you need is a function that is prefixed in an `async` keyword, and then you can write your logic imperatively without a `then` chain of functions. Use this if you can take advantage of ES2017/ES8 features today!

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#38-Async-await-are-even-cleaner-than-promises

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
