---
title: virtualenv + SublimeText
subtitle: Integrating virtualenv in SublimeText's build system
date: 04/07/2013
author: Ludovic Heyberger
tags: [ programming, python ]
---

When programming in python, it's a good practice to use [virtualenv](http://www.virtualenv.org) to clearly separate the dependencies between different projects. However, it's not always straightforward to integrate _virtualenv_ within your current workflow.

I like to code using [SublimeText2](http://www.sublimetext.com) because it fits my needs to have both a powerful code editor, and a simple text editor to write markdown, but hitting _ctrl + shift + b_ while editing a python file will execute it using the python install that comes first in your $PATH environment variable, which is obviously not what you want.

A good way to integrate _virtualenv_ with a _SublimeText2_ is to create a project file that contains a custom build system that will run your scripts using your _virtualenv_'s python.

    {
      "folders":
      [
        {
          "name": "Project",
          "path": "."
        }
      ],
      "build_systems":
      [
        {
          "name": "Python virtualenv",
          "selector": "source.python",
          "cmd": ["$project_path/env/bin/python", "-u", "$file"]
        }
      ]
    }

That's it.

Your script will now be executed with whatever python version you used to create your virtual environment.
