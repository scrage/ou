# A general point to make about programming paradigms

First of all, there is an argument about programming paradigms in general, which puts the reson for having distinguishable programming approaches into the limelight, and resolves some debates about about them -- or even makes these debates straight invalid:
> "All programming paradigms assisst developers to adopt programming habits that constrain them **to help them to limit mistakes**."

Every programming paradigm, one way or another, essentially try to limit the programmer who adpts it, and that self-imposed limitation helps the programmer to steer away from potential mistakes.
And they tend to guard us from more mistakes than that of the freedom we have to give up for them.

**Structural programming** ensures a straight-forward execution flow by constraining the flow of transfer of control. (**Esgar Dijkstra** considered GOTO harmful. --  ***Structured Programming, 1968***)

**Functional programming** constrains assignment by writing code with no side-effects (relying on *immutability*): Each function translates its inputs into a new output, without changing those inputs in any way at all. (This is also referred to as *pure functioning programming*.)

**Logic programming** constrains programs to follow rules of formal logic.

One could even argue that **Machine Learning programming** constrains programming to specifications of fitness functions and selection of training data.

**OO programming** aims to put constrains on dependency management through polymorphism, as described by **Robert C. Martin**.

### A general good advice
Adopt programming habits that constrain you, to help you limit mistakes. Any programming paradigm only assists with that.

This choice of programming paradigm is truly just a choice, and it *can be fluid and contextual*. We can write crap code with any paradigm just as we can write great code with any paradigm as well. There is no bad or good paradigm, the existence of this debate is superfluous to say the least.

> *Source: https://www.youtube.com/watch?v=wyABTfR9UTU*

# OOP Programming

## The real value of OO is not the objects and inheritance, but messaging and polymorphism!
Object-Orientation is not merely about inheritance or polymorphism, as many OO developers tend to think. Alan Kay, who invented the term object-orient programming (***Object Orientation, 1966***) later said:
> "I'm sorry that I, long ago, coined the term "Objects" for this topic, because it gets many people to focus on the lesser idea. The big idea is messaging!"

He presumably meant that the key value of OO is the phenomena where we can send a message to **something** (a.k.a. an object) and it figures out how to process that **message**.
We can send the same message to 2 different objects and each of them (could) deal with that same message different ways -- ways that makes sense to them.

And this is polymorphism. The true value of OO is polymorphism, not inheritance.
In fact, the 1972 version of SmallTalk didn't even support inheritance at all.

## Visibility
**Encapsulation** is the discipline of organising an object’s properties and operations into private and public areas, depending on whether other objects should be able to access them. By defining what parts of a class in code should be private, public, or other, we declare their **visibility**.
Some languages, like Java, lets us control access to classes, methods, and operations via **access modifiers**.