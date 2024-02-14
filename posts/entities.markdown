---
title: Entities
subtitle: A lightweight entity-component system - Part 2
date: 09/12/2012
edited: 04/08/2013
author: Ludovic Heyberger
tags: [ programming, python, components ]
---

This is the second article about an Entity / Component proof of concept I've been developing.
If you haven't done it already, I suggest you read the article about [Components](./components.html) before reading this one.

Entities shouldn't be more complicated than components.
They actually just provide a logical way of regrouping components.

They are implemented as python dictionaries and created using a factory method:

	def Entity(ID = uuid.uuid4()):
		return {
			'ID': ID,
		}

	>>> e = Entity()
	>>> pprint(e)
	{
		'ID': UUID('fc9f593d-9b99-4eba-abd6-a2309bbb84f0')
	}

Attaching a component is easy:

	>>> p = Position()
	>>> attach(e, p)
	>>> pprint(e)
	{
		'ID': UUID('fc9f593d-9b99-4eba-abd6-a2309bbb84f0'),
		'components': {
			'__main__::Position': [
				{'_type': 'Module::Position', 'x': 0.0, 'y': 0.0, 'z': 0.0}
			]
		}
	}

Detaching is simple as well:

	>>> detach(e, p)
	>>> pprint(e)
	{
		'ID': UUID('fc9f593d-9b99-4eba-abd6-a2309bbb84f0'),
		'components': {
			'Module::Position': []
		}
	}

To keep good performances when attaching and detaching lot of components, cleanup is left to another function that can be called at the end of the update:

	>>> cleanup(e)
	>>> pprint(e)
	{
		'ID': UUID('fc9f593d-9b99-4eba-abd6-a2309bbb84f0')
	}

There's no restriction concerning the number of components of the same type you can attach to an entity.
As previously said, entities are just bags of components and they don't have any logic.

Since entities and components both are simple dictionaries, they can be serialized and unserialized easily.

In the next [entry](./systems.html), I talk about _systems_.
