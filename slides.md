# CSS Superfriday!

---

## what about it?

- CSS fundamentals
- The problem with CSS
- Some solutions
- Let's practice!

---

## css fundamentals

---

## what is css?
![css peter griffin gif](images/css-petergriffin.gif)

---

## but really...
> used to style and layout web pages &mdash; for example, to alter the font, colour, size and spacing of your content, split it into multiple columns, or add animations and other decorative features <br /> &mdash; MDN web docs


notes:
show amazing things you can do with CSS
https://blog.codepen.io/2018/09/05/the-dogs-of-codepen/
https://colorlib.com/wp/css-layouts/

---

## anatomy of a css ruleset

![css ruleset](images/css-ruleset.png)

notes:

** Show demo/1-css-fundamentals to change the colour of the paragraph

Selector

The HTML element name at the start of the rule set. It selects the element(s) to be styled (in this case, "p" elements). To style a different element, just change the selector.

Declaration

A single rule like color: red; specifying which of the element's properties you want to style.

Properties

Ways in which you can style a given HTML element. 

Property value

To the right of the property after the colon, we have the property value, which chooses one out of many possible appearances for a given property (there are many color values besides red).

&mdash; MDN web docs

---

## cascade & specificity

selectors overrule each other in this order
1. importance
2. specificity
3. source order

---

## importance
using *`!important`* keyword will take the highest priority

```css
p {
    color: red !important;
}
```

---

## specificity
> a measure of how specific a selector is &mdash; how many elements it could match <br /> &mdash; MDN web docs

---

## selectors from the highest specificity to the lowest
1. inline styles
2. id selectors (e.g. #example).
3. class selectors (e.g. .example), attributes selectors (e.g. [type="radio"]) and pseudo-classes (e.g. :hover).
4. element selectors (e.g. h1) and pseudo-elements (e.g. ::before).

notes:

** use 2-specificity to demo each type of selector

demo what happens when you use the selector with !important

---

## source order

```css
p {
    color: red;
}

/* this overrides red */
p {
    color: blue;
}
```

---

## box model

<img src="images/box-model.png" alt="box model" width="600"/>

---

the fill area gets filled by the background property

<img src="images/fill-area.png" alt="box model fill area" width="600"/>


notes:

as you can see, this includes the content area, padding and border
see 3-box-model index1.html to practice adding padding and margin

---

## types of css boxes

- defined by the display property
- inline, inline-block, block

notes:

see 3-box-model index2.html

---

## collapsing margin

> The top and bottom margins of blocks are sometimes combined (collapsed) into a single margin whose size is the largest of the individual margins (or just one of them, if they are equal) <br /> &mdash; MDN web docs

notes: 

example with the h1 and p tag margins collapsing in the demo

---

## responsive design

> For Web developers, it is now fairly common to be called upon to create a Web site or app that changes its user interface depending on the browser or device accessing the site to provide an optimized experience. <br /> &mdash; MDN web docs

notes:

example responsive websites
https://www.awwwards.com/websites/responsive-design/
https://www.thoughtworks.com/
https://www.apple.com/au/shop/buy-mac/macbook-pro


---

## building blocks of responsive design
- media queries
- viewport

---

## media queries
allows content to be rendered differently through conditions such as 
- media type (eg. screen, print)
- screen resolution
- and more...

notes:

we will only talk about device width in this presentation
https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries

---

## anatomy of a media query

```css
/* 
Bootstrap mobile first breakpoints
No media query for devices less than 576px because this is default
*/

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) { ... }

/* Medium devices (tablets, 768px and up) */
@media (min-width: 768px) { ... }

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) { ... }

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) { ... }

```

notes:

- opening the mobile view from the inspector,
- we find that this is not really optimised for mobile devices
- enter viewport meta

---

## viewport

The browser's viewport is the area of the window in which web content can be seen. This is often not the same size as the rendered page, in which case the browser provides scrollbars for the user to scroll around and access all the content. <br /> &mdash; MDN web docs

---

## viewport meta tag to the rescue

typical mobile-optimised site contains:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

notes:

width:
- The width property controls the size of the viewport.
- can be set to a specific number of pixels like width=600 or to the special value device-width, which is the width of the screen in CSS pixels at a scale of 100%

initial-scale:
- controls the zoom level when the page is first loaded

(MDN web docs)
