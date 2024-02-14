---
title: Minimalism
subtitle: Random thoughts on minimalism in a programmer's world
date: 10/12/2012
edited: 05/08/2013
author: Ludovic Heyberger
tags: [ workflow ]
---

A famous quote from [Antoine de Saint-Exupéry](http://wikipedia.org/wiki/Antoine_de_Saint-Exupéry) says that:

> A designer knows he has achieved perfection not when there is nothing left to add, but when there is nothing left to take away.

If the implication of minimalism in art is rather obvious, I've been liking the idea of trying to find minimalism in my everyday life, and especially in coding.

Let me share a few examples with you.


# Minimalism in design

The first example is the one that is right in front of your eyes.

While building this [this website](./about.html), I've tried to keep everything as small and minimalist as possible, starting with the script that generates it.
The python script is about 150 lines (plus a few external files) and goes through all the articles and generates the website, renders the templates and generate the atom feed.

Writing new articles is only a matter of creating a new [Markdown](http://wikipedia.org/wiki/Markdown) file containing a [Yaml](http://wikipedia.org/wiki/YAML) header.

If I want to re-generate the whole website, I only hit ctrl + shit + B in my [text editor](http://www.sublimetext.com) and the python script does all the job.

If I need to backup the website, a small .zip archive will easily do the job.

Having a static website is not only cool when you edit it, but it's also very easy to publish.
Any web server will do the job.
You can even _publish_ your website using Dropbox and something like [site 44](http://www.site44.com).

The HTML and the CSS has also been kept to their minimalistic state:
Very few colors (currently it could also be summed up to a few shades of gray + a hint color) and as few HTML tags as possible.


# Minimalism in tools

Since a few years, I've also been interested in finding minimalism in the tools I use.

During the first year of my computer science degree, we learned the C language using only [Emacs](http://wikipedia.org/wiki/Emacs) and [makefiles](http://wikipedia.org/wiki/Make_(software)) and while at school, you were authorized to read your emails / newsgroup only if you used [pine](http://wikipedia.org/wiki/Pine_(email_client)) or [mutt](http://wikipedia.org/wiki/Mutt_(email_client)).

No graphical user interface allowed.

Like most of us, I started using Visual Studio at the end of the scholarship. The first time I used it, it actually felt so powerful: projects, code completion, no more makefile writing. The paradise.

One day I stumbled upon [this article](http://www.charlespetzold.com/etc/doesvisualstudiorotthemind.html) and I really liked the whole concept even if I didn't fully understand what it was talking about (I was still discovering Visual Studio features like IntelliSense or the debugger).
I eventually kept the last paragraph about "The Pure Pleasures of Pure Coding" somewhere in my head and for me and this concept started to make it's comeback a few months / years ago.

After having used Visual Studio in a professional environment for a while with all the integrated tools like _better-IntelliSense-this_, _great-unit-test-framework-that_ and having experienced *lag* while typing your code (yes, using Resharper makes your text editor lag), you really value the beauty and simplicity of a well designed code or text editor.

Coming back to Emacs or Vim was a bit hard, especially in a windows environment, so I started to look at great alternatives.
That's when I started to use [SCite](http://wikipedia.org/wiki/SciTE). I really appreciated the simplicity of the interface, without dropping powerful features and ease of use.
I recently switched to [SublimeText2](http://www.sublimetext.com) which is as powerful as SCite, and is packed with great integrated themes, a distraction-free mode, and a fancy the minimap.


# Minimalist implementations

When I started my journey as a programmer I loved to write my C code as compact as possible.
I wasn't helped by the constraint we had at school that was called _the norm_ and that was automatically checked with a script:

- functions had to be less than 25 lines of code
- lines couldn't be more than 80 characters
- files had to contain a maximum of 5 public functions (you could go to 10 functions if they where static)

Of course we slightly missed the point of even having a _norm_ but a few years later, we realized that it should have led us to try to achieve better responsibility separation, and clearly splitting code between files.

It was fun to write those very compact C functions at first, but an awful pain when you wanted to read your code a few weeks or months later.
Those 1 letter variables were definitely not a good idea.


# Closing thoughts

You've probably already heard this quote from "[The Elements of Programming Style](http://wikipedia.org/wiki/The_Elements_of_Programming_Style)" by [Kernighan](http://wikipedia.org/wiki/Brian_Kernighan) and Plauger:

> Don't comment bad code, rewrite it

As true as it is, I found a principle that perfectly fits my state of mind while writing code:

> Write code in a way that the next person reading it will say: "I wouldn't have done better".

Following this mantra has helped me write simpler, cleaner and more direct code, and I think that this is the true way of minimalism.
