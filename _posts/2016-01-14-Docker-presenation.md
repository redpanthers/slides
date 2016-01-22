---
layout: slide
title: Docker
description: Package an application with all of its dependencies into a standardized unit for software development.
theme: black
transition: slide
permalink: /virtualization-using-docker-containers/
author: Jeena Jacob
post_thumbnail: /slides/images/docker.png
profile_image: /slides/profiles/jeena_jacob.jpg
---
<section data-markdown>
# Docker

Jan 13, 2016
</section>

<!-- Just to show that markdown and html can be mixed -->
<section>
  <h4>Hi, I am</h4>
  <h3>Jeena Jacob</h3>
  <div style="width:150%;">
    <div style="float:left; width:30%;">
      <img alt="Jeroen De Meerleer" src="/slides/profiles/jeena_jacob.jpg" style="float: left; width:300px; height:300px;">
    </div>
    <div style="float:right; width:70%;">
      <ul style="float: left; padding-top: 4%;">
          <li>RoR Devoloper at Redpanthers</li>

      </ul>
    </div>
  </div>

</section>

<section data-markdown>
### Why Docker?

Docker provides an integrated technology suite that enables development and IT operations teams to build,ship, and run distributed applications anywhere.

</section>

<section data-markdown>
### What is Docker?

Docker allows you to package an application with all of its dependencies into a standardized unit for software development.

Original author(s) :Solomon Hykes

Developer(s)  : Docker, Inc.

Initial release :13 March 2013

Stable release	1.9.1[1] :21 November 2015

</section>

<section data-markdown>
### Get Started with Docker for Linux

Install Docker

$ wget -qO- https://get.docker.com/ | shxt

</section>

<section data-markdown>
### Verify if Docker is installed successfully.

$ which docker 

service docker start 
service docker restart


</section>


<section data-markdown>
### images & containers

An image is software you load into a container.A container is a stripped-to-basics version of a Linux operating system

<img alt="dockerrun" src="/slides/images/run.png" style="float: left; width:300px; height:300px;">

</section>

<section data-markdown>
### Build your own image

#### Step 1: Write a Dockerfile

touch Dockerfile

eg:

FROM docker/whalesay:latest
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | cowsay

</section>

<section data-markdown>

#### Step 2: Build an image from your Dockerfile

$ docker build -t new_image_name .


</section>

<section data-markdown>

#### Step 3: Run your new docker-whale

 $ docker run new_image_name

</section>


<section data-markdown>
### Remove Docker Images

$ docker rmi -f image_id

or

$ docker rmi -f image_name


</section>

<section data-markdown>
### Reference

https://docs.docker.com/linux/

https://www.youtube.com/watch?v=K6WER0oI-qs

</section>

<section data-markdown>
### Thank You

</section>