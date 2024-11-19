========== Question ==========  

### Are you following the Liskov Substitution Principle (LSP)?

The Liskov Substitution Principle states that objects of a superclass should be replaceable with objects of its subclasses without breaking the application. In simpler terms, child classes must be able to do everything their parent class can do.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#liskov-substitution-principle-lsp](https://github.com/ryanmcdermott/clean-code-javascript#liskov-substitution-principle-lsp)

**Bad:**

```javascript
class Rectangle {
    constructor() {
        this.width = 0;
        this.height = 0;
    }

    setColor(color) {
        // ...
    }

    render(area) {
        // ...
    }

    setWidth(width) {
        this.width = width;
    }

    setHeight(height) {
        this.height = height;
    }

    getArea() {
        return this.width * this.height;
    }
}

class Square extends Rectangle {
    setWidth(width) {
        this.width = width;
        this.height = width;
    }

    setHeight(height) {
        this.width = height;
        this.height = height;
    }
}

// This breaks LSP because Square doesn't behave like a Rectangle
function renderLargeRectangles(rectangles) {
    rectangles.forEach((rectangle) => {
        rectangle.setWidth(4);
        rectangle.setHeight(5);
        const area = rectangle.getArea(); // BAD: Returns 25 for Square. Should be 20.
        rectangle.render(area);
    });
}

const rectangles = [new Rectangle(), new Rectangle(), new Square()];
renderLargeRectangles(rectangles);
```  

========== Answer ==========  

The solution creates a proper hierarchy where each shape handles its own properties correctly through a common interface. This respects LSP because each shape can be used interchangeably when calculating and rendering areas.

**Good:**

```javascript
class Shape {
    setColor(color) {
        // ...
    }

    render(area) {
        // ...
    }
}

class Rectangle extends Shape {
    constructor(width, height) {
        super();
        this.width = width;
        this.height = height;
    }

    getArea() {
        return this.width * this.height;
    }
}

class Square extends Shape {
    constructor(length) {
        super();
        this.length = length;
    }

    getArea() {
        return this.length * this.length;
    }
}

function renderLargeShapes(shapes) {
    shapes.forEach((shape) => {
        const area = shape.getArea();
        shape.render(area);
    });
}

const shapes = [new Rectangle(4, 5), new Rectangle(4, 5), new Square(5)];
renderLargeShapes(shapes);
```

========== Id ==========  
33

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 5 - SOLID

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#33-Are-you-following-the-liskov-substitution

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
