---
layout: slide
title: Playing timezones in rails
description: A presentation slide for playing timezones in rails
theme: black
transition: slide
permalink: /playing-timezone-in-rails
author: Pooja Raghunath
post_thumbnail: /slides/images/timezone.png  
profile_image: /slides/profiles/pooja-raghunath.jpg
---

<section data-markdown>

# Playing timezone in rails

Feb 8, 2016

</section>

<section>
  <h4>Pooja Raghunath</h4>
  <p>
    Ruby Developer@RedPanthers
  </p>
</section>

<section data-markdown>
### Why is time important?
* Track when something happened

* Schedule when something will happen

</section>

<section data-markdown>
### What is UTC?
“Coordinated Universal Time” International Standard Other time zones can be described with the number of hours and minutes with which they deviate from UTC as an offset
</section>

<section data-markdown>
### UTC offset?
The UTC offset is the difference in hours and minutes from Coordinated Universal Time (UTC) for a particular place and date.It is generally shown in the format ±[hh]:[mm], ±[hh][mm], or ±[hh].
</section>

<section data-markdown>
 ### Time zones vs time offsets
 * A time zone is a geographical region where almost everyone observes the same standard time.

* A time offset is an amount of time subtracted from or added to UTC to get the current civil time – whether it's standard time or daylight saving time.
</section>

<section data-markdown>
### Configure your Rails app
 * The most important one is the config.time_zone configuration in your `config/application.rb file`.
 * ActiveRecord will help you convert from and to UTC and the time zone.
 * ActiveRecord fetches UTc time from DB and convert it to the timezone in config.time.zone

</section>

<section data-markdown>
### Parsing
* When parsing time information it's important to never do it without specifying the time zone.
* The best way to do this is to use Time.zone.parse (which will use the time zone specified in config.time_zone) instead of just Time.parse (which will use the computer's time zone).

</section>

<section data-markdown>
### Date vs Time
* Time has date information but Date does NOT have time information.
* Always make sure to convert it to your configured time zone:

* 1.day.from_now # => Fri, 03 Mar 2012 22:04:47 JST +09:00

* Date.current.in_time_zone # => Fri, 02 Mar 2012 00:00:00 JST +09:00

* Never use:

 Date.today.to_time # => 2012-03-02 00:00:00 +0100
</section>

<section data-markdown>
### Querying
Since Rails know that your time information is stored as UTC in the database it will convert any time you give it to UTC.

* Post.where(["posts.published_at > ?", Time.current])
</section>

<section data-markdown>
### Working with multiple user time zones

Create a private method in your ActionController and run it as an around filter.  

</section>

<section data-markdown>
###DOs
* 2.hours.ago # => Thu, 27 Aug 2015 14:39:36 AFT +04:30
* 1.day.from_now # => Fri, 28 Aug 2015 16:39:36 AFT +04:30
* Time.zone.parse("2015-08-27T12:09:36Z") # => Thu, 27 Aug 2015 16:39:36 AFT +04:30
* Time.current # => Thu, 27 Aug 2015 16:39:36 AFT +04:30
* Time.current.utc.iso8601 # When supliyng an API ("2015-08-27T12:09:36Z")

</section>

<section data-markdown>

* Time.strptime("2015-08-27T12:09:36Z", "%Y-%m-%dT%H:%M:%S%z").in_time_zone # If you can't use Time.zone.parse (Thu, 27 Aug 2015 16:39:36 AFT +04:30)
* Date.current # If you really can't have a Time or DateTime for some reason (Thu, 27 Aug 2015)
* Date.current.in_time_zone # If you have a date and want to make the best out of it (Thu, 27 Aug 2015 00:00:00 AFT +04:30)
</section>

<section data-markdown>
### DON'Ts
* Time.now # Returns system time and ignores your configured time zone. (2015-08-27 14:09:36 +0200)
* Time.parse("2015-08-27T12:09:36Z") # Will assume time string given is in the system's time zone. (2015-08-27 12:09:36 UTC)
* Time.strptime("2015-08-27T12:09:36Z", "%Y-%m-%dT%H:%M:%S%z") # Same problem as with Time.parse. (2015-08-27 12:09:36 UTC)
* Date.today # This could be yesterday or tomorrow depending on the machine's time zone, see https://github.com/ramhoj/time-zone-article/issues/1 for more info. (Thu, 27 Aug 2015)
</section>

<section data-markdown>
### What if I don't have logged in users
If your are building a site that needs to show times and you don't have logged in users, setting the server time zone is not a solution either. You have the following options:
* Use Javascript on the front end to figure out the correct time to display, based on the user's browser
* Try this gem https://github.com/scottwater/detectimezonerails
* Use the user's IP address to infer the timezone
</section>

<section data-markdown>
### Testing

* Timezones are working correctly by changing the timezone for the current user and checking that  views show the correct date/time for their timezone.

</section>

<section data-markdown>
### Integration testing with client side JS
However if you are doing integration testing that involves client side JavaScript, things get more difficult. For example the client side could get the timezone from the browser and then use that for querying the server, this is really hard to mock.
A particular gem that is very useful is timezone_local.

</section>

<section data-markdown>
### Reference
* http://api.rubyonrails.org/classes/ActiveSupport/TimeZone.html
* http://www.elabs.se/blog/36-working-with-time-zones-in-ruby-on-rails
* https://www.reinteractive.net/posts/168-dealing-with-timezones-effectively-in-rails

</section>

<section data-markdown>
### Thank You!!

</section>
