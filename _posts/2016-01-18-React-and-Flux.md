---
layout: slide
title: React and Flux
description: React is a popular javascript view library, flux is supporting application architecfture to build web and native application
theme: black
transition: slide
permalink: /web-with-react-and-flux/
author: Sibin Xavier
post_thumbnail: /slides/images/react-flux.jpg
profile_image: /slides/profiles/sibin.jpg
---
<section data-markdown>
 React and Flux
</section>
<section>
	<h4>Sibin Xavier</h4>
	<p>
		Frontend Developer
	</p>
</section>
<section>
	What is React, Why it is different
</section>
<section>
	React is a Javascript View Library, It can used with other Javascript frameworks
</section>
<section >
	<h3>It is not a different, but it has some unique features</h3>


  <ul>
    <li>Virtual DOM</li>
    <li>Fast render  </li>
    <li>Reusable components</li>
    <li>Uni directional data flow</li>
  </ul>


</section>
<section data-markdown>
  ### Virtual Dom
  `Virtual-dom` is a collection of modules designed to provide a declarative way of representing the DOM for your app.
  So instead of updating the DOM when your application state changes, you simply create a `virtual tree` or `VTree`, which looks like the DOM state that you want.
  `virtual-dom` will then figure out how to make the DOM look like this efficiently without recreating all of the DOM nodes.
</section>
<section data-markdown>
###SHow Codes
```
React Code
```
</section>

<section data-markdown>
#### React Components has 3 properties
- State
- Props
- Refs
</section>
<section data-markdown>
#### State
- state of a components
</section>

<section data-markdown>

 ES5
-----
```javascript
getInitialState: function(){
  retrun (
    value: 1
  )
}
```

ES6
-----
```javascript
constructor(){
  this.state = {
    value: 1
  }
}
```
> get value:
```javascript
var value = this.state.value
```
> update value:
```javascript
this.setState({
  value: 2
})
```

</section>

<section data-markdown>
#### Props

- From Parent to Child
</section>

<section data-markdown>
#### Refs

##### Get data from Component

`<input type=/'text/' ref=/'name/' name=/'name/'>`


`var name = this.refs.name`

</section>

<section data-markdown>
#### Life Cycle

- getInitialState = constructor
- componentWillMount
- ComponentDidMount
- componentWillReceiveProps
- shouldComponentUpdate
- ComponentWillUpdate
- ComponentDidUpdate
- componentWillUnmount
</section>

<section data-markdown>
#### More Properties?

Ans: Yes. Prop validation
- You can specify state variable ( string, number, functions) with propType

>
`
propTypes: {
    // You can declare that a prop is a specific JS primitive. By default, these
    // are all optional.
    optionalArray: React.PropTypes.array,
    optionalBool: React.PropTypes.bool,
    optionalFunc: React.PropTypes.func,
  }
`

</section>

<section data-markdown>
#### How to get Value from Components
- Using different javascript events
##### React and Native Javascript Events ?
- onCLick , onHover, onMouseOver
- onFocus, onKeyUp
- Support all javascript events


```
input className='form-control' onClick={this.state.clickEvent}/
```
```javascript
clickEvent: function(){// You can call Stores or Action or anyother ajax calls}
```

</section>
<section data-markdown>
### Basic information about React, Lets move to Flux

</section>

<section data-markdown>
### Why Flux
***
Flux is an Application Architecture but it is not an MVC, Flux used to build scalable web applications with React and Flux
#### Flux

Action -> Dispatcher --> Store --> View
( Then View -> Action via events/state change)
![Flux](https://facebook.github.io/flux/img/flux-simple-f8-diagram-with-client-action-1300w.png)
</section>

<section data-markdown>
![Flux Architecture](https://facebook.github.io/flux/img/flux-simple-f8-diagram-explained-1300w.png)
</section>

<section data-markdown>
#### Action
- as like its name
We call/dispatch dispatcher with certain action type, in store dispatch invoke registered action

</section>
<section data-markdown>
#### Dispatcher
- Center Hub, Like control center in Airport
- APIS ( register, unresgister, dispatch, waitFor)
- More Information [Dispatcher](https://facebook.github.io/flux/docs/dispatcher.html)
</section>
<section data-markdown>
#### Store
- Application state and Logic
</section>

<section data-markdown>
##### More informations about Action, Dispatcher and Store

[React and Flux Doc](http://facebook.github.io/react/blog/2014/07/30/flux-actions-and-the-dispatcher.html)
</section>

<section data-markdown>
#### Example Applications
[React and Flux Examples](https://github.com/facebook/flux/tree/master/examples)
</section>

<section data-markdown>
##### React and Flux continues...

Next React Router
</section>
<section data-markdown>
#### Thanks
</section>
<section data-markdown>
##### Reference

- [React docs](https://facebook.github.io/react/index.html)
- [Flux docs](https://facebook.github.io/flux/)
- React and Flux Examples by Facebook(https://github.com/facebook/flux/tree/master/examples)
- React and FLux ( Lynda, Tutplus, Pluralsight)
- [Videoreels](https://bitbucket.org/sibinx7/newreels)

</section>
