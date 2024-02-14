---
title: Components
subtitle: A lightweight entity-component system - Part 1
date: 08/12/2012
edited: 04/08/2013
author: Ludovic Heyberger
tags: [ programming, python, components ]
---

Entity-components systems seem to have been around for a few years now.
I remember debating about it with co-workers back in 2007 and they were nothing new.
For a long time, classic engines where inheritance-based and used complicated object oriented design to fulfill their needs.
But it seems that the trend has quickly evolved in favor of Entities / Components architectures which allows for better code and data separation as well as better component re-usability.

Let me share a few details about how the components are implemented in a proof of concept I've been developing as a pet project.
I've tried to keep the design as [minimalist](./minimalism.html) as possible.

There can be potentially a great number of components running at the same time during the application's lifetime, so they must be very simple and lightweight.
They are implemented using built-in python dictionaries and created by a factory method:

	def Position(x = 0.0, y = 0.0, z = 0.0):
		return {
			'x': x,
			'y': y,
			'z': z
		}

	>>> p = Position()
	{'x': 0.0, 'y': 0.0, 'z': 0.0}

A decorator is used to add internal attributes to components such as their types:

	@Component
	def Position(x = 0.0, y = 0.0, z = 0.0):
		return {
			'x': x,
			'y': y,
			'z': z
		}

	>>> p = Position()
	{'_type': 'Module::Position', 'x': 0.0, 'y': 0.0, 'z': 0.0}

And here is the decorator used to create components:

	class Component(object):
		def __init__(self, f):
			self.f = f

		def __call__(self, *args):
			c = self.f(*args)
			c['_type'] = '{0}::{1}'.format(self.f.__module__, self.f.__name__)
			return c

In the next [entry](./entities.html), I introduce the entities, which are basically just bags of components.
