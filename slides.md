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

notes:

Check 0-start folder
The problem with css is its unpredictability
1. Why can't i put any margins around this link
  - "a" tag is an inline element, so you can’t put margin top and bottom
2. Specificity  (View button in final mob demo, change view button to blanchedalmond colour)
  - Previously, there is a view-button class that wasn't removed
  - Add class to view button
  - Put style near card-controls, because seems logical
  - Refresh page, find that it doesn't work
  - Open dev tools, find out what’s wrong, remove class
  - Find that there was a previous style there
  - Other dev: Add inline style blanchedalmond to last button
  - Now have to change back to white
  - So now change .view-button class to white
  - Find that one colour still hasn't changed
3. Oh man now that blue button needs to change to a red button
  - naming classes .blue-button or .red-button is not good

The aim  of this superfriday is to make CSS less like the gif


---

<img src="images/confused.gif" alt="confused dogs" width="600">

---

<img src="images/genius.gif" alt="genius dog" width="600">

---

## but really...
> used to style and layout web pages &mdash; for example, to alter the font, colour, size and spacing of your content, split it into multiple columns, or add animations and other decorative features <br /> &mdash; MDN web docs


notes:
show amazing things you can do with CSS
https://blog.codepen.io/2018/09/05/the-dogs-of-codepen/
https://colorlib.com/wp/css-layouts/

---

## connecting html to css

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- the document's character encoding -->
    <meta charset="utf-8">
    <title>CSS Fundamentals</title>
    <!-- 
      linking external resources to the document 
      eg. a stylesheet 
    -->
    <link href="style.css" rel="stylesheet">
  </head>
  <body>
    <!-- contents displayed on the web page -->
  </body>
</html>
```

notes:

- let's start with a way we can connect our styles with our html document

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

## type/element selector
matches elements by the name of the node

<p style="text-align:left;">html</p>

```html
<p>Hello world!</p>
```

<p style="text-align:left;">css</p>

```css
p {
  color: red;
}
```

---

## class selector
selects all elements that have the given class attribute

<p style="text-align:left;">html</p>

```html
<p class="greeting">Hello world!</p>
```

<p style="text-align:left;">css</p>

```css
.greeting {
  color: red;
}
```

---

## id selector
- selects an element with the id attribute
- there should only be one

<p style="text-align:left;">html</p>

```html
<p id="greeting">Hello world!</p>
```

<p style="text-align:left;">css</p>

```css
#greeting {
  color: red;
}
```

---

## pseudo selector
selects an element with a given state

<p style="text-align:left;">html</p>

```html
<a href="#">go somewhere</a>
```

<p style="text-align:left;">css</p>

```css
a:hover {
  color: red;
}
```

notes:

- common example changing the hover style of a link

---

<p style="text-align:left;">html</p>

```html
<p>First paragraph</p>
<p>Second paragraph</p>
<p>Third paragraph</p>
```

<p style="text-align:left;">css</p>

```css
p:first-of-type {
  color: red;
}
```

notes:

- selects the first sibling "p" element

---

## some common combinators

- descendant combinator
  - https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator

- child combinator
  - https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator

---

## CHALLENGE

demo/1-css-fundamentals folder

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

## !important = evil

<img src="images/evil.gif" alt="evil" width="600">

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

- see 3-box-model demo2.html
- mention html elements have their own initial display type

---

## CHALLENGE

demo/3-box-model/demo2.html

- what happens when you increase the width of p?
- what happens when you add a margin of 20px to all of the highlighted words? 

---

## collapsing margin

> The top and bottom margins of blocks are sometimes combined (collapsed) into a single margin whose size is the largest of the individual margins (or just one of them, if they are equal) <br /> &mdash; MDN web docs

notes: 

- example with the h1 and p tag margins collapsing in the demo
- it's probably better to use margin top only in some cases

---

<img src="images/wat.gif" alt="wat" width="600">

---

## position property

> sets how an element is positioned in a document. The top, right, bottom, and left properties determine the final location of positioned elements <br /> &mdash; MDN web docs

---

## position: static

the default position of elements

notes: 

- go to 3-box-model demo 3
- show box 1 and look at the computed position in the dev tools

---

## position: relative

allows positioning of elements with an offset

notes:

- show box 5 and the offset from the left of the page

---

## position: absolute

- allows positioning of elements with an offset
- specifying offset is relative to the edges of the containing block

notes:

- show box 2 and 3, with 2 having position:relative
- show box 4 with no ancestor, so it's attached to the root element

---

## CHALLENGE

demo/3-box-model/challenge.html

---

## common use case: dropdown

https://css-tricks.com/solved-with-css-dropdown-menus/

notes:

- the li element is positioned relative
- it has another ul, which contains the dropdown
- the dropdown ul is positioned absolute

---

## responsive design

> For Web developers, it is now fairly common to be called upon to create a Web site or app that changes its user interface depending on the browser or device accessing the site to provide an optimized experience. <br /> &mdash; MDN web docs

---

<img src="images/responsive.gif" alt="responsive" width="600">

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

- in 4-responsive-design, start.html changes colour according to size
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

https://developers.google.com/web/fundamentals/design-and-ux/responsive/

---

## challenge: align a box vertically in a box

<img src="images/css-verticalalign.jpg" alt="css vertical align comic">

notes:

saved by flexbox

---

## flexbox
- the children of a flex container can be laid out in any direction, and can "flex" their sizes, either growing to fill unused space or shrinking to avoid overflowing the parent
- Both horizontal and vertical alignment of the children can be easily manipulated <br /> &mdash; MDN web docs

notes:

- now easy to align things vertically
- EXAMPLE https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout

---

## commonly used flexbox properties

- display: flex to a parent container
- vertical alignment
  - https://cssreference.io/flexbox/#align-items
- horizontal alignment
  - https://cssreference.io/flexbox/#justify-content

---

## CHALLENGE

demo/4-responsive-design/start.html

align the numbers to the centre of the box

---

## let's combine this with media queries

notes:

- there are several ways to make the layout responsive
- we will be using flexbox, although it is typically best used for one dimension layouting
- to achieve final.html in 4-responsive-design
- let's start without the border first
- at min-width: 576px, we want 2 boxes in a row

---

## specifying the number of boxes per line...

1. apply display: flex to the parent
2. apply flex-basis: 50% (for 2 items) to the children to set the initial size of the flex items
3. apply flex-wrap: wrap to allow them to occupy multiple lines when the space occupied gets too big

notes:

- not using flex-wrap will force the boxes to overflow to the right

---

## adding gutter

1. apply negative margin-top to shift parent up
2. apply negative margin-left to shift parent to the left
3. then applying positive margin-top and margin-left to the children will only create the gap in the middle
4. finally, flex: 0 0 calc(50% - 10px); to reduce the size of the flex items by 10px


---

<img src="images/wat.gif" alt="wat" width="600">

---

## flexbox aside

- best used for one dimension layout
- explore css grid for two dimensional layout
- make sure it is supported by the browsers
https://caniuse.com/#feat=css-grid

---

## let's apply what we've learnt!

- clone: https://github.com/kksy/css-superfriday
- go to <span style="color:#9fd65c;">/demo/mob-coding</span> folder and edit <span style="color:#9fd65c;">start.html</span> and <span style="color:#9fd65c;">start.css</span>


---

## maintainability

notes:
- a lot of these can be subjective, but here are some of the things that can help in making css more maintainable

---

## semantic naming

```html
<!-- non semantic -->
<div class="red pull-left pb3">
<div class="grid row">
<div class="col-xs-4">

<!-- semantic -->
<div class="basket">
<div class="product">
<div class="searchResults">
```

---

## why semantic naming

- more readable, easier to find
- easier to style elements without having to define multiple classes
- avoid conflicting styling
- easier to use with media queries

---

## conventions

eg. BEM
http://getbem.com/naming/

notes:

- there are different naming conventions with advantages and disadvantages
- for the purpose of this presentation, we will explore BEM

---

## <span style="color:#9fd65c;">B</span>EM: <span style="color:#9fd65c;">block</span>

encapsulates a standalone entity that is meaningful on its own

```html
<div class="block">...</div>
```

---

## B<span style="color:#9fd65c;">E</span>M: <span style="color:#9fd65c;">element</span>

- parts of a block and have no standalone meaning
- any element is semantically tied to its block

```html
<div class="block">
	  ...
    <span class="block__elem"></span>
</div>
```

---

## BE<span style="color:#9fd65c;">M</span>: <span style="color:#9fd65c;">modifier</span>

- flags on blocks or elements
- use them to change appearance, behavior or state.

```html
<div class="block block--mod">...</div>
<div class="block block--size-big block--shadow-yes">...</div>
```

---

## BEM: example

- suppose you have block form with modifiers <span style="color:#9fd65c;">theme: "xmas"</span> and <span style="color:#9fd65c;">simple: true</span>
- with elements <span style="color:#9fd65c;">input</span> and <span style="color:#9fd65c;">submit</span>
- element <span style="color:#9fd65c;">submit</span> with its own modifier <span style="color:#9fd65c;">disabled: true</span> for not submitting form while it is not filled

---

html

```html
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

css
```css
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }

```

---

## why having conventions matter

- naming is hard
- reduces specificity issues
- new devs will have a reference point

---

## normalize

- browsers render elements differently
- reduces styling pain when supporting multiple browsers
- example: https://github.com/sindresorhus/modern-normalize

notes:

https://github.com/sindresorhus/modern-normalize/blob/master/modern-normalize.css

- removing margins in the body
- button example

---

## using css preprocessors

> a program that lets you generate CSS from the preprocessor's own unique syntax <br /> &mdash; MDN web docs

---

## example: SASS 
https://sass-lang.com/guide

---

## SASS: variables

```scss
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

---

## SASS: variables benefits

- define style guide colours
- reuse

---

## SASS: nesting

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

---

## SASS: nesting benefits

- having a visual hierarchy makes css more readable
- warning: too much nesting will be harder to maintain

---

## CSS is code too

<img src="images/marie.gif" alt="marie kondo" width="600">

---

## now let's do more practices!

---

## thanks for attending!

---

## resources

- css intro: https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS
- maintainable css: https://maintainablecss.com
- bem: http://getbem.com
- sass: http://sass-lang.com
- browser support check: https://caniuse.com/
- css visual reference: https://cssreference.io/
- centering in css: https://css-tricks.com/centering-css-complete-guide/







