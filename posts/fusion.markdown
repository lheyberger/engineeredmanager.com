---
title: HTML5 framework fusion
subtitle: Seamless HTML5 frameworks integration in your templates
date: 07/03/2014
edited: 10/03/2014
author: Ludovic Heyberger
tags: [ programming, web, randombits ]
---

Today, lot of web developers are relying on HTML5 / CSS frameworks like Twitter's [Bootstrap](http://getbootstrap.com) or its twin brother [ratchet](http://goratchet.com). Those frameworks are very good at tackling the most boring issues like browser compatibility, responsive designs and homogeneity.

They sure are great at helping you start a web project very quickly but in my quest for [minimalism](./minimalism.html), there's one thing that annoys me a lot.

# Before

Here's what I'm talking about:

	<header class="bar bar-nav">
	  <h1 class="title">Title</h1>
	</header>

In this example, classes are used to define the look of the elements and how they will be styled by your framework.

As far as I remember, the big deal about CSS was to separate the semantic content from the presentation, and it seems to me, that this kind of frameworks are totally destroying all the efforts spent to have clean, and minimalist HTML markups.

# The bit

The idea is to use [SASS](http://sass-lang.com) and its simple yet powerful [@extend](http://sass-lang.com/guide) feature to "fuse" your favorite HTML5 framework with your beautiful markup.

You'll probably need to rename the main css file of your framework ("framework.min.css" for example) to something a bit more SASS complient like "_framework.scss" because SASS doesn't support importing standard CSS files (if you try to import a standard CSS file, it will be translated to a standard CSS import clause, which is not what we want here).

Then, all you have to do is to create your own SASS style containing something like:

	/* style.scss */

	@import "_myframework";

	header {
	  @extend .bar;
	  @extend .bar-nav;
	}

	header h1 {
		@extend .title;
	}

# After

_Et voilà_, you can remove those intruding classes from your markup and end up with a beautiful HTML source like that:

	<header>
	  <h1>Title</h1>
	</header>
