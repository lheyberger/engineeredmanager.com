---
title: Event tester
subtitle: Simplifying event unit testing with a few overloads
date: 06/04/2013
edited: 08/08/2013
author: Ludovic Heyberger
tags: [ programming, c#, randombits ]
---

Everybody agrees that writing unit tests is good for your application.
You often need to test that an event has been raised or not.

Your mocking framework probably offers you a way to check if some method has been called which can be used to test your events ([Moq](http://code.google.com/p/moq) provides such a mechanism at least), or you can go for a full-manual solution.

But there always comes a moment where you have to test an asynchronous event, and generally you have to introduce things like ManualResetEvents finally ending up with two different ways of testing your events.

# Before

Testing a synchronous event:

    [Test]
    public void TestEventRaised()
    {
      bool hasBeenRaised = false;

      var testObject = new TestObject();

      testObject.Event += () => hasBeenRaised = true;
      testObject.DoSomething();

      Assert.IsTrue(hasBeenRaised);
    }

Testing an asynchronous event:

    [Test]
    public void TestEventRaised()
    {
      ManualResetEvent resetEvent = new ManualResetEvent();

      var testObject = new TestObject();

      testObject.Event += () => resetEvent.Set();
      testObject.DoSomething();

      Assert.IsTrue(resetEvent.WaitOne(1000));
    }

# The bit

Here comes the EventTester and the AsyncEventTester classes that lets you write your unit tests the same way whether your events are asynchronous or not.

The trick here is to implement a few templated OnEventRaised methods that will match your event's signatures.

    public void OnEventRaised<T1>(T1 a1);
    public void OnEventRaised<T1, T2>(T1 a1, T2 a2);
    public void OnEventRaised<T1, T2, T3>(T1 a1, T2 a2, T3 a3);

    public T OnEventRaised<T, T1>(T1 a1);
    public T OnEventRaised<T, T1, T2>(T1 a1, T2 a2);
    public T OnEventRaised<T, T1, T2, T3>(T1 a1, T2 a2, T3 a3);

# After

Now you can use the same construct for both synchronous and asynchronous events:

    [Test]
    public void TestEventRaised()
    {
      EventTester eventTester = new EventTester();
      // AsyncEventTester eventTester = new AsyncEventTester();

      var testObject = new TestObject();

      testObject.Event += eventTester.OnEventRaised;
      testObject.DoSomething();

      eventTester.Verify();
    }
