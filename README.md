# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [https://github.com/ababaug/product-preview-card-component-main]
- Live Site URL: [https://ababaug.github.io/product-preview-card-component-main/]

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

**Note: These are just examples. Delete this note and replace the list above with your own choices**

### What I learned

Use this section to recap over some of your major learnings while working through this project. Writing these out and providing code samples of areas you want to highlight is a great way to reinforce your own knowledge.

To see how you can add code snippets, see below:

```html
<body>
  <main>
    <article class="product">
      <picture class="product__image">
        <source
          srcset="images/image-product-desktop.jpg"
          media="(min-width: 480px)"
        />
        <img src="./images/image-product-mobile.jpg" alt="mobile image" />
      </picture>
      <div class="product__content">
        <h2>Perfume</h2>
        <h1>Gabrielle Essence Eau De Parfum</h1>
        <p>
          A floral, solar and voluptuous interpretation composed by Olivier
          Polge, Perfumer-Creator for the House of CHANEL.
        </p>
        <div class="product_price">
          <small class="discount_price">$149.99</small>
          <small class="original_price">$169.99</small>
        </div>
        <button><span></span>Add to Cart</button>
      </div>
    </article>
  </main>
</body>
```

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap");

@import url("https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,100..900;1,9..144,100..900&display=swap");

:root {
  /* Colors */
  /* Primary */
  --color-very-dark-cyan: hsl(159, 37%, 11%);
  --color-dark-cyan: hsl(158, 36%, 37%);
  --color-cream: hsl(30, 38%, 92%);

  /* Neutral */
  --color-Very-dark-blue: hsl(212, 21%, 14%);
  --color-dark-grayish-blue: hsl(228, 12%, 48%);
  --color-white: hsl(0, 0%, 100%);

  /* Typography */
  --font-size-paragraph: 14px;

  /* Font family */
  --montserrat-font-family: "Montserrat", sans-serif;
  --fraunces-font-family: "Fraunces", serif;

  /* Font Weight */
  --montserrat-font-weight-500: 500;
  --montserrat-font-weight-700: 700;
  --fraunces-font-weight-700: 700;
}

/* Universal Reset Start*/
*,
*::before,
*::after {
  box-sizing: border-box;
}

* {
  margin: 0;
}

img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}

input,
button,
textarea,
select {
  font: inherit;
}

p,
h1,
h2,
h3,
h4,
h5,
h6 {
  overflow-wrap: break-word;
}

#root,
#__next {
  isolation: isolate;
}
/* Universal Reset */

body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  font-size: var(--font-size-paragraph);
  font-weight: var(--montserrat-font-weight-500);
  background-color: var(--color-cream);
  display: grid;
  place-content: center;
  min-height: 100vh;
  padding: 1em;
}

.product {
  background-color: var(--color-white);
  border: 0;
  border-radius: 0.5rem;
  overflow: hidden;
  max-width: 480px;
}

.product__content {
  margin: 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.product__content h1 {
  color: var();
  font-family: var(--fraunces-font-family);
  font-size: 1.875rem;
  font-weight: var(--fraunces-font-weight-700);
  line-height: 1;
}

.product__content h2 {
  color: var(--color-dark-cyan);
  text-transform: uppercase;
  font-size: 0.85rem;
  font-family: var(--montserrat-font-family);
  font-weight: var(--montserrat-font-weight-500);
  letter-spacing: 0.25rem;
}

.product__content p {
  color: var(--color-dark-cyan);
  font-size: 0.875rem;
  font-family: var(--montserrat-font-family);
  font-weight: var(--montserrat-font-weight-500);
}

.product_price {
  display: flex;
  gap: 1rem;
  align-items: center;
  color: var(--color-dark-cyan);
}

.discount_price {
  font-family: var(--fraunces-font-family);
  font-size: 1.5rem;
  font-weight: var(--fraunces-font-weight-700);
}

.original_price {
  text-decoration: line-through;
}

button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  font-family: var(--montserrat-font-family);
  font-weight: var(--montserrat-font-weight-700);
  font-size: 0.75rem;
  border: 0;
  color: var(--color-white);
  background-color: var(--color-dark-cyan);
  padding: 0.725em 1.5em;
  border-radius: 0.5em;
}

button span {
  display: inline-block;
  width: 1rem;
  height: 1rem;
  background-image: url("/images/icon-cart.svg");
  background-size: cover;
  background-position: center;
}

@media (min-width: 480px) {
  html {
    font-size: 15px;
  }

  .product {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  img {
    height: 100%;
  }

  .product__content {
    gap: 1.5em;
  }

  button:hover,
  button:focus {
    background-color: var(--color-very-dark-cyan);
  }
}
```

## Author

- Website - [https://www.linkedin.com/in/augustine-stephen-abah-51103090/]
- Frontend Mentor - [@ababaug](https://www.frontendmentor.io/profile/ababaug)
