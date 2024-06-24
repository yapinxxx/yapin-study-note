---
date: 202303032350
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2023-03-03]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

[williamdurand.fr](https://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/)

# From STUPID to SOLID Code!

William Durand

9–12 minutes

---

⚠️ This content has been written a long time ago. As such, it might not reflect my current thoughts anymore. I keep this page online because it might still contain valid information.

Last week I gave a talk about [Object-Oriented Programming](https://en.wikipedia.org/wiki/Object-oriented_programming) at Michelin, the company I am working for. I talked about writing better code, [from STUPID to SOLID code!](http://slides.williamdurand.fr/from-stupid-to-solid-code/) **STUPID** as well as [**SOLID**](http://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) are two acronyms, and have been [covered](http://blog.ircmaxell.com/2012/05/dont-be-stupid-grasp-solid-slides.html) [quite](http://nikic.github.io/2011/12/27/Dont-be-STUPID-GRASP-SOLID.html) a [lot](http://lostechies.com/chadmyers/2008/03/08/pablo-s-topic-of-the-month-march-solid-principles/) for a long time. However, these mnemonics are not always well-known, so it is worth spreading the word.

In the following, I will introduce both **STUPID** and **SOLID** principles. Keep in mind that these are **principles**, **not laws**. However, considering them as laws would be good for those who want to improve themselves.

## STUPID code, seriously?[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#stupid-code-seriously)

This may hurt your feelings, but you have probably written STUPID code already. I have too. But, what does that mean?

-   [**S**ingleton](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#singleton)
-   [**T**ight Coupling](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#tight-coupling)
-   [**U**ntestability](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#untestability)
-   [**P**remature Optimization](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#premature-optimization)
-   [**I**ndescriptive Naming](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#indescriptive-naming)
-   [**D**uplication](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#duplication)

In the following, I will explain the individual points with more details. This is more or less the transcript of my talk.

### Singleton[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#singleton)

The [Singleton pattern](http://en.wikipedia.org/wiki/Singleton_pattern) is probably the most well-known design pattern, but also the most misunderstood one. Are you aware of the _Singleton syndrome_? It is when you think the Singleton pattern is the most appropriate pattern for the current use case you have. In other words, you use it everywhere. That is definitely **not** cool.

[Singletons are controversial](https://code.google.com/p/google-singleton-detector/wiki/WhySingletonsAreControversial), and they are often [considered anti-patterns](http://stackoverflow.com/questions/11292109/why-is-singleton-considered-an-anti-pattern-in-java-world-sometimes). You should [avoid them](http://programmers.stackexchange.com/questions/40373/so-singletons-are-bad-then-what). Actually, the use of a [singleton is not the problem, but the symptom of a problem](http://programmers.stackexchange.com/questions/40373/so-singletons-are-bad-then-what/40376#40376). Here are two reasons why:

-   Programs using global state are very difficult to test;
-   Programs that rely on global state hide their dependencies.

But should you really avoid them all the time? I would say _yes_ because you can often replace the use of a singleton by something better. Avoiding static things is important to avoid something called **tight coupling**.

### Tight Coupling[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#tight-coupling)

**Tight coupling**, also known as **strong coupling**, is a generalization of the Singleton issue. Basically, you should [reduce coupling](http://martinfowler.com/ieeeSoftware/coupling.pdf) between your modules. **Coupling** is [the degree to which each program module relies on each one of the other modules](http://en.wikipedia.org/wiki/Coupling_(computer_programming)).

If making a change in one module in your application requires you to change another module, then coupling exists. For instance, you instantiate objects in your constructor’s class instead of passing instances as arguments. That is bad because it **doesn’t allow further changes** such as replacing the instance by an instance of a sub-class, a _mock_ or whatever.

Tightly coupled modules are **difficult to reuse**, and also **hard to test**.

### Untestability[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#untestability)

In my opinion, **testing should not be hard!** No, really. Whenever you don’t write unit tests because you don’t have time, the real issue is that your code is bad, but that is another story.

Most of the time, **untestability** is caused by **tight coupling**.

### Premature Optimization[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#premature-optimization)

Donald Knuth said: “_premature optimization is the root of all evil_. There is **only cost**, and **no benefit**”. Actually, optimized systems are much more complex than just rewriting a loop or using [pre-increment instead of post-increment](http://stackoverflow.com/questions/24886/is-there-a-performance-difference-between-i-and-i-in-c). You will just end up with unreadable code. That is why [Premature Optimization is often considered an anti-pattern](http://www.c2.com/cgi/wiki?PrematureOptimization).

A friend of mine often says that there are two rules to optimize an application:

-   don’t do it;
-   (for experts only!) don’t do it yet.

### Indescriptive Naming[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#indescriptive-naming)

This should be obvious, but still needs to be said: **name** your classes, methods, attributes, and variables **properly**. Oh, and [don’t abbreviate](https://williamdurand.fr/2013/06/03/object-calisthenics/#6-dont-abbreviate)! You write code for people, not for computers. They don’t understand what you write anyway. Computers just understand `0` and `1`. **Programming languages are for humans**.

### Duplication[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#duplication)

[Duplicated code](http://c2.com/cgi/wiki?DuplicatedCode) is bad, so please [Don’t Repeat Yourself](http://lostechies.com/patricklioi/2013/07/30/no-seriously-dont-repeat-yourself/) ([DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself)), and also [Keep It Simple, Stupid](http://en.wikipedia.org/wiki/KISS_principle). Be lazy the right way - write code only once!

Now that I have explained what STUPID code is, you may think that your code is STUPID. It does not matter (yet). Don’t feel bad, keep calm and be awesome by writing SOLID code instead!

## SOLID to the rescue![#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#solid-to-the-rescue)

SOLID is a term describing a **collection of design principles** for good code that was invented by Robert C. Martin, also known as _Uncle Bob_.

SOLID means:

-   [**S**ingle Responsibility Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#single-responsibility-principle)
-   [**O**pen/Closed Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#openclosed-principle)
-   [**L**iskov Substitution Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#liskov-substitution-principle)
-   [**I**nterface Segregation Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#interface-segregation-principle)
-   [**D**ependency Inversion Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#dependency-inversion-principle)

### Single Responsibility Principle[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#single-responsibility-principle)

Single Responsibility Principle or [SRP](http://en.wikipedia.org/wiki/Single_responsibility_principle) states that **every class should have a single responsibility**. There should **never be more than one reason for a class to change**.

Just because you can add everything you want into your class doesn’t mean that you should. Thinking in terms of responsibilities will help you design your application better. Ask yourself whether the logic you are introducing should live in this class or not. Using **layers** in your application helps a lot. Split big classes in smaller ones, and avoid [god classes](http://c2.com/cgi/wiki?GodClass). Last but not least, **write straightforward comments**. If you start writing comments such as `in this case`, `but if`, `except when`, `or`, then you are doing it wrong.

### Open/Closed Principle[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#openclosed-principle)

Open/Closed Principle or [OCP](http://en.wikipedia.org/wiki/Open/closed_principle) states that software entities should be **open for extension**, but **closed for modification**.

You should make all member variables **private** by default. Write getters and setters only when you need them. I’ve already covered this point in a previous article, as [the ninth rule of the Object Calisthenics](https://williamdurand.fr/2013/06/03/object-calisthenics/#9-no-getters/setters/properties) is related to this principle.

### Liskov Substitution Principle[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#liskov-substitution-principle)

Liskov Substitution Principle or [LSP](http://c2.com/cgi/wiki?LiskovSubstitutionPrinciple) states that objects in a program should be **replaceable with instances of their subtypes without altering the correctness** of the program.

Let’s take an example. A rectangle is a plane figure with four right angles. It has a `width`, and a `height`. Now, take a look at the following pseudo-code:

```
rect = new Rectangle();

rect.width  = 10;
rect.height = 20;

assert 10 == rect.width
assert 20 == rect.height
```

We simply set a `width` and a `height` on a `Rectangle` instance, and then we assert that both properties are correct. So far, so good.

Now we can improve our definition by saying that a rectangle with four sides of equal length is called a square. A square **is a** rectangle so we can create a `Square` class that extends the `Rectangle` one, and replace the first line above by the one below:

According to the definition of a square, its width is equal to its height. Can you spot the problem? The first assertion will fail because we had to change the behavior of the setters in the `Square` class to fit the definition. This is a violation of the Liskov Substitution Principle.

### Interface Segregation Principle[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#interface-segregation-principle)

Interface Segregation Principle or [ISP](http://en.wikipedia.org/wiki/Interface_segregation_principle) states that **many** client-specific **interfaces are better than one** general-purpose interface. In other words, you should not have to implement methods that you don’t use. Enforcing ISP gives you **low coupling**, and **high cohesion**.

When talking about **coupling**, [cohesion](http://en.wikipedia.org/wiki/Cohesion_(computer_science)) is often mentioned as well. **High cohesion** means to keep similar and related things together. The **union** of cohesion and coupling is [orthogonal design](http://www.jasoncoffin.com/cohesion-and-coupling-principles-of-orthogonal-object-oriented-programming/). The idea is to **keep your components focused** and try to **minimize the dependencies between them**.

Note that this is similar to the [Single Responsibility Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#single-responsibility-principle). An interface is a contract that meets a need. It is ok to have a class that implements different interfaces, but be careful, don’t violate SRP.

### Dependency Inversion Principle[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#dependency-inversion-principle)

Dependency Inversion Principle or [DIP](http://www.c2.com/cgi/wiki?DependencyInversionPrinciple) has two key points:

-   **Abstractions should not depend upon details**;
-   **Details should depend upon abstractions**.

This principle could be rephrased as **use the same level of abstraction at a given level**. Interfaces should depend on other interfaces. Don’t add concrete classes to method signatures of an interface. However, use interfaces in your class methods.

Note that [Dependency Inversion Principle is not the same as Dependency Injection](http://lostechies.com/derickbailey/2011/09/22/dependency-injection-is-not-the-same-as-the-dependency-inversion-principle/). **Dependency Injection** is about how one object knows about another dependent object. In other words, it is about [how one object acquires a dependency](http://martinfowler.com/articles/dipInTheWild.html). On the other hand, DIP is about the level of abstraction. Also, a [Dependency Injection Container](http://www.martinfowler.com/articles/injection.html) is a way to auto-wire classes together. That does not mean you do Dependency Injection though. Look at the [Service Locator](http://en.wikipedia.org/wiki/Service_locator_pattern) for example.

Also, rather than working with classes that are tight coupled, use interfaces. This is called [programming to the interface](http://www.fatagnus.com/program-to-an-interface-not-an-implementation/). This **reduces dependency** on implementation specifics and makes code **more reusable**. It also ensures that you can replace the implementation without violating the expectations of that interface, according to the Liskov Substitution Principle seen before.

## Conclusion[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#conclusion)

As you probably noticed, **avoiding tight coupling is the key**. It is present in a lot of code, and if you start by focusing on _fixing_ this alone, you will immediately start writing better code.

If I may leave you with only one piece of advice, that would be to **use your brain**. There are a lot of principles in software engineering. Even if you don’t understand all these principles, always think before writing code. Take the time to understand those that you don’t understand.

Honestly, writing SOLID code is not that hard.

## Slides[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#slides)

## TL;DR[#](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#tldr)

**STUPID** is an acronym that describes bad practices in Oriented Object Programming:

-   [**S**ingleton](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#singleton)
-   [**T**ight Coupling](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#tight-coupling)
-   [**U**ntestability](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#untestability)
-   [**P**remature Optimization](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#premature-optimization)
-   [**I**ndescriptive Naming](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#indescriptive-naming)
-   [**D**uplication](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#duplication)

**SOLID** is an acronym that stands for **five basic principles** of Object-Oriented Programming and design to _fix_ STUPID code:

-   [**S**ingle Responsibility Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#single-responsibility-principle)
-   [**O**pen/Closed Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#open/closed-principle)
-   [**L**iskov Substitution Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#liskov-substitution-principle)
-   [**I**nterface Segregation Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#interface-segregation-principle)
-   [**D**ependency Inversion Principle](about:reader?url=https%3A%2F%2Fwilliamdurand.fr%2F2013%2F07%2F30%2Ffrom-stupid-to-solid-code%2F#dependency-inversion-principle)

Rule of thumb: **use your brain**!