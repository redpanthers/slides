---
layout: slide
title: jenkins
description: A presentation slide for Jenkins-CI
theme: black
transition: slide
permalink: /jenkins-ci-opensource-automation-server
author: Augustin Pulikan  
post_thumbnail: /slides/images/jenkins.jpg
profile_image: /slides/profiles/augustin.jpg
---

<section data-markdown>
# Jenkins-CI

Jan 19, 2016
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

Jenkins is an open source continuous integration tool written in Java. The project was forked from Hudson after a dispute with Oracle. Jenkins provides continuous integration services for software development. 

</section>

<section data-markdown>
###What is CI?

Continuous integration (CI) is the practice, in software engineering, of merging all developer working copies to a shared mainline several times a day.

</section>

<section data-markdown>
### CI – Benefits
 Immediate bug detection

 No integration step in the lifecycle

 A deployable system at any given point

 Record of evolution of the project 
</section>

<section data-markdown>
### Why Jenkins? Flexibility!
 Jenkins is a highly configurable system by itself
  By combining Jenkins with Ant, Gradle, or other Build
Automation tools, the possibilities are limitless 

</section>

<section data-markdown>
### What can Jenkins do?
 Generate test reports

 Integrate with many different Version Control Systems

 Push to various artifact repositories

 Deploys directly to production or test environments
 

</section>

<section data-markdown>
### How Jenkins works - Setup
 Associating with a version control server

 Triggering builds

 Execution of shell scripts, bash scripts, Ant targets

 Artifact archival

 Email notifications
</section>

<section data-markdown>
### How Jenkins works - Building
 Building

 Jenkins executes the build in an executer

 Jenkins also has the concept of slave build servers

 Useful for building on different architectures

 Distribution of load 

</section>

<section data-markdown>
### How Jenkins works - Reporting

 Jenkins comes with basic reporting features


 Keeping track of build status
 Last success and failure
 “Weather” – Build trend
 T

</section>

<section data-markdown>
### Jenkins main page

 What’s building (“No builds in the queue”)
 Build Executor Status (both “Idle”)
 Status of the projects 

</section>

<section data-markdown>
### Enhancing Jenkins
SCM

Testing

Notifications

Reporting

Artifact savings
</section>

<section data-markdown>
### What Can Plugins Do?
Jenkins defines extensibility points, which are interfaces or abstract classes that model an aspect of a build system.

</section>

<section data-markdown>
### How to install plugins?

Installing the newest version

Installing a specific version

By hand
</section>

<section data-markdown>
### Installing the newest version

clicking Manage Plugins and go to the Available tab. select the checkbox, and then either attempt to Install without restart or Download now and install after restart

</section>

<section data-markdown>
### Installing a specific version

you can upload it from your computer on the Advanced tab of the Manage Plugins page in Jenkins.
</section>

<section data-markdown>
### By hand
Save the downloaded *.hpi/*.jpi file into the $JENKINS_HOME/plugins directory. You will then need to restart Jenkins
</section>

<section data-markdown>
### Plugin for highly productive ci
Jenkins git plugin 

Jenkins svn plugin 

Jenkins ssh plugin

Jenkins jira plugin

Jenkins email plugin

Artifactory

</section>

<section data-markdown>
### Useful plugins

All change plugin

Bitbucket plugin

Checkstyle plugin

</section>

<section data-markdown>
### Useful plugins

Depentency graph viewer

git notes

Deployment plugin

Heroku plugin

</section>



<section data-markdown>
### References

https://wiki.jenkins-ci.org
 
http://stackoverflow.com
 
https://www.quora.com
 
www.vogella.com
</section>

<section data-markdown>
##Thank you :)

</section>
