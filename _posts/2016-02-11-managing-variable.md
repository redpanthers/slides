---
layout: slide
title: managing environment variable
description: A presentation slide for managing environment variable
theme: black
transition: slide
permalink: /managing environment variable
author: Augustin Pulikan  
post_thumbnail: /slides/images/manage-env-variables.jpg
profile_image: /slides/profiles/augustin.jpg
---

<section data-markdown>
## Managing Environment Configuration Variables in Rails

Feb 11, 2016
</section>


<!-- Just to show that markdown and html can be mixed -->
<section>
  <h4>Hi, I am</h4>
  <h3>Augustin Pulikan</h3>
  <div style="width:150%;">
    <div style="float:left; width:30%;">
      <img alt="Jeroen De Meerleer" src="https://scontent.fmaa1-1.fna.fbcdn.net/hphotos-xft1/v/t1.0-9/12065624_873705689393220_2906766376590498181_n.jpg?oh=a5eca759b8989d24dd44d77d04b5eb8d&oe=57443E25" style="float: left; width:300px; height:300px;">
    </div>
    <div style="float:right; width:70%;">
      <ul style="float: left; padding-top: 4%;">
          <li>Ruby Devoloper Trainee at Redpanthers</li>

      </ul>
    </div>
  </div>

</section>

<!-- Just to show that markdown and html can be mixed -->

<section data-markdown>
### Introduction

when developing apps with Rails you need to set up environment variables to keep sensitive information secure in your code

</section>

<section data-markdown>
###Why Configuration Variables?

Hard coding sensitive information and committing them into source control can be dangerous as it means anyone with access to your code can see your API keys and secrets

</section>

<section data-markdown>
### few ways to manage environment variables in Rails

 Using Bash or Zsh Profile

 dotenv

 Figaro

 secrets.yml
</section>
<section data-markdown>
### Using Bash or Zsh Profile
 You can store the environment variable key/value pairs with the operating system directly and globally

 export KEY=value
</section>
<section data-markdown>
### Demerits of using Zsh or Bash profile

 Config file might get cluttered with so many of these variables and you’ll end up with one very messy global space

</section>

<section data-markdown>
### dotenv
dotenv solves the problems of setting project-specific environment vars and is super easy
You can then put your sensitive information inside a .env file at the root of your project directory

gem 'dotenv-rails'

PASSWORD=h4lpd4skpw0rd

S3_BUCKET=YOURS3BUCKET

</section>

<section data-markdown>
### Figaro
 Figaro is similar to dotenv. What it does is to allow you to store all your sensitive secrets in a YAML file at config/application.yml. With it’s simple figaro install command you get your YAML file automatically added to gitignore.

</section>

<section data-markdown>
### secrets.yml
 Very similar to Figaro’s config/application.yml, secrets.yml was added to Rails 4.1. You’ll have to add your secrets in config/secrets.yml as is done with Figaro

 The variables added here are accessible through Rails.application.secrets


</section>
<section data-markdown>
### Advantages of secrets.yml

 Enhanced security

 Prevents session tampering

 No need for any external dependency


</section>

<section data-markdown>
###Other Solutions

If you don’t want to use a gem to separate sensitive information from your project, there is a common pattern to create simple YAML files. You can name it private.yml.


</section>









<section data-markdown>
### How do I choose?

Using Bash or Zsh profile to store environment variables allows you to set system wide and user specific environment variable this approach is, as your configuration grows and becomes more complex The addition of secrets.yml to Rails 4.1 is a major step in the right direction and also does a very good job at managing app-specific environment variables in dotenv add your .env file to gitignore when using dotenv. Figaro does this for you because of its convention of never committing configuration files

</section>



<section data-markdown>
### References

https://www.launchschool.com

http://stackoverflow.com

https://www.twilio.com
</section>

<section data-markdown>
##Thank you :)

</section>
