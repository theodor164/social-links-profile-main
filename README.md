# Frontend Mentor - Social links profile solution

This is a solution to the [Social links profile challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)


## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

![](./Screenshot%20from%202026-07-31%2022-57-48.png)

### Links

- Solution URL: [Add solution URL here](https://github.com/theodor164/social-links-profile-main)
- Live Site URL: [Add live site URL here](https://theodor164.github.io/social-links-profile-main/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned

#### Semantic HTML

I learned that `<nav>` should be used instead of a generic `<div>` when a group of elements is meant for navigating to other places (in my case, the social links). I also learned that `<a href="...">` is the right element for links that take the user to another page or site, while `<button>` is meant for actions that happen on the same page (like submitting a form).

```html
<nav class="buttons">
  <a class="button" href="https://github.com/...">GitHub</a>
</nav>
```

#### Box model

I learned that `box-sizing: border-box` makes `width`/`height` include the padding and border, instead of the browser adding them on top (`content-box`, the default). This was the reason my card's measurements didn't match the Figma design at first. I also learned to check for hidden default `margin` values on elements like `<p>` and `<button>`, since those can throw off measurements too.

```css
* {
  box-sizing: border-box;
}
```

#### Flexbox

I learned that `flex` is shorthand for three properties: `flex-grow`, `flex-shrink`, and `flex-basis`. In my case, `flex: 1 0 0` means the element grows to fill available space, never shrinks below its content, and starts from a basis of `0`.

#### Responsive spacing with `clamp()`

I learned to use `clamp(min, preferred, max)` so I can change the padding based on the width of the screen, without writing a separate media query. The `min` and `max` values act as safe boundaries, while the middle value (using `vw`) scales fluidly in between.

```css
.card {
  padding: clamp(24px, 5vw, 40px);
}
```

I also learned that I should use `box-sizing: border-box`, so that the padding is calculated inside the measurements of the card.

#### Letting the browser calculate height

I learned that `height: auto` lets the element's height be determined by its content, which is usually better than hardcoding a fixed height — the card only matched the design once I had filled in the real content (image, name, bio, links).


### Continued development


- **Flexbox in depth** - I understand `flex-grow`, `flex-shrink`, and `flex-basis` now, but I want more practice with real layouts (navbars, card grids) until it feels intuitive instead of something I have to reason through step by step.
- **CSS Grid** - I haven't used it yet. I want to learn it as the natural next step after Flexbox, for layouts that need rows and columns at the same time.
- **Accessibility (keyboard navigation & focus states)** - I learned that links need visible `:focus` styles for keyboard users, and that `<a>` elements without `href` aren't focusable at all. I want to go deeper into accessibility basics: focus-visible, ARIA when needed, and testing with a screen reader.
- **Responsive design beyond `clamp()`** - I want to get comfortable with traditional media queries too, so I know when to reach for `clamp()`/fluid sizing versus explicit breakpoints.
- **Git/GitHub workflow** - I mixed up my local version with the deployed GitHub Pages version while testing. I want to get more comfortable with the commit/push/deploy cycle so I always know which version I'm actually looking at.


### AI Collaboration

- **Tool used:** Claude (Claude Code), configured with a mentor-style `AGENTS.md` for this challenge.
- **How I used it:** Instead of asking for finished code, I described what I was seeing (e.g. "the card's width/height doesn't match Figma", "focus isn't working on the buttons") and worked through the cause with guided questions. Claude explained concepts (box model, flexbox shorthand, `clamp()`, semantic HTML) using analogies and asked me to reason through the answer before confirming it, rather than giving the fix directly.
- **What worked well:** The back-and-forth debugging was the most useful part - for the focus bug, instead of just telling me the answer, it asked me to test step by step (click into the page, count Tab presses) until I found out on my own that I was looking at the deployed GitHub Pages version instead of my local one, not a code problem at all. Same for the box-sizing issue - it asked guiding questions until I noticed the hidden default margins myself.
- **What didn't work as well:** A couple of times it gave me guidance based on outdated context (e.g. assuming my HTML was still empty, or that my `<div class="buttons">` still existed) instead of re-reading the current file first, which cost a bit of back-and-forth to correct.

## Author

- Frontend Mentor - [@theodor164](https://www.frontendmentor.io/profile/theodor164)


