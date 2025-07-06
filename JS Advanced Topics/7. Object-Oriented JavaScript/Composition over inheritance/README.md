## Introduction
Composition over inheritance is a design principle that promotes using composition (combining smaller, reusable components) instead of inheritance to build complex systems. This approach avoids the pitfalls of deep inheritance hierarchies.

## Real-Life Example
Think of a LEGO set. You can build various structures by combining different LEGO pieces (composition) instead of relying on a fixed blueprint (inheritance).

### Code Example
```javascript
const canFly = {
    fly: function() {
        console.log(`${this.name} is flying.`);
    }
};

const canSwim = {
    swim: function() {
        console.log(`${this.name} is swimming.`);
    }
};

function createBird(name) {
    const bird = { name };
    return Object.assign(bird, canFly);
}

const eagle = createBird('Eagle');
eagle.fly(); // Eagle is flying.
```

## Problems It Solves
1. **Flexibility**: Avoids rigid inheritance hierarchies.
2. **Reusability**: Promotes reusable components.

## Real-Life Usage
1. **Component Design**: Building reusable UI components.
2. **Frameworks**: Many frameworks use composition for extensibility.

## Pros
- **Flexibility**: Supports dynamic behavior.
- **Reusability**: Reduces code duplication.

## Cons
- **Complexity**: Can lead to complex object structures.
- **Debugging**: Requires careful handling of composed components.

## Conclusion
Composition over inheritance is a powerful design principle that promotes flexibility and reusability. By understanding how it works, developers can build more maintainable and scalable systems.
