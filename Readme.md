Markdown Slide
==============

Markdown slide is the simplest way to share your thoughts.
[reveal.js](https://github.com/hakimel/reveal.js/) allows you to create
beautiful interactive slides using HTML. This presentation will show/demo you
how to use *reveal.js* and write your presentations in style with [*Jekyll*](http://jekyllrb.com/)

### Features

    - Easy to install
    - Stupidly easy to use
    - Supports all Github-supported .gitignore files
    - Works on Mac, Linux and Windows

### Creating Slide

To add a new slide, simply add a file in the `-posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext`.

In the front matter use `slide` for layout. You can define *title*, *author*, *description* as well as the slide's *theme* and *transition* as. 

    --
    layout: slide
    title: Jekyll&#58; Make presentation page with reveal.js
    description: A presentation slide for how to use reveal.js in Jekyll
    theme: black
    transition: slide
    --
    
### Instruction to add new slides to [Red Panthers](http://redpanthers.github.io/slides/)


- Clone the slide using  git clone git@github.com:redpanthers/slides.git – recursive
- Create a 'new branch' with your name
- Open it in any text editor and edit the content listed inside posts (2016-01-12-create-slides-with-   revealjs-and-jekyll.html).
- Create new post in the newly created branch
- Push this branch to remote (git push origin 'newbranch')
- Create a pull request to master branch with a message to review the slides (tag sibinx7,pooja-r,manusajith)
- On successfull merging of this branch with master, pull master branch.
- From master branch give command `octopress deploy`  

### Contact info

Website : www.redpanthers.co

Company name : Red Panthers Software Solutions (P) Ltd

Address : Vijaya complex, Chembumukku, Kakkanad, Kochi 682030

### Thanks

redpanthers©2016