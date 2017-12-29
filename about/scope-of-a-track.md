# The scope of a track

Exercism's sweet spot is to bridge that awkward gap between an effortful "hello world" and being able to fluently express simple ideas idiomatically using the basic features of a language along with its standard library.

There are a few key ideas here:

* **basics:** basic syntax, basic language features, commonly used standard library packages or modules
* **fluency:** ease and familiarity, not having to think about syntax
* **idioms:** using the conventions that are common for the language

Familiarity with third party libraries is notably absent from this list.
As is the ability to write scalable, production-worthy code and solve real-world problems.

There are plenty of resources available that cover more advanced topics, but it's challenging to make use of them without fluency in the basics.

## What makes a good track?

A good track targets a programming language.
It provides lots of small exercises, each of which is self-contained.

It covers all the language features that are used in the normal day-to-day work of a programmer writing code in that language.
It provides opportunities to discover and make use of the most commonly used packages or modules in the standard library.

## What is out of scope?

There are many interesting topics and exercises that _could_ be added to Exercism, but that probably shouldn't.

### Specialty libraries and techniques

In [exercism/exercism.io#3113](https://github.com/exercism/exercism.io/issues/3113) [Jim Rybarski](https://github.com/jimrybarski) brought up the idea of adding exercises that teach introductory image analysis with Python and `scikit-image`.

Image analysis is a great topic, and the `scikit-image` library is a useful library, but it is not targeting fluency in basic Python, and is therefore a great example of something which is out of scope for Exercism.

### Not programming languages

Early on someone requested that we add a track for math proofs.

A project that provides lots of little exercises helping people get better at math proofs would be really cool—it just doesn't fit within the framework of Exercism.

### Not _really_ programming languages

In [exercism/discussions#84](https://github.com/exercism/discussions/issues/84) Brian Hicks wondered whether or not we should have a track for JSON after observing that people do some funny things with it.

JSON is markup, not a programming language.
People absolutely do funny things with it—and it's a worthy topic for teaching best practices, but it's not a great fit for an Exercism track.

The same goes for HTML and CSS, which have also been requested.

### Big, real-world-sized problems

While it would be undeniably useful to practice navigating in large codebases and refactoring extremely complex code, adding these sorts of exercises would stretch the format of Exercism beyond the breaking point.

## What does this mean for existing tracks?

An Exercism track can be improved by considering several different questions:

* Are there language features that are not (or are only sparsely) covered by exercises?
* Are there parts of the standard library that are unlikely to be used in solutions to existing exercises?

Additionally, it's worth considering that we're targeting fluency.
We're not just trying to introduce a topic, we want people to have ample opportunity to practice and play around with it.
A good track will often provide numerous exercises that all touch on similar areas.
