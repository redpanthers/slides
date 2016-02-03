---
layout: slide
title: Spree Commerce
description: A presentation on Spree Commerce
theme: black
transition: slide
permalink: /vim-editor-tips
author: Ajay Joseph
post_thumbnail: /slides/images/spree.jpg
profile_image: /slides/profiles/ajay-joseph.jpg
---

<section data-markdown>
# Spree Commerce

Feb 2, 2016
</section>

<!-- Just to show that markdown and html can be mixed -->
<section>
  <h4>Hi, I am</h4>
  <h3>Ajay Joseph</h3>
  <div style="width:150%;">
    <div style="float:left; width:30%;">
      <img alt="Jeroen De Meerleer" src="https://scontent-hkg3-1.xx.fbcdn.net/hphotos-frc3/v/t1.0-9/945390_3255807009318_1975357127_n.jpg?oh=1cbfba3bef55ba6fa91cb048a4808622&oe=5747C14D" style="float: left; width:300px; height:300px;">
    </div>
    <div style="float:right; width:70%;">
      <ul style="float: left; padding-top: 4%;">
          <li>Ruby Devoloper Trainee at Redpanthers</li>

      </ul>
    </div>
  </div>

</section>

<section data-markdown>
### Introduction
Spree is a full featured e-commerce platform written for the Ruby on Rails framework. Spree is a production ready store that can be used “out of the box”, but more importantly, it is also a developer tool that can be used as a solid foundation for a more sophisticated application than what is generally possible with traditional open source offerings.

</section>

<section data-markdown>
### Introduction -- contd.

Spree is 100% open source. It is licensed under the very permissive New BSD License. You are free to use the software as you see fit, at no charge. Perhaps more important than the cost, Spree is a true open source community. Spree has hundreds of contributors who have used and improved it while building their own e-commerce solutions.

</section>

<section data-markdown>
  ##Why spree commerce and why not something like magento?

</section>

<section data-markdown>
##what is Magento

* 25% marketshare
* written in php with some elements of zend framework
* over 8.2million lines of code
* 2 editions CE and EE of which EE is paid

</section>

<section data-markdown>
### Motivation

The goal spree is to build a complete open source commerce solution for Ruby on Rails. At the start of this project, the Rails commerce space was immature and lacking serious solutions for developers with complex business needs. Spree seeks to create a large and healthy open source community that developers of other languages have come to expect.
</section>

<section data-markdown>

The founder of Spree was motivated to start the project after failing to find an existing community in the Rails space dedicated to this vision. In addition, he was motivated by unsuccessful efforts to use other open source solutions in other programming languages, including (but not limited to) the Magento and OSCommerce platforms. These solutions were deemed to be unsatisfactory when challenged with even the simplest practical cases of use.
</section>

<section data-markdown>
###  Opinionated Commerce

David Heinemeier Hansson (the creator of Rails) is well known for saying that Rails is “opinionated software.” Spree continues this fine tradition of adopting a few strong (possibly controversial) opinions which drive its development.


</section>

<section data-markdown>
### No Solution Will Satisfy Everyone

No solution can possibly solve everyone’s needs perfectly. There are simply too many ways in which people do business for us to tailor to each individual need. Rather than come up short (like so many projects before it did), Spree’s approach is to simply accept this and not even try. Instead Spree tries to focus on solving 90% of the bulk that most commerce projects face. The remaining 10% will need to be addressed by the end developer familiar with the client’s exact business requirements.

</section>

<section data-markdown>
### Online Commerce --Spree

Rails developers are the target audience for this application - not business owners. Serious businesses have complicated needs that require paying one or more software professionals to solve them. Spree seeks to be the platform that developers use as the foundation for their project rather than having to start from scratch or settle for less with other software
</section>

<section data-markdown>
### Developers Need Complete Control

 Most business owners will not be satisfied with the generic templates offered by other platforms. Most businesses have very specific shipping and taxation rules as well. Spree needs to be flexible enough to accommodate most situations. Sensible defaults should be provided with an eye towards allowing further customization.

</section>


<section data-markdown>
## THE CORE of spree commerce

</section>

<section data-markdown>
### Addresses
* Address
* Zones
* Countries
* State

</section>

<section data-markdown>
### Adjustments

* amount
* label
* eligible
* mandatory
* state
* included

</section>

<section data-markdown>
### Spree customization

* Authentication
* View
* Checkout

</section>

<section data-markdown>
## Setting up spree

</section>

<section data-markdown>
  ###Setting up a sample rails application using spree

  * gem install rails -v 4.2.0
  * gem install bundle
  * brew install imagemagick
  * gem install spree_cmd
  * rails _4.2.0_ new mystore
  * cd mystore
  * spree install --auto-accept // rails generate spree:install
  * rails server

</section>


<section>

    <img alt="Jeroen De Meerleer" src="https://guides.spreecommerce.com/images/developer/spree_welcome.png">

</section>

<section data-markdown>
###References

* http://bluestout.com/blog/magento-vs-spree-best-ecommerce-platform/
* https://guides.spreecommerce.com/developer/getting_started_tutorial.html

</section>

<section data-markdown>

##Thank you :)

</section>
