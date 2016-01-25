---
layout: slide
title: Share Tribe
description: A presentation slide for Sharetribe
theme: black
transition: slide
permalink: /sharetribe
author: Pooja Raghunath
profile_image: /slides/profiles/pooja-raghunath.jpg
---
<section data-markdown>
# Sharetribe 

Jan 30, 2016
</section>

<section>
  <h4>Pooja Raghunath</h4>
  <p>
    Ruby Developer@RedPanthers
  </p>
</section>

<section data-markdown>
### Introduction
What is Sharetribe?
Sharetribe is an open source platform to create your own peer-to-peer marketplace.

</section>

<section data-markdown>
### Requirements

    * Ruby. Version 2.1.2 
    * RubyGems
    * Bundler: gem install bundler
    * Git
    * A database: Only MySQL has been tested, so we give no guarantees that other databases (e.g. PostgreSQL) work. 
    * Sphinx: Version 2.1.4 has been used successfully, but newer versions should work as well. Make sure to enable MySQL support. If you're using OS X and have Homebrew installed, install it with brew install sphinx --with-mysql
    * Imagemagick: If you're using OS X and have Homebrew installed, install it with brew install imagemagick

</section>
<section data-markdown>
### Setting up the development environment
* Get the code. Cloning this git repo is probably easiest way:

git clone git://github.com/sharetribe/sharetribe.git

* Navigate to the Sharetribe project root directory.

* Create a database.yml file by copying the example database configuration:

cp config/database.example.yml config/database.yml

* Create the required databases with these commands.
* Add your database configuration details to config/database.yml. You will probably only need to fill in the password for the database(s).

</section>
<section data-markdown>
* Install the required gems by running the following command in the project root directory:

`bundle install`

* Initialize your database:

`bundle exec rake db:schema:load`

* Run Sphinx index:

`bundle exec rake ts:index`

* Start the Sphinx daemon:

`bundle exec rake ts:start`
</section>
<section data-markdown>
* Use Mailcatcher to receive sent emails locally
* Invoke the delayed job worker:

`bundle exec rake jobs:work`

* In a new console, open the project root folder and start the server. The simplest way is to use the included Webrick server:

`bundle exec rails server`


</section>
<section data-markdown>
### Database migrations
To update your local database schema to the newest version, run database migrations with:

  `bundle exec rake db:migrate`
</section>
<section data-markdown>
### Setting up Sharetribe for production
* Initialize your database:

`bundle exec rake RAILS_ENV=production db:schema:load`

* Run Sphinx index:

`bundle exec rake RAILS_ENV=production ts:index`

* Start the Sphinx daemon:

`bundle exec rake RAILS_ENV=production ts:start`

* Precompile the assets:

`bundle exec rake assets:precompile`

</section>
<section data-markdown>
### Setting up Sharetribe for production
* Invoke the delayed job worker:

`bundle exec rake RAILS_ENV=production jobs:work`

* In a new console, open the project root folder and start the server:

`bundle exec rails server -e production `

</section>
<section data-markdown>
### Set configuration values
Default configuration settings are stored in `config/config.default.yml`


</section>
<section data-markdown>
### Pros and cons for building with a Sharetribe backend
## Procs
* Get a fully functional marketplace built in one day.
* Need not to write any new code to create a marketplace website
* There's a community of other developers buiding on top of Sharetribe codebase.

</section>

<section data-markdown>
### pros and cons for building with a Sharetribe backend
## Cons
* Sharetribe is a marketplace CMS built to support multiple different marketplace types. 
* Also, Sharetribe is a CMS built specifically for building marketplaces. 
* To extend the platform by leveraging the open source code.

</section>

<section data-markdown>
### Thank You!!

</section>
