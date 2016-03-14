---
layout: slide
title: Polymer JS
description:
theme: black
transition: slide
permalink: /polymer-js
author: Sibin Xavier
post_thumbnail: /slides/images/polymer-js.jpg 
profile_image: /slides/profiles/sibin.jpg
---
<section data-markdown>
## Polymer JS
</section>
<section>
  <h4>Sibin Xavier</h4>
  <p>
    Frontend Developer
  </p>
</section>
<section data-markdown>
### What is Polymer JS
The Polymer library is designed to make it easier and faster for developers to create great,
reusable components for the modern web.
</section>

<section data-markdown>
### HTML and HTML 5

- Form , Inputs , Paragraph
- Video , Canvas , Audio  - HTML 5

These Elements have it's own apis, form , input have different type of javascript apis

</section>

<section data-markdown>
## Complex website need more complex elements

- Like Sidebar, Navbar, Chat Windows
- Developers build their own solutions, but many features are common

### Reusable Components
With custom elements, you can extend the vocabulary of HTML with your own elements.
Elements that provide sophisticated UI.
</section>

<section data-markdown>
## Polymer JS

It is a collection of web components, We can build custom components which uses
Shady DOM, faster than normal DOM and lighter
</section>


<section data-markdown>
### Shadow DOM

- Shadow DOM provides encapsulation
for the JavaScript, CSS, and templating in a Web Component.
- Shadow DOM makes it so these things remain separate
from the DOM of the main document.
</section>
<section data-markdown>
### Tree-scoping

- Tree-scoping is the ability to take a DOM subtree and hide it
from the main document scope
Jquery

```html
<x-fade>
  <div>
    <img src="cool.jpg">
  </div>
  <canvas></canvas>
</x-fade>
```

Shadown DOM

```html
<x-fade>
  <img src="cool.png">
</x-fade>
```
</section>

<section data-markdown>
## With Tree Scoping
-Details of the implementation are hidden.
-Queries over the document will not see the canvas or the div.
-The new nodes are not affected by stylesheets, because they are not in the document scope.
-The img node will not lose styling, because it never moves.
-The developer can add a new img or replace the old one, it’s just a regular child of x-fade

</section>

<section data-markdown>
### Shadow DOM Real Picture
```html
<x-fade>
  <img src="cool.png">
  #shadow-root
    <div>
      <content select="img">
    </div>
    <canvas></canvas>
</x-fade>
```
</section>

<section data-markdown>
### Why Shady DOM

- Shadow DOM is not developed as Standard, Not Common in All browser
- Lots of code required to polyfill Shadow DOM
- It’s slow to indirect all the DOM API.
- Structures like NodeList can simply not be emulated.
- There are certain accessors that cannot be overwritten (for example, window.document, window.document.body).
- The polyfill returns objects that are not actually Nodes, but Node proxies, which can be very confusing.
</section>

<section data-markdown>
### Shady DOM
- Originated from idea of Shadow DOM
- Shady DOM and Shadow DOM are compatible
- Once Shadow DOM is common, Shady DOM use its features
- 'Examine it using the shady DOM API' to see Shadow DOM
-
```
var arrayOfNodes = Polymer.dom(x-fade).children;
```
</section>

<section data-markdown>
## Polymer Elements
- Iron Elements
- Paper Elements
- Google Web Components
- Gold Elements
- Neon Elements
- Platinum Elements
- Molecules
</section>

<section data-markdown>
## Polymer JS Events
  - Support all Javascript events
</section>

<section data-markdown>
## Polymer Styles
- Isolated styles for elements
</section>

<section data-markdown>
## Data Binding  - Syntax
- One Way Bind [[]]
- Two way binding {{}}
</section>
<section data-markdown>
## Data Binding - Helper functions
### DOM-REPEAT

```html
<template is="dom-repeat" items="{{employees}}">
  <div># <span>{{index}}</span></div>
  <div>First name: <span>{{item.first}}</span></div>
  <div>Last name: <span>{{item.last}}</span></div>
</template>
```
</section>

<section data-markdown>
## Data binding - Helper functions
### DOM-IF

```html
<template is="dom-if" if="{{user.isAdmin}}">
  Only admins will see this.
  <div>{{user.secretAdminStuff}}</div>
</template>

```
</section>
<section data-markdown>
### Reference

* [PolymerJS](https://www.polymer-project.org/)
* [Shadow && Shady DOM](http://glazkov.com/2011/01/14/what-the-heck-is-shadow-dom/)
</section>
