# CSS Selectors

## Overview

In this lesson we will do a quick review of CSS selectors from the video lecture in the prior lesson.

## What's Covered in This Lesson 

1. Review Type Selector
2. Review Class Selector
3. Review ID Selector
4. Review Compound Selector
5. Review Descendent Selector
6. Review Child
7. Review Adjacent Sibling
8. Review General Sibling
9. Review Universal
10. Review Attribute Selectors
11. Review Pseudo Selectors

## Selectors

CSS gives us a variety of ways to select different elements and style them.

#### Type

```css
p {
  color: red;
}
```

This selects an element of the specified type based directly on providing the element name.

```html
<p>Lorem ipsum</p>
```

#### Class

```css
.thick {
  font-weight: bold;
}
```

This selects an element with matching class attribute name. This selector is indicated by the preceeding `.` dot (period).

```html
<span class="thick">I'm thick</span>
```

You can apply a class name to as many elements as you like across the same page and across any pages in your website. This is a good selector for sprinkling the same style to many different elements.

You can also apply more than one class to the same element. For example, let's apply two classes to the same paragraph.

```css
.thick {
    font-weight: bold;
}

.alert {
    color: red;
}
```

To apply the two classes we simply use a space to separate their names.

```html
<p class="thick alert">Warning...</p>
```

#### ID

```css
#box {
  background: blue;
}
```

This selects an element with matching id attribute name. This selector is indicated by the preceeding `#` hashtag symbol.

```html
<div id="box">I'm a box</span>
```

A single Id name should only be applied to one element per page.

#### Compound

```css
h1, h2, #box {
  font-family: Arial, Helvetica, sans-serif;
}
```

This selects all matched elements in the compound set. This selector is indicated by a `,` comma separating the selectors of the set. Each element within the coma separated list will be styled the same.

```html
<h1>Heading</h1>
<h2>Subheading</h2>
<div id="box">I'm a box</span>
```

#### Descendent

```css
#nav li {
  background: blue;
}
```

This selects an element that is nested inside of the specified parent element. This selector is indicated by a ` ` keyboard space between the parent and the child to be selected.

```html
<ul id="nav">
  <li>child</li>
</ul>
```

#### Child

```css
#list > li {
  color: black;
}
```

This selects an element that is nested only one level deep inside of the specified parent element. It only selects direct children and not grandchildren. This selector is indicated by a `>` (greater than) symbol between the parent and the child to be selected.

```html
<ul id="list">
  <li>child</li>
  <li>child
    <ul>
      <li>grand child</li>
    </ul>
  </li>
</ul>
```

#### Adjacent Sibling

```css
h3 + p {
  color: green;
}
```

This selects an element that appears directly after the former element assuming they are both siblings (in the same level of nesting, in the same parent). This selector is indicated by a `+` plus symbol between the former sibling and the selected element that follows.

```html
<h3>Heading</h3>
<p>I'm a paragraph that is selected because I come directly after an h3.</p>
<p>I'm not selected.</p>
```

#### General Sibling 

```css
h2 ~ p {
  color: black;
}
```

This selects all elements that appear directly after the former element. This selector is indicated by a `~` tilde symbol between the former sibling and the selected element that follows it.

```html
<h2>Sub heading</h2>
<p>I'm selected because I appear after an h2.</p>
<p>I'm also selected for the same reason, in fact any paragraphs on the rest of the page after the h2 will be selected.</p>
```

#### Universal

```css
* {
  color: orange;
}
```

This selects elements where the properties specified have not been styled by any other selectors. This selector is indicated by a `*` asterisk symbol.

```html
<h5>Sub heading</h5>
```

We haven't yet specified a color style for `h5` anywhere else yet on our CSS so they will get the color orange now being covered under the universal selector.

#### Attribute

```css
img[alt="Cat"] {
  border: 1px solid black;
}
```

This selects an element with a matching attribute value. This selector is indicated by `[]` square brackets, followed by the attribute property and value of the selected element within the brackets.

```html
<img src="myimage.jpg" alt="Cat">
```

##### Other Attribute Selectors Include:

`a[href^="http"]` The `^=` carrot symbol selects elements that start with the matching value, such as `<a href="http://google.com">google</a>`.

`p[class$="dog"]` The `$=` dollar sign selects elements that end with the matching value, such as `<p class="bigbdog">...</a>`.

`img[alt*="love"]` The `*=` asterisk selects elements that have the matched characters appearing anywhere within the value, such as `<img src="myimage.jpg" alt="I love you.">`.

`p[class~="monkey"]` The `~=` tilde symbol selects elements that contain the term within a space separated value, such as `<p class="zoo monkey details">...</p>`.

`p[class|="birds"]` The `|=` pipe symbol selects elements that contain the term within a dash separated value, such as `<p class="new-birds-today">...</p>`.

#### Pseudo Class

```css
a:link {
  text-decoration: none;
}
```

This selects an element based on the unique relationship or state described in the selector. This selector is indicated by the `:` colon symbol, followed by the pseudo class that describes the element's state or positioning amongst other elements.

```html
<a href="about.html">About</a>
```

##### Other Pseudo Class Selectors Include:

`a:link` selects links in their default state before the visitor has interacted with them.

`a:visited` selects links after the user has already clicked on them and is visiting that page again.

`a:hover` selects links when the user is hovering their mouse over the link.

`a:active` selects links for only the moment when the mouse button is pressed when clicking on the link.

`p:first-child` selects elements that are the first child when appearing inside a common parent. Such as `<div><p>I'm selected</p><p>I'm not</p><p>Neither am I</p></div>`

`p:last-child` selects elements that are the last child when appearing inside a common parent. Such as `<div><p>I'm not selected</p><p>Neither am I</p><p>I'm selected</p></div>`

These are just a few psuedo selectors, but there are many additional ones you can explore in the resource links provided at the botoom of this lesson.

## Summary

- CSS provides a wide range of selectors to select different elements. Get to know them all.

## Resources

- [MDN - CSS Tutorials for Beginners](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started)
- [MDN - CSS Property Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [Tuts Plus - 30 CSS selectors to Memorize](http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048)
- [Learn More Pseudo Selectors](http://css-tricks.com/pseudo-class-selectors/)
- [CSS Diner Online Game](http://flukeout.github.io/)

<p class='util--hide'>View <a href='https://learn.co/lessons/css-selectors'>CSS Selectors</a> on Learn.co and start learning to code for free.</p>
