---
layout: slide
title: Memoization in ruby
description: A presentation slide for memoization in ruby
theme: black
transition: slide
permalink: /memoization-in-ruby
author: Pooja Raghunath
post_thumbnail: /slides/images/.jpg 
profile_image: /slides/profiles/pooja-raghunath.jpg
---
<section data-markdown>
# Memoization in Ruby

Feb 18, 2016
</section>

<section>
  <h4>Pooja Raghunath</h4>
  <p>
    Ruby Developer@RedPanthers
  </p>
</section>

<section data-markdown>
### What is Memoization?

* Memoization is the process of storing a computed value to avoid duplicated work by future calls.

* Memoization can be used to initialize a variable and store it with the result of some computation that is expected to give same result if computed again. 

</section>
<section data-markdown>
### Basic memoization pattern
* Perform some work
* Store the work result
* Use stored results in future calls

</section>


<section data-markdown>
### Types of memoization
* Single-line memoization
* Multiple-line memoization

</section>



<section>
Single-line memoization
<img alt="Jeroen De Meerleer" src="/slides/images/mem01.png">
</section>

<section data-markdown>
###Multiple-line memoization
Slow code won’t fit on one line without doing terrible things to it. There are a few ways to extend the basic pattern to work with multiple lines of code.

</section>

<section>
Multiple-line memoization

<img alt="Jeroen De Meerleer" src="/slides/images/memo11.png">
</section>




<section data-markdown>
### When to use Memoization
* When you have complex calculation that is supposed to give same result on multiple calls

* When you have a method that is giving same result over multiple calls but you need to call it multiple times

</section>

<section data-markdown>
### When to use Memoization -- contd.
* When you have database query with same parameters for a instance

  @user_score ||= User.where(name: 'Sam').first.try(:name)


* If you need user Sam's score then you can calculate and store it. When you need again then you can just return it from the instance variable.

</section>

<section data-markdown>
###What about nil and false in Memoization?

* Memoization technique  does not work with nil,false values.

@variable ||= false # suppose calculation value is false  

* As @variable had false value it will again go and evaluate for the OR part of condition which will come out false again.

* Thus, over multiple calls Memoization will not work if value comes out to be nil, or false.

</section>

<section data-markdown>
### What is Lazy initialization?

Lazy initialization is delaying intialization of the object/entity until the need of it for first time.

</section>

<section>
 Lazy initialization 
<img alt="Jeroen De Meerleer" src="/slides/images/lazy1.png">


</section>

<section data-markdown>
### Does Rails support Memoization?

* Rails had support for Memoize through ActiveSupport::Memoizable. 
* Memoizable is deprecated from Rails.
* Memoist is an extraction of ActiveSupport::Memoizable.

</section>

<section data-markdown>
### When should you memoize?

* When  duplicated database calls 
* When  expensive calculations
* When  repeated calculations that don’t change


</section>
<section data-markdown>
### When shouldn’t you memoize?

* Method that takes parameter
* Methods that uses instance variables

</section>

<section data-markdown>
### Conclusion
* So if you’re working on an app that needs a lot of memoization, you might want to use a gem that handles memoization for you with a nice, friendly API.

* Memoist seems to be a good one, and pretty similar to what Rails used to have.

</section>

<section data-markdown>
### References
* http://www.justinweiss.com/articles/4-simple-memoization-patterns-in-ruby-and-one-gem/
* http://rubyinrails.com/2014/11/03/memoization-ruby/
* http://gavinmiller.io/2013/basics-of-ruby-memoization/

</section>

