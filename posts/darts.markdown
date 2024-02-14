---
title: Throwing darts
subtitle: The story behind T-80 Darts for iOS - Postmortem
date: 31/07/2013
edited: 8/11/2014
author: Ludovic Heyberger
tags: [ programming, gaming, postmortem ]
---

_The opinions expressed herein are my own and do not represent my (ex-)employer’s views in any way. Nothing posted here should be considered official or sanctioned by my (ex-)employer or any other organization I’m affiliated with._

# The project

Right after the launch of [SplitApple](http://wikipedia.org/wiki/SplitApple) we started to work on a darts throwing game for iOS, [T-80 Darts](http://wikipedia.org/wiki/T-80_Darts). The game was mainly developed by 2 programmers (including me) and 2 artists over a period of 7 months.

# What went right

## Capitalizing on the work of SplitApple

During the development of T-80 Darts, we were still working on SplitApple to add more content and release a few updates. We clearly had in mind [what went right and what went wrong](./splitapple.html) during the development, so we could be careful not to repeat the same errors.

When we started the development of SplitApple, we already had a lot of assets that were ready, so the technical part lagged a bit behind. On the contrary, during the development of T-80 Darts, lot of technical parts were reused so we could take the time to do some cleanup and really think on how things should have been done while the graphical assets were produced.

## Enhancing our internal scripting engine

While the artists were creating the assets, we enhanced a lot of the parts we reused from SplitApple, including:

* State machines
* UI scripting file & configuration
* [Components](./archives.html#components) management
* Input management

Almost everything we did in SplitApple was reworked to be more straightforward and more efficient. We had time to tackle a lot of the small technical issues we had on SplitApple and from a technical point of view, the game was _more mature_.

## Providing more features

When we released SplitApple, we knew the game was designed to be done by 1 programmer and 1 artist, so we had to trim all the unnecessary features and limit the content to the strict minimum. We tried to improve that point for T-80 Darts and we succeeded in some way:

* The game implements the classic 01 games (301, 501 and 701) in addition to the less common _Around the clock_ and _Cricket_ modes.
* All game modes are available both in single player and versus.

## "Packaging"

SplitApple was launched as a universal application with a starting price at €1,79. It was increased to €2,69 latter because we decided to _rebrand_ the application as an HD version and release a special _SplitApple for iphone_ version at €0,89 as well as a free version call _SplitApple Lite_.

On the other hand, T-80 Darts' release plan was much clearer:

* T-80 Darts (iphone only version) released at €0,89
* T-80 Darts HD (universal version) released at €2,69

# What went wrong

## Waste of resources

We were virtually a team about 2 times the size as the team that worked on SplitApple and even with that, T-80 Darts took longer to develop that SplitApple. For this kind of small games, development time is crucial, and you should release your games as fast as possible with the absolute minimum set of features required to make a game.

## Lot of ideas dropped

When we were initially thinking about making a darts throwing game reusing as much from SpitApple as we could, we had a lot of ideas to try to improve the game. For example we wanted to have different kind of rules and each one of them would take place in a special environment, with a special player and a special target.

The only one that actually made it to the final release was the irish pub.

We also thought about adding in-app purchase to customize the look of the game (custom darts and targets) but this feature was also dropped.

## Marketing & Sales

The company only took care of creating a Facebook page dedicated for the game, so we decided to created both Twitter and Google+ pages to increase our _presence_ as well as a Wikipedia page. Nothing else was really done to try to bring people to speak about the game. We knew we were not really releasing the killer game for iOS and we had the feeling that we didn't try all our possible to make it work.

In the end, the game was far from being profitable with less than 15 000 users and 75 000 sessions played.
