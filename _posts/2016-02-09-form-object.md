---
layout: slide
title: Form Objects
description: Form objets used to de-complex ruby models
theme: black
transition: slide
permalink: /form-objects
author: Harisankar P S
post_thumbnail: /slides/images/form.jpg
profile_image: /slides/profiles/hsps.jpg
---

<section data-markdown>
# Form Objects
### Decomplexing your models

Feb 09, 2016
</section>

<!-- Just to show that markdown and html can be mixed -->
<section>
  <div style="width:150%;">
    <div style="float:left;">
      <img alt="Harisankar P S" src="https://avatars1.githubusercontent.com/u/979321?v=3&s=460" style="float: left; width:400px; height:400px;"><br>
      <b>Harisankar P S aka <i> HsPS</i></b>
    </div>
    <div>
      <ul style="float: left">
        <li>Biker</li>
        <li>Gadget Enthusiast</li>
        <li>Writes Ruby code for a living</li>
      </ul>
    </div>
  </div>

</section>

<section data-markdown>
### Introduction

* Models, as per the MVC pattern are where we store our business logic.
* Forms, refering to web forms, are html pages through which we collect data from the user
* We add a lot of code to the models to make our forms work properly like validations, extra attributes.

</section>

<section data-markdown>
### So whats are these form objects?

Form objects are like models just that it would only have code related to your forms.

</section>

<section data-markdown>
### So if they are like models, then why create new objects?

Building a complex business application is more or less like building a complex webform, the
way we collect data is most important. Thus our models are growing for just a single form, now imagine
if you require 10 forms for your model, and for each model there is a different requiement.

You will end up with models having over ** 500-1000 ** lines of code. Which essentially becomes a nightmare to
maintain.

</section>

<section data-markdown>
### So what will using a form object achieve


  * Code related to a forms would be at a single location

  * Thus it becomes easier to write test for them

  * Our model will end up having only the actual business logic

</section>

<section data-markdown>
### Now some live code examples

```sh
https://github.com/coderhs/form-objects-example
Branches:
> without-form-objects, 

> with-form-objects 
```
</section>

<section data-markdown>
### So how does this work?
* Duck Typing

Ruby/Rails doesn't look into the type of object that was passed, the only concern is the methods it tries to call
should be there. ie. if we ask it to quack, it should quack. In this case, we need to make sure that the form gets
the model_name when it calls for it.
</section>

<section data-markdown>
### References

* http://railscasts.com/episodes/416-form-objects
* https://robots.thoughtbot.com/activemodel-form-objects
* https://github.com/coderhs/form-objects-example

</section>

<section data-markdown>
##Thank you :)

</section>
