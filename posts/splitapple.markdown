---
title: Splitting apples
subtitle: The story behind SplitApple for iOS - Postmortem
date: 28/07/2013
edited: 8/11/2014
author: Ludovic Heyberger
tags: [ programming, gaming, postmortem ]
---

_The opinions expressed herein are my own and do not represent my (ex-)employer’s views in any way. Nothing posted here should be considered official or sanctioned by my (ex-)employer or any other organization I’m affiliated with._

# The idea

The idea of doing an archery game on iOS came while [MKO Games](https://wikipedia.org/wiki/MKO_Games) was under administration. We were announced that the company would have to lay off a great amount of employees so the motivation was not at its best, to say the least.

Some of the employees started to look for a new job, others were playing games they didn't have time to finish during the year and others were working on side projects.

This is how [SplitApple](https://wikipedia.org/wiki/SplitApple) started.

The goal was to do a game that could be developed by a two-guys army, one programmer and one artist. The game had to be simple enough to allow one programmer to do all the coding (engine + gameplay included) and include few enough environments that one artist only could do all the modeling and the texturing.

After the two-thirds of the company _left_, we started to work on a few projects, including [Skyland SSR](http://wikipedia.org/wiki/Skyland_SSR), a really bad game based on the [Skyland](http://wikipedia.org/wiki/Skyland) animated series. During this time, the development of SplitApple was put on hold.

# The development

The development of SplitApple really started on January 2011 after one of the two people (the programmer) left the company. The artist submitted the idea of assigning a team on SplitApple and finishing what they both started.

That's when I started to work on this project.

I started from zero, re-implementing the early prototype in our in-house game engine O2. With the exception of the necessary bindings with the engine, which were done in C++, the whole game was actually done in [LUA](http://www.lua.org) with an heavy use of the state machine pattern and the [entity/component architecture](./archives.html#components).

Only a few months after the start, the project was submitted and the version 1.0 was released on the AppStore.

# The marketing

I never really understood why, but it seemed to me that the company didn't try to push the game as far as possible.

Nobody seemed to care that the game didn't have a dedicated Twitter account to communicate with the customers, to tease future updates and do other _marketing sutff_, so I created one ([@split_apple](https://twitter.com/@split_apple)).

Nobody really cared that neither the company nor the game had a Wikipedia page, so I created and updated them _(this is actually a shame if you consider that googling for [MKO Games](http://www.google.com/search?q=mko+games) or [SplitApple](http://www.google.com/search?q=splitapple) actually returns the Wikipedia page in the few first results)_.

People seemed to enjoy the game. We had good reviews and good feedbacks from the various blogs. People were saying good things, but we didn't really used it, so I added those mentions on the Wikipedia page, probably violating a few rules in the process.

In the end, it didn't worked as bad as initially expected, and the game managed to be ranked 1st of the french AppStore during one full week. According to the analytics, the game has **1.3 million unique users** and was **launched around 12 million times** on people's iOS' devices which is something we can be proud of.
