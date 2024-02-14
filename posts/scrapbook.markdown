---
title: Scrapbook
subtitle: A copy/paste heaven
date: 01/01/1970
author: Ludovic Heyberger
tags: [ draft ]
---

# Blog post ideas

- using postsharp
- dependency injection / testability using MEF
- refactoring existing codebases
- OpticsPro 10
- A/B testing in mobile applications


# Artemis

## Entities, Components, Systems

- Entities as bags of component
- Components as bags of data
- Systems as a way to work on components
- Component (c data structure) + System (c function) = Component as a class / object
- Entities, Components and Systems must be prioritized
- Components should be testable separately (no need for a scheduler)
- Entities should be testable separately (no need for a scheduler)

example implementation:

    entity = {
    	components : {
    		ComponentSystem_1 : [ Component_1, Component_1, Component_1, ],
    		ComponentSystem_2 : [ Component_2, Component_2, Component_2, ],
    		ComponentSystem_3 : [ Component_3, Component_3, Component_3, ],
    	}
    }

## Scheduler

- entities / components / systems should not be aware of the scheduler
- entities / components / systems should not depend on the implementation (threads, coroutines, subprocess, remote calls, whatever.)
- Scheduler should work on lot of entities / components / systems
- entities should not have to rely on the scheduler to synchronize (they should use a priority mechanism)

# Automatic folder sorter

facts:

- a download is typically a folder containing stuff
- it may match a release whatever its type is

process:

1. identify the content of the folder
2. move the folder to the right destination
3. eventually clean the content of the folder

# About notebooks

## First results

Before starting this process, I merely only used a pen to sign checks to pay the rent and I was a great fan of taking notes on my smart phone.
For a computer scientist, I would have imagine the transition to be painful and boring, but it was actually surprisingly fun.
