# CSS calc() Unexpected Behavior with Percentages

This repository demonstrates a common issue encountered when using the `calc()` function in CSS with percentages.  Specifically, the calculated width isn't always what you expect when subtracting pixels from a percentage.

## The Problem

The `calc()` function is powerful for dynamic calculations, but it can behave unexpectedly when mixing units. For instance, the following CSS might not render as intended:

```css
/* bug.css */
div {
  width: calc(50% - 10px);
}
```

In some cases, the browser might not accurately calculate the `10px` subtraction from the percentage, leading to incorrect rendering.

## The Solution

The best approach often involves avoiding direct subtraction of pixels from percentages inside `calc()`. Instead, consider using a container element with a defined width to determine the percentage calculation more reliably.

```css
/* bugSolution.css */
.container {
  width: 500px; /* Or any fixed width */
}

div {
  width: calc(50% - 10px);
}
```

This separation allows for a clearer, predictable outcome. Alternatively, re-evaluate your design and adjust to use either only percentage or pixels for the calculation.