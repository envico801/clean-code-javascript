========== Question ==========  

### Single concept per test

**Bad:**

```javascript
import assert from 'assert';
describe('MomentJS', () => {
    it('handles date boundaries', () => {
        let date;
        date = new MomentJS('1/1/2015');
        date.addDays(30);
        assert.equal('1/31/2015', date);
        date = new MomentJS('2/1/2016');
        date.addDays(28);
        assert.equal('02/29/2016', date);
        date = new MomentJS('2/1/2015');
        date.addDays(28);
        assert.equal('03/01/2015', date);
    });
});
```  

========== Answer ==========  

**Good:**

```javascript
import assert from 'assert';
describe('MomentJS', () => {
    it('handles 30-day months', () => {
        const date = new MomentJS('1/1/2015');
        date.addDays(30);
        assert.equal('1/31/2015', date);
    });
    it('handles leap year', () => {
        const date = new MomentJS('2/1/2016');
        date.addDays(28);
        assert.equal('02/29/2016', date);
    });
    it('handles non-leap year', () => {
        const date = new MomentJS('2/1/2015');
        date.addDays(28);
        assert.equal('03/01/2015', date);
    });
});
```

========== Id ==========  
36

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 6 - Testing

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-6-Testing::#36-Single-concept-per-test-bad-javasc

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
