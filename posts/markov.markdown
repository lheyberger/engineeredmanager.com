---
title: Generating names using Markov chains
subtitle: Yet Another markov chains article
date: 15/11/2012
author: Ludovic Heyberger
tags: [ programming, procedural, python ]
---

I've always been interested in procedural generation.
It's the kind of computer sciences area that makes you think that everything is possible without investing to much time on building assets.

Random name generation is probably the most intuitive and easiest way to start.

You will probably find countless random name generators using [Markov chains](https://wikipedia.org/wiki/Markov_chain) or other techniques, anyways, here's another one... :)

# Introduction to Markov chains

Citing wikipedia:

> A Markov chain, named after Andrey Markov, is a mathematical system that undergoes transitions from one state to another, between a finite or countable number of possible states. It is a random process usually characterized as memoryless: the next state depends only on the current state and not on the sequence of events that preceded it. This specific kind of "memorylessness" is called the Markov property.

The thing about Markov chains is that they are very simple to implement, and you have a nice result very quickly.

# Feeding the beast

Markov chains are great at generating names that sound real because they are based on real data.
The best way to start is to feed the program with a huge list of real world words, like common first names, god names, or town names for example.
The more words, the better.

Internally, the program uses a transition table to generate the names.
This is the transition table for the name "John":

	{
		None: ['jo'],
		'jo': ['h'],
		'oh': ['n'],
		'hn': [None]
	}

The word is sliced in group of 2 letters:

	[ "jo", "oh", "hn" ]

and each of this group gets a transition to the letter right next to it.
The "None" values indicate the start and the beginning transitions.

If you add "Joseph" as a second word to the transitions table, it would be sliced in:

	[ "jo", "os", "se", "ep", "ph" ]

and the updated transition table would be:

	{
		None: ['jo', 'jo'],
		'jo': ['h', 's'],
		'oh': ['n'],
		'hn': [None],
		'os': ['e'],
		'se': ['p'],
		'ep': ['h'],
		'ph': [None]
	}

There are now two ways of starting the chain, though they are the same, "jo" and "jo", as well as two ways of ending the chain, "hn" and "ph".

# Generating names

Given the previous transition table, starting to generate a random name will look like this:

- Select a random starting transition between "jo" and "jo". The word is **"jo"**.
- From "jo", select the next transition between "h" and "s". The word could either be "jos" or "joh". Let's say it picked **"jos"**.
- From "os", select the next transition. No choice here so it gives **"jose"**.
- Proceed until you pick an end transition. You will now have your word **"joseph"**.

Simple.

You can control the output by providing a maximum lenght to prevent generated names to be too long.
The more you will encounter a transition when parsing the names, the more it's likely to be picked when generating a random word.
The main thing here is to provide a big enough list so that random generated names will _sound_ like the names in the list.

Given a list that contains the names of gods from different origins, running the algorithm 10 times gives:

- Wakaman
- Midhrbogdo
- Taizokamma
- Myr
- Jun
- Hodlun
- Kolano-gi
- Machine
- Sar'e
- Avar-ko-ka
