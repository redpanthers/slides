---
layout: slide
title: Meteor JS
description:
theme: black
transition: slide
permalink: /meteor-framework
author: Sibin Xavier  
post_thumbnail: /slides/images/meteor-js.jpg
profile_image: /slides/profiles/sibin.jpg
---
<section data-markdown>
### Meteor Javascript Framework
</section>
<section>
	<h4>Sibin Xavier</h4>
	<p>
		Frontend Developer
	</p>
</section>
<section data-markdown>
### Frameworks
#### Web Frameworks
- Ruby On Rails, Laravel, Django, Zend, Yii, Symphony...
</section>
<section data-markdown>
####  Meteor JS is a complete Javascript Framework
- Use HTML,CSS, Javascript and MongoDB
</section>
<section data-markdown>
### Node JS , Mongo DB, Javascript Template engines, Javascript View Frameworks
</section>
<section data-markdown>
### Javascript Web Technologies
#### Meteor and MEAN ( MonogoDB Express Angular NodeJS)
</section>
<section data-markdown>
### Node JS
- Server side Javascript
- Originated from Chrome's Webkit engine
</section>
<section data-markdown>
### Mongo DB
- No SQL Database
- Stores as Object
- No Columns and Rows
</section>
<section data-markdown>
### Javascript Template Engines
- React JS, Handlebar , Blaze
</section>

<section data-markdown>
#### Meteor
- Cross Platform application - Windows, Linux and Mac
- Executable meteor application available on Windows

</section>
<section data-markdown>
#### Meteor command
##### Basic
> Meteor

- `create`, `run`

##### Install packages
> Meteor

- `add`, `remove`, `update`
</section>
<section data-markdown>
#### Create Application

>
`meteor create app-name`

</section>

<section data-markdown>
#### Server and Client side codes
##### Client
```
if(Meteor.isClient){
	// work only in client side web browser or mobile devices
}
```
##### Server
```
if(Meteor.isServer){
	// work only in server, like PHP, Ruby
}
```

</section>
<section data-markdown>
#### Ease of Use
###### Can use folder structure
- client - html,css, subscribe, calles
- server - methods, publish, restirction , collection
- public - images,fonts
- lib - common collection
- private  - secure contents, can asses using `Asset`
</section>

<section data-markdown>
#### Routes/ Routing
- Iron Router
- Flow Router
</section>

<section data-markdown>
#### Flow Router

`meteor add kadira:flow-router`

</section>

<section data-markdown>
#### Flow Router Config

``` javascript
FlowRouter.route("/blog/:cat/:id", {
    name: "blogPostRoute",
		subscriptions: function() {

    },
		triggersEnter: [localeCheck],
		triggersLeave: [localeCheck],
    action: function(queryParams,params) {
			// Render Template Logic, Subscription
			BlazeLayout.render('componentLayout', {content: 'login'});
    }
})
```

```
"/blog/meteor/abc?show=yes&color=black"
```

</section>
<section data-markdown>
#### Flow Router properties, helpers
- FlowRouter.go('/')
- FlowRouter.getParam(paramName);
- FlowRouter.getQueryParam(queryStringKey);
- FlowRouter.path(pathDef, params, queryParams)
- FlowRouter.url(pathDef, params, queryParams)
- FlowRouter.getRouteName()
</section>
<section data-markdown>
#### Flow Router Contd..
```
FlowRouter.notFound = {
		// Subscriptions registered here don't have Fast Render support.
		subscriptions: function() {

		},
		action: function() {

		}
};
```
</section>
<section data-markdown>
#### Flow Router helper for Template
- subsReady
- isSubReady (deprecated)
- pathFor
- urlFor
- param
- queryParam
- currentRouteName

```
<a href="{{pathFor 'routeName' params=params query params}}"

id=3 name="John Doe"
```
</section>
<section data-markdown>
#### Template
- Blaze Template
- Reusable Components
```
<template name="templateName">
	// html codes
</template>
```
</section>
<section data-markdown>
#### Temaplete Helpers
```
{{#if booleanValue}}

{{ else}}

{{/if}
```

```
{{#each array|object }}
	- this.objectProperties
	- @index
{{/each}}
```
</section>
<section data-markdown>
#### Meteor Template Helpers

```
Template.templateName.helpers({
		teams: function(){
			return array
		}
})
```
```
{{#each teams}


{{/each}}
```

</section>

<section data-markdown>
#### Meteor Template Events
```
Template.templateName.events({
	'click selector': function(){

	},
	'submit form selector': function(){

	}

})

```
</section>
<section data-markdown>
#### Meteor Template Events
```
Template.templateName.onCreated
Template.templateName.onRendered
Template.templateName.onDestroyed

```
</section>

<section data-markdown>
#### Mongo
```
Task = new Meteor.Collection('tasks')

```
</section>
<section data-markdown>
#### Mongo CRUD
- Task.insert()
- Task.update(id,{updatedData})
- Task.remove({})
- Task.remove({_id:id})
</section>
<section data-markdown>
#### Mongo Read
- Task.find({}).fetch() -> array
- Task.find({selector},{options})
</section>
<section data-markdown>
#### Mongo Read Selector

- {_id: id, name:name}
</section>
<section data-markdown>
#### Mongo Read Options
- limit
- skip (Meteor)
- sort
</section>

<section data-markdown>
#### Authetication

##### Meteor Account packages
- Username/Password, Facebook, Twitter

</section>
<section data-markdown>
#### Roles

##### Meteor Roles Packages

</section>
<section data-markdown>
#### Extend/ Improve meteor Applications
- Use Pckages
- Use alternate Template Engines
</section>
<section data-markdown>
#### Thanks
</section>
<section data-markdown>
### Reference
* [Meteor](https://www.meteor.com/)
* [Iron Router](https://github.com/iron-meteor/iron-router)
* [Flow Router](https://github.com/kadirahq/flow-router)
* [Blaze Layout](https://github.com/kadirahq/blaze-layout)
* [Flow Router Helpers](https://github.com/arillo/meteor-flow-router-helpers)
</section>
