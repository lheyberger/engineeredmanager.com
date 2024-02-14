---
title: Parameters' validation
subtitle: Using C# linq to achieve better readability
date: 17/06/2013
edited: 04/08/2013
author: Ludovic Heyberger
tags: [ programming, c#, randombits ]
---

In a large scale application, you often use some kind of [defensive programming](http://wikipedia.org/wiki/Defensive_programming) techniques such as [input validation](http://wikipedia.org/wiki/Secure_input_and_output_handling#Input_validation) to ensure that your method can run correctly and produce the desired output.

This simple random bit of code provides you a clean and elegant way of validating that your collections are neither null nor empty.

Bonus: It also works with strings.

# Before

    MyClassConstructor(string name, IEnumerable<int> values)
    {
      if (string.IsNullOrEmpty(name))
      {
        throw new ArgumentNullException("name");
      }

      if (values == null || values.Any() == false)
      {
         throw new ArgumentNullException("values");
      }
    }

# The bit

    public static class Extensions
    {
       public static bool IsNullOrEmpty<T>(this IEnumerable<T> collection)
       {
          return collection == null || collection.Any() == false;
       }
    }

# After

    MyClassConstructor(string name, IEnumerable<int> values)
    {
      if (name.IsNullOrEmpty())
      {
        throw new ArgumentNullException("name");
      }

      if (values.IsNullOrEmpty())
      {
         throw new ArgumentNullException("values");
      }
    }
