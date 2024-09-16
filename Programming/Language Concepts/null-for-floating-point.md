# Accept Null for Floating Point

## What are Floating Point Numbers?

Imagine you have a ruler and you're measuring something with it. You place the ruler next to an object, and it measures exactly 4 cm. Simple, right?

Then, you start measuring other things, and wait a minute... it's not a whole number! It might be 2 and a half, or even something like 2.87.

Those numbers after the dot (`.`) are called **floating point numbers**. We call them "float" because they can be anywhere between whole numbers.

In math, we refer to these as **decimals**. Computers also use floating point numbers to handle these "in-between" values so they can measure and work with tiny parts of things, not just whole numbers!

## What is Null?

Imagine you’re working hard to earn money so you can someday visit a store and buy something special. You reach into your wallet and discover... oh no, you don’t have any money!

This is what `null` means in programming.

**Null** is like having an empty wallet. It means there’s nothing inside—no money, no card, no object, no value at all.

When a program checks a variable and finds it’s `null`, it knows that there’s no value stored in it.

### Example in JavaScript

Here's an example of how `null` is used in JavaScript:

```javascript
let myNumber = null; // The variable is explicitly set to null

console.log(myNumber); // Output: null

// Checking if the variable is null
if (myNumber === null) {
	console.log("The variable is null, which means it has no value.");
} else {
	console.log("The variable has a value.");
}
```

In this example, `myNumber` is explicitly set to `null`, indicating it has no value. The check confirms that `myNumber` is indeed `null`.

---

## Language accepts null

When a language accepts null for floating points, it means that the language allows a null value to be assigned or passed where a floating-point number (like float, double, or decimal) is expected.
