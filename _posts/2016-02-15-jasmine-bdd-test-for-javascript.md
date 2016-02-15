---
layout: slide
title: Jasmite Test Suite
description:
theme: black
transition: slide
permalink: /jasmine-javascript-test-suite
author: Sibin Xavier  
post_thumbnail: /slides/images/jasmine-test.jpg
profile_image: /slides/profiles/sibin.jpg
---
<section data-markdown>
 Jasmine Javascript Test Suite
</section>
<section>
	<h4>Sibin Xavier</h4>
	<p>
		Frontend Developer
	</p>
</section>
<section data-markdown>
### Testing is Important !!
 - To discover defects.
 - To avoid user detecting problems
 - To prove that the software has no faults
 - To learn about the reliability of the software.
 - To avoid being sued by customers
</section>
<section data-markdown>
### Testing is Important Cont..
 - To ensure that product works as user expected.
 - To stay in business
 - To detect defects early, which helps in reducing the cost of defect fixing?
</section>
<section data-markdown>
### Different type testing approach

  - Test Driven Development ( TDD )

  - Behavior Driven Development ( BDD )

</section>

<section data-markdown>
### TDD - Test Driven Development

  Simple and Easy to understand for Developers

  - First the developer writes some tests.
  - The developer then runs those tests and (obviously) they fail because none of those features are actually implemented.
  - Next the developer actually implements those tests in code.
</section>

<section data-markdown>
### TDD - contd..
  - If the developer writes his code well, then the in next stage he will see his tests pass.
  - The developer can then refactor his code, add comments, clean it up, as he wishes because the developer knows that    if the new code breaks something, then the tests will alert him by failing.

</section>

<section data-markdown>
### Test Driven Development - Life Cycle
  * Add a Test
  * Run all tests and see if the new one fails
  * Write some code
  * Run tests
  * Refactor code
  * Repeat
</section>
<section data-markdown>

  ![TDD]({{site.baseurl}}/assets/images/tdd-flowchart.png)
</section>
<section data-markdown>
### Various Methods

- KISS ( Keep It Simple, Stupid)
- YAGNI (You Aren't Gonna Need It)

</section>

<section data-markdown>
### Everything have some Advantages

  - More Test More Productive
  - More Quality
  - More Issue solving
  - More Cases
  - More Happy

Still issues

</section>
<section data-markdown>
### Everything have some Limitation

  * TDD also has many limitations
  * Extensive use of `Unit Testing`
  * Time spent to write Tests
  * Depend upon developer
  * Security Issues and Lots of useless codes
  * Maintenance is Cumbersome

</section>

<section data-markdown>
### Many alternatives

- Test Driven Work
- Acceptance Test Driven Development

</section>

<section data-markdown>
### BDD - Behavior Driven Test  

- New approach

</section>

<section data-markdown>
### BDD is not

![TDD vs BDD]({{site.baseurl}}/assets/images/two-roads.jpg)
</section>

<section data-markdown>
### BDD is

![Originated from TDD]({{site.baseurl}}/assets/images/originated-from-tdd.jpg)
</section>
<section data-markdown>
### BDD is

- Use General Technique and Principle of TDD
- Use benefits of Domain Driven Design and Object Oriented Analysis and Design


</section>
<section data-markdown>
### BDD Focus On

  - Where to start in the process
  - What to test and what not to test
  - How much to test in one go
  - What to call the tests
  - How to understand why a test fails

</section>
<section data-markdown>
####Example

  >Scenario 1:
  Refunded items should be returned to stock
  Given a customer previously bought a black sweater from me
  And I currently have three black sweaters left in stock
  When he returns the sweater for a refund
  Then I should have four black sweaters in stock

</section>

<section data-markdown>
## Jasmine - BDD for JavaScript Applications

Jasmine is Behavior Driven Development framework, It is not depend upon any other Frameworks,
Also It is not required DOM ( Document Object Model)

Jasmine available as Standalone version, as packages for Angular JS, Meteor JS and a Couple of other frameworks

Current Version is 2.4.1

</section>

<section data-markdown>
### Similar to other Testing Frameworks

It is similar to RSpec and Other Frameworks
***
#### Common

- Describe  block `describe`
- It block `it`
- Expect, ToBe, ToEqual etc...
- Pending methods

</section>

<section data-markdown>
##### Typical Example

  ```
  describe('A Suite ', function(){
    it("checking true equal to true", function(){
      expect(true).tobe(true)
    })  
  })
  ```

</section>
<section data-markdown>
### Suite

* Describe method
* Describe : String and Function as argument


</section>

<section data-markdown>
### Specs

* It method
* It: String and Function as arguments
* As many expectations  
</section>

<section data-markdown>
#### `Pending` in Jasmine

```
xdescribe('A Pending Suite', function(){
    xit("Checking pending spec", function(){
        pending()
    })
})

```
</section>
<section data-markdown>
### Setup and Teardown

##### Before and After methods

```
beforeEach(function(){

})
```
```
afterEach(function(){

})
```
</section>
<section data-markdown>
### Setup and Teardown - Contd..

##### Before All  and After  All
- Execute only once

```
beforeAll(function(){

})
```
```
afterAll(function(){

})
```
</section>
<section data-markdown>
# Spies

- A Spy can stub any function and tracks call to it and all arguments
- A Spy only exist inside describe or it block
- A Spy remove after each spec (it)

</section>


<section data-markdown>
## Spies - Helpers
- toHaveBeenCalled - return `true` if spy called
- toHabeBeenCalledWith - return `true` if the argument list matches any recorded calls

</section>
<section data-markdown>
### Example with Spy

</section>
<section data-markdown>
### Reference

* [Jasmine](http://jasmine.github.io/)
* [Josidavis](http://joshldavis.com/2013/05/27/difference-between-tdd-and-bdd/)
</section>
