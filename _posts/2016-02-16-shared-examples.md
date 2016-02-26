---
layout: slide
title: Shared Examples in Rspec
description: A presentation on Shared Examples
theme: black
transition: slide
permalink: /shared-examples-rspec
author: Ajay Joseph
post_thumbnail: /slides/images/rspec.jpg
profile_image: /slides/profiles/ajay-joseph.jpg
---

<section data-markdown>
# Shared Examples in Rspec and keeping the code dry

Feb 16, 2016
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
### DRY
DRY (Don't Repeat Yourself)  is a principle of Software Development to reducing repetition of information or codes. We can apply DRY quite broadly to database schema, test plan, system, even documentation. DRY is mainly impremented using inheritance.

</section>

<section data-markdown>
##What is shared example?


</section>

<section data-markdown>
###Shared examples describe behaviour of classes or modules.
</section>

<section data-markdown>
###Shared examples make testing compositions of objects much easier. They allow us to execute the same group of expectations against several classes.
</section>

<section data-markdown>
###Including shared groups in other groups

</section>

<section data-markdown>
* include_examples "name"
* it_behaves_like "name"
* it_should_behave_like "name"
* matching metadata

</section>

<section>

    <img alt="Jeroen De Meerleer" src="/slides/images/Screen Shot 2016-02-16 at 7.58.14 am.png">

</section>

<section>

    <img alt="Jeroen De Meerleer" src="/slides/images/Screen Shot 2016-02-16 at 8.01.30 am.png">

</section>


<section data-markdown>
To prevent this kind of subtle error a warning is emitted if you declare multiple
methods with the same name in the same context. Should you get this warning
the simplest solution is to replace include_examples with it_behaves_like, in this
way method overriding is avoided because of the nested context created by it_behaves_like.

</section>

<section data-markdown>
##Shared Examples Conventions

The simplest approach is to require files with shared examples explicitly
from the files that use them. Keep in mind that RSpec adds the spec
directory to the LOAD_PATH, so you can say require
'shared_examples_for_widgets' to require a file at
###{PROJECT_ROOT}/spec/shared_examples_for_widgets.rb.

</section>

<section data-markdown>
##Shared Examples Conventions contd

One convention is to put files containing shared examples in spec/support/
and require files in that directory from spec/spec_helper.rb:

</section>

<section data-markdown>
##Shared Examples Conventions contd

When all of the groups that include the shared group reside in the same file,
just declare the shared group in that file.

</section>


<section data-markdown>
##Shared Examples Scenarios



</section>

<section data-markdown>
##Shared examples group included in two groups in one file

</section>

<section>

    <img alt="Jeroen De Meerleer" src="/slides/images/Screen Shot 2016-02-16 at 8.15.17 am.png">

</section>

<section data-markdown>
##Passing parameters to a shared example group

</section>

<section>

    <img alt="Jeroen De Meerleer" src="/slides/images/Screen Shot 2016-02-16 at 8.20.11 am.png">

</section>

<section data-markdown>
##Sharing metadata automatically includes shared example groups

</section>

<section>

    <img alt="Jeroen De Meerleer" src="/slides/images/Screen Shot 2016-02-16 at 8.24.01 am.png">

</section>

<section data-markdown>
###References

* https://www.relishapp.com/rspec/rspec-core/docs/example-groups/shared-examples
* http://modocache.svbtle.com/code-reading-shared-examples-in-rspec
* http://modocache.io/shared-examples-in-rspec

</section>

<section data-markdown>

##Thank you :)

</section>
