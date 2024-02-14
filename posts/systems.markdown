---
title: Systems
subtitle: A lightweight entity-component system - Part 3
date: 05/08/2013
author: Ludovic Heyberger
tags: [ draft, programming, python, components ]
---

This is the third article talking about an Entity / Component proof of concept I've been developing.
You should probably read the one talking about [Components](./components.html) and the one talking about [entities](./entities.html) before.

In an Entity / Component architecture, there's data on one side (entities and components) and _code_ that actually does stuff on the other side.
One part of that would be the Systems.

Systems are mainly used to apply changes on a full set of entities like collecting all the Sprites components and drawing them on the screen.
Typically, systems will be executed by order of priority.
