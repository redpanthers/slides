---
layout: slide
title: Goal Analyzer
description: A presentation on our project goalsheet_analyzer
theme: black
transition: slide
permalink: /goal-analyzer/
author: Juliat Joy & Ajay Joseph
post_thumbnail: /slides/images/api.jpg
profile_image: /slides/profiles/ajay-joseph.jpg
profile_image_2: /slides/profiles/juliat.jpg
---

<section data-markdown>
# Goalsheet Analyzer

Mar 11, 2016
</section>

<!-- Just to show that markdown and html can be mixed -->
<section>
  <h4>Hi, I am</h4>
  <h3>Ajay Joseph</h3>
  <div style="width:150%;">
    <div style="float:left; width:30%;">
      <img alt="Ajay Joseph" src="https://scontent-hkg3-1.xx.fbcdn.net/hphotos-frc3/v/t1.0-9/945390_3255807009318_1975357127_n.jpg?oh=1cbfba3bef55ba6fa91cb048a4808622&oe=5747C14D" style="float: left; width:400px; height:400px;">
    </div>
    <div style="float:right; width:70%;">
      <ul style="float: left; padding-top: 4%;">
          <li>Ruby Devoloper Trainee at Redpanthers</li>

      </ul>
    </div>
  </div>

</section>

<section>
  <h4>Hi, I am</h4>
  <h3>Juliat Joy</h3>
  <div style="width:150%;">
    <div style="float:left; width:30%;">
      <img alt="Juliat Joy" src="https://avatars2.githubusercontent.com/u/7353124?v=3&u=6eeeedc3e9ecfbf20e6dcd128ea7344ed9261f49&s=140" style="float: left; width:400px; height:400px;">
    </div>
    <div style="float:right; width:70%;">
      <ul style="float: left; padding-top: 4%;">
          <li>Ruby Devoloper Trainee at Redpanthers</li>

      </ul>
    </div>
  </div>

</section>

<section data-markdown>
### What goalsheet is?

Goalsheet is an app where we can see our goalsheets for the corresponding day, week or month. Which also helps us to know how much of our tasks are completed. Only admin can see all the goalsheets.

</section>

<section data-markdown>
### Why goalsheet?

Goalsheet helps us to see our goalsheets and goals.

</section>

<section data-markdown>
### Difficulties faced

* has_many_through
* Absence of rails view
* Curl requests
* Testing
* react and flux

</section>

<section data-markdown>
### Application design

In our project we have mainly users, goals, goalsheets and teams model.
* Where a goal can have a user and belongs to a goalsheet.
* Where a goalsheet may belong to a team or a user and has many goals.
* Where a team can have many goals and users.

</section>


<section data-markdown>
### view

We buid json view for goalsheet using jbuilder, which is handled by react and flux framework in front end.

</section>

<section data-markdown>
### Why jbuider?

It is simple and has a more approchable concept.

</section>

<section data-markdown>
### contd..

For json handling there are 3 approches they are
* Active Model Serializers(AMS)
* Rabl
* Jbuilder
</section>

<section data-markdown>
### Active Model Serializers(AMS)

* Separates the serialization concern into its own folder /app/serializers
* It comes with its own Rails generator
* It behaves more like ActiveRecord in that you can define associations in the serializer

</section>

<section data-markdown>
### Rabl

RABL's DSL is generally less favored than Jbuilder's, there can be difficulty in getting started, and in later maintenance. Jbuilder's DSL is simpler and easier to learn/use, but the general consensus appears to be that Jbuilder is easier to pick up and run with.
</section>

<section data-markdown>
### Jbuilder

* It considers JSON format construction as just another Rails view
* Builds responses in the corresponding /app/views/ directories just like we do with view templates
* It can take on many of the characteristics of a view template, like understanding what current_user is, chaining relations (@user.posts)... etc

</section>

<section data-markdown>
### Documentation of API

Well documented APIs enhance the experience for developers and have become an essential requirement for defining an API's success. Good documentation is no longer just about clarity but also improving the affordance of documents as live API experiences for developers.

</section>

<section data-markdown>
### Swagger

With the Swagger framework, the server, client and documentation team can be in synchronization simultaneously.

</section>

<section data-markdown>
### contd

As Swagger is a language-agnostic specification, with its declarative resource specification, clients can easily understand and consume services without any prior knowledge of server implementation or access to the server code.

</section>

<section data-markdown>
### Testing

</section>

<section data-markdown>
### Unit Testing

A unit is the smallest testable part of software. It usually has one or a few inputs and usually a single output. The smallest unit is a method, which may belong to a base/ super class, abstract class or derived/ child class. Unit Testing is the first level of testing and is performed prior to Integration Testing.

</section>

<section data-markdown>
### Integeration Testing

Integration tests are used to test the interaction among any number of controllers. They are generally used to test important work flows within your application.

</section>

<section data-markdown>
### Controller specs

A controller spec is an RSpec wrapper for a Rails functional test.

</section>

<section data-markdown>
### contd

It allows you to simulate a single http request in each example, and then
specify expected outcomes such as:

* rendered templates
* redirects
* instance variables assigned in the controller to be shared with the view
* cookies sent back with the response

</section>

<section data-markdown>
### contd

To specify outcomes, you can use:

* standard rspec matchers (expect(response.status).to eq(200))
* standard test/unit assertions (assert_equal 200, response.status)
* rails assertions (assert_response 200)
* rails-specific matchers:

</section>

<section data-markdown>
### Model specs

It includes all of the behavior and assertions that it provides.

</section>


<section data-markdown>
### Request specs

Request specs provide a thin wrapper around Rails' integration tests, and are
designed to drive behavior through the full stack, including routing

</section>

<section data-markdown>
### contd

With request specs, you can:

* specify a single request
* specify multiple requests across multiple controllers
* specify multiple requests across multiple sessions


</section>

<section data-markdown>
### Stubs and Mocks

Hitting the database or spinning up a UI for every test can make your test suite too slow, which either slows down productivity or encourages you to not run your tests as often

</section>

<section data-markdown>
### Stub

A stub can be told to return a specified fake value when a given method is called. If your test subject requires a companion object to provide some sort of data, you can use a stub to “stub out” that data source and return consistent fake data in your test setup.


</section>

<section data-markdown>
### Mock

A mock is similar to a spy, but the way you use it differs slightly. Rather than just capturing all method calls and letting you write assertions on them after the fact, a mock typically requires you to set up expectations beforehand. You tell it what you expect it to happen, execute the code you’re testing, and then verify that the correct behavior happened.

</section>

<section data-markdown>
### Shared examples

* Shared examples describe behaviour of classes or modules.
* Shared examples make testing compositions of objects much easier. They allow us to execute the same group of expectations against several classes.
* By Convention we place the files containing shared examples in spec/support/
and require files in that directory from spec/spec_helper.rb

</section>

<section data-markdown>
### Why react?

React is faster and write-less-do-more than angular. Being faster makes it preferable for mobile clients. It beats angular when memory is limited.

</section>

<section data-markdown>
### contd

React uses VDOM(virtual DOM) which results in much better performance than angular rendering views. React is used to create user interfaces, one can use react as V in Angular. React performs DOM modifications only when they are really necessary


</section>

<section data-markdown>
### References

http://guides.rubyonrails.org/association_basics.html
http://stackoverflow.com/questions/26097563/jbuilder-vs-rails-api-active-model-serializers-for-json-handling-in-rails-4
http://swagger.io/
https://www.relishapp.com
http://stackoverflow.com/questions/3459287/whats-the-difference-between-a-mock-stub
https://facebook.github.io/react/docs/why-react.html
</section>

<section data-markdown>
##Thank you :)

</section>
