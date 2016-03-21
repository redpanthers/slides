---
layout: slide
title: Snap SVG
description:
theme: black
transition: slide
permalink: /snap-svg-javascript-svg-plugin
author: Sibin Xavier
post_thumbnail: /slides/images/snap-svg.jpg
profile_image: /slides/profiles/sibin.jpg
---

<section data-markdown>
### Snap SVG
</section>

<section data-markdown>
  <h4>Sibin Xavier</h4>
  <p>
    Frontend Developer
  </p>
</section>
<section data-markdown>
  ### SVG - Scalable Vector Graphics
  * SVG stands for Scalable Vector Graphics
  * SVG is used to define vector-based graphics for the Web
  * SVG defines the graphics in XML format
  * SVG graphics do NOT lose any quality if they are zoomed or resized
Every element and every attribute in SVG files can be animated
  * SVG is a W3C recommendation
  * SVG integrates with other W3C standards such as the DOM and XSL
</section>
<section data-markdown>
  ### SVG is a opensource project from W3C
  - Currently alsmost every browser supports SVG
  - Many well developed plugins available to create SVG Objects
  - Google index SVG elements in search results
</section>
<section data-markdown>
  ### 14 Functional areas
  - Paths, Basic Shapes, Text, Painting, Color, Gradients and patterns
  - Clipping, masking and compositing, Filter effects
  - Interactivity, Linking, Scripting, Animation
  - Fonts, Metadata
</section>
<section>
  <h3> Typical SVG Element</h3>
  <pre><code>
  <svg xmlns="http://www.w3.org/2000/svg" version="1.1">
    <rect x="25" y="25" width="200" height="200" fill="lime"
    stroke-width="4" stroke="pink" />
    <circle cx="125" cy="125" r="75" fill="orange" />
    <polyline points="50,150 50,200 200,200 200,100" stroke="red"
    stroke-width="4" fill="none" />
    <line x1="50" y1="50" x2="200" y2="200" stroke="blue" stroke-width="4" />
  </svg>
  </code></pre>
</section>
<section data-markdown>
  ## Why Snap SVG
  - Snap.svg is a brand new JavaScript library for working with SVG
  - Snap provides web developers with a clean, streamlined, intuitive, and powerful API for animating and manipulating both existing SVG content, and SVG content generated with Snap.
  -  Snap was written entirely from scratch by the author of Raphaël (Dmitry Baranovskiy), and is designed specifically for modern browsers (IE9 and up, Safari, Chrome, Firefox, and Opera)
  - Use advantages of modern browser features (masking, clipping, patterns, full gradients, groups, and more)
</section>
<section>
  <h3> Create a Snap JS Object </h3>
  <pre><code>
    var s = Snap("#svg");
  </code></pre>
</section>
<section>
  <h3>Simple Snap JS Element </h3>
  <pre><code>
  var s = Snap("#svg");
  // Lets create big circle in the middle:
  var bigCircle = s.circle(150, 150, 100);
  </code></pre>
</section>
<section>
  <h3>Snap SVG Elements</h3>
  <ul>
    <li> Rectagle, Circle, Paths, Line </li>
  </ul>
</section>
<section>
  <h3> Set Propertries for Snap SVG </h3>
  <pre>
  <code>
    var s = Snap("#svg");
    // Lets create big circle in the middle:
    var bigCircle = s.circle(150, 150, 100);
    // By default its black, lets change its attributes
    bigCircle.attr({
        fill: "#bada55",
        stroke: "#000",
        strokeWidth: 5
    });
  </code>
  </pre>

</section>
<section>
<h3>Create Multiple Elements </h3>
<pre>
<code>
  var s = Snap("#svg");
  var bigCircle = s.circle(150, 150, 100);
  bigCircle.attr({
    fill: "#bada55",
    stroke: "#000",
    strokeWidth: 5
  });
  var smallCircle = s.circle(100, 150, 70);
</code>
</pre>
</section>
<section data-markdown>
- We use cordinates inside Snap Objects
- We use X,Y properties to set position
- For Polygun, Circle we have extra values
</section>

<section>
<h3>Group SVG Elements</h3>
<pre><code>
  var discs = s.group(smallCircle, s.circle(200, 150, 70));
</code></pre>
<pre><code>
  var c1 = paper.circle(),
  c2 = paper.rect(),
  g = paper.g();
  g.add(c2, c1);
</code></pre>
</section>
<section>
<h3> Group continue ....</h3>
<pre><code>
  var c1 = paper.circle(),
  c2 = paper.rect(),
  g = paper.g(c2, c1);
</code></pre>
Using Groups we can set properties for all elements inside group
</section>

<section>
<h3> Snap SVG Transformation </h3>
 groupHouse.transform("s2, 50, 200")
<pre><code>

</code></pre>

</section>

<section>
<h3> Snap SVG Animation </h3>

<pre><code>
groupHouse.animate({
    transform:'s1.2,-400,-400',
    fill:'#e51c71'
  },2000,mina.easeinout, function(){
    // callback
    groupHouse.animate({
      transform:'s1,0,0',
      fill:'#e57f1c'
    },1000)
  });
</code></pre>

</section>
<section>
<h3>Snap SVG Events</h3>
<pre><code>
treeBranches.click(function(){
alert("Hi! Tree Branch")
})

groupHouse.mouseover(function(){
alert("Moving on House")
})
</code></pre>
</section>
<section>
<h3>Snap SVG Event Handlers</h3>
<pre><code>
click, unclick, dbclick, mouseover, unmouseover, mouseup
</code></pre>
</section>

<section>
  <h3> Load External SVG Elements </h3>
  <pre><code>
  var s = Snap('#svg-external');
  // Lets create big circle in the middle:
  Snap.load('/images/mascot.svg', function(element){
  console.log("loaded")
  s.append(element)
  })
  </code></pre>
</section>

<section>
<h3>Snap SVG Ajax</h3>
<pre><code>
Snap.ajax(
      '/page-snap-ajax.json',
      function(data){
        console.log(JSON.parse(data.response))
      }
    )
</code></pre>

</section>
<section data-markdown>
### Reference
* [Snap SVG](http://snapsvg.io/)
</section>
