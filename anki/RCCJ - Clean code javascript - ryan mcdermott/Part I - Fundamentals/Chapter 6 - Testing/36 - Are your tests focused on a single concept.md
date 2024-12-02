========== Question ==========  

### Are your tests focused on a single concept?

Look at this test code. What makes it hard to understand and maintain?

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

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens if one assertion fails? How easy is it to identify which case failed?

-   How many different concepts are being tested in a single test?

-   What's the story this test is trying to tell?

-   How could you make the test's purpose clearer?

</details>  

========== Answer ==========  

**The Principle**:

Tests should be clear, focused, and test one specific concept or behavior. This makes tests easier to maintain, debug, and understand when they fail. Each test should tell a story about a specific behavior of your code.

**Solution**:

Here's a better way to structure these tests:

```javascript
import assert from 'assert';

describe('MomentJS date handling', () => {
    describe('when adding days to a date', () => {
        it('correctly handles the last day of a 31-day month', () => {
            const date = new MomentJS('1/1/2015');
            date.addDays(30);
            assert.equal('1/31/2015', date);
        });

        it('properly handles leap year February', () => {
            const date = new MomentJS('2/1/2016');
            date.addDays(28);
            assert.equal('02/29/2016', date);
        });

        it('correctly transitions to next month in non-leap year February', () => {
            const date = new MomentJS('2/1/2015');
            date.addDays(28);
            assert.equal('03/01/2015', date);
        });
    });
});
```

**Why is this better?**

1. Each test has a single, clear purpose

2. Test names clearly describe the behavior being tested

3. When a test fails, you immediately know which scenario failed

4. Tests are organized hierarchically by functionality

5. Each test tells a complete story

========== Id ==========  
36

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 6 - Testing

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-6-Testing::#36-Are-your-tests-focused-on-a-single-concept

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
