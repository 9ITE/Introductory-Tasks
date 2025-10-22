# Modern CSS Features

This document covers some of the most powerful and trending CSS features every front-end developer should know in 2025 — complete with short explanations and working code snippets.

---

## 1. Container Queries

**What it is:**  
Container Queries let elements style themselves based on the **size of their parent container**, not the entire viewport.  
This makes components fully **context-aware** and reusable across different layouts.

**Example:**

```html
<div class="card">
  <h2>Responsive Card</h2>
  <p>Text adapts to container width!</p>
</div>

<style>
  .card {
    container-type: inline-size; /* Enables container-based styling */
    border: 1px solid #ccc;
    padding: 1rem;
    width: 300px;
  }

  /* Apply styles when container width ≥ 500px */
  @container (min-width: 500px) {
    .card {
      background: lightblue;
      font-size: 1.2rem;
    }
  }
</style>
```

## 2. Subgrid

**What it is:**  
The **subgrid** value allows a nested grid to inherit the column and/or row definitions from its parent grid.
Perfect for keeping consistent alignment across complex layouts.

**Example:**

```html
<div class="parent with-subgrid">
  <header>Header</header>
  <section class="content">
    <article>Article 1</article>
    <article>Article 2</article>
  </section>
</div>

<style>
  .parent.with-subgrid {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 10px;
  }

  .content {
    display: grid;
    grid-template-columns: subgrid; /* inherits columns */
    grid-column: 1 / -1; /* span full width of parent grid */
    gap: 10px;
  }

  .parent,
  .content,
  article,
  header {
    border: 1px solid #ccc;
    padding: 10px;
  }
</style>
```

## 3. Native CSS Nesting

**What it is:**  
Native nesting allows you to nest selectors directly inside one another in pure CSS — similar to what preprocessors like SCSS offered, but natively supported.

**Example:**

```html
<style>
  .card {
    padding: 1rem;
    border-radius: 8px;
    background: #fafafa;

    &:hover {
      background: #e0f7fa;
    }

    h2 {
      color: #00796b;
    }

    p {
      font-size: 0.9rem;
    }
  }
</style>
```

## 4. Fluid Typography with _clamp()_

**What it is:**  
The **clamp()** function lets you define values that scale smoothly between a minimum, preferred, and maximum size.
Great for responsive typography and spacing.

**Example:**

```html
<h1>Responsive Heading</h1>

<style>
  h1 {
    font-size: clamp(1.5rem, 5vw, 3rem);
  }
</style>
```

## 5. Anchor Positioning

**What it is:**  
Anchor positioning lets you position one element relative to another, without complex JavaScript or manual positioning.
Useful for tooltips, popovers, dropdowns, and modals.

**Example:**

```html
<button id="anchor">Hover me</button>
<div id="tooltip">This is a tooltip</div>

<style>
  #anchor {
    anchor-name: --btn;
  }

  #tooltip {
    position: absolute;
    position-anchor: --btn; /* Link to the anchor element */
    top: anchor(bottom);
    left: anchor(center);
    background: #333;
    color: #fff;
    padding: 5px 10px;
    border-radius: 4px;
  }
</style>
```
