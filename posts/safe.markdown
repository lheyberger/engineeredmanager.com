---
title: Safe LinQ queries
subtitle: Using linq to protect your code from null collections
date: 20/02/2013
author: Ludovic Heyberger
tags: [ programming, c#, randombits ]
---

In my quest of [minimalism](./minimalism.html) I always try to find elegant solutions to common issues that I face every day.

This time, it's all about simplifying your linQ queries to a much more elegant form.

# Before

Your code could look like this:

    if (values != null)
    {
      var result = values.Select(r => r.Value);
    }
    else
    {
      // do stuff
    }

or maybe like that:

    var result = values != null
      ? values.Select(r => r.Value)
      : Enumerable.Empty<object>();

# The bit

    public static IEnumerable<T> EmptyIfNull<T>(this IEnumerable<T> collection)
    {
      return collection ?? Enumerable.Empty<T>();
    }

# After

    var result = values.EmptyIfNull().Select(r => r.Value);
