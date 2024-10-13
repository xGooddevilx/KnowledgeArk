# Use Intention-Revealing Names

Remember that cookie box that always seems to contain threads and needles? If it doesn't, something feels wrong, right? Naming things in code can feel the same way. If your variables, functions, or classes have unclear or misleading names, it’s like opening that cookie box expecting sewing supplies🧵 but finding cookies🍪 instead.

Naming **variables**, **functions**, **classes**, **parameters**, and everything else in your code is one of the most important things in programming. It’s not just about what names you _can_ use—it’s about using names that **make sense**. Just like you wouldn’t put a label on a box that doesn’t describe its contents, your code should label things correctly.

### Why Is Naming Important?

Imagine you have a toolbox for your gaming equipment, and you call it `G`. Then, your brother labels his gym equipment box as `G` too. Now, when you ask for `G`, neither of you knows which box you’re talking about! This is exactly the problem you’ll run into if you give your variables or functions generic, meaningless names in your code.

In programming, your names should be:

- **Meaningful**: Tell what the item is and why it exists.
- **Clear**: Explain what it does or holds.
- **Consistent**: Avoid confusion by using a logical naming system.

Let’s take a look at a bad naming example and how it can be improved:

### Bad Example

```javascript
function calc(a, b) {
	return a * b;
}

const x = 5;
const y = 20;
const z = calc(x, y);
console.log(z);
```

Here, `calc()`, `a`, `b`, `x`, `y`, and `z` are not meaningful names. The function `calc()` doesn’t tell us what it’s calculating, and the variables `x`, `y`, and `z` could mean anything. After a few months (or even days), it will be difficult to remember what this code does.

### Good Example

```javascript
function calculateTotalPrice(quantity, pricePerItem) {
	return quantity * pricePerItem;
}

const numberOfItems = 5;
const priceOfEachItem = 20;
const totalPrice = calculateTotalPrice(numberOfItems, priceOfEachItem);
console.log(totalPrice);
```

This version of the code is much clearer:

- **Function name**: `calculateTotalPrice()` tells you exactly what the function does.
- **Parameter names**: `quantity` and `pricePerItem` describe what is being passed into the function.
- **Variable names**: `numberOfItems`, `priceOfEachItem`, and `totalPrice` make it obvious what the values represent.

Now, if you come back to this code in the future, it’s immediately clear that the function calculates the total price of a number of items based on their price per unit.

### The Key Takeaway

Your code should be like a story that is easy to follow. When you use **intention-revealing names**, you’re making your code more readable, maintainable, and understandable for both yourself and others who might work with it. If you can look at a function or variable name and immediately understand its purpose, you're writing clean code.

So, next time you’re naming something, don’t just call it `G` or `calc()`. Choose names that truly represent what the code is doing. You’ll save yourself (and others) from a lot of confusion down the line.
