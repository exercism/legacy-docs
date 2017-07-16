# Overview of Exercism

Exercism—as an open source project—has two distinct parts.

1. The Product
2. The Curriculum

Most open source projects are code that people incorporate into their own projects. They're tools and components used to build software: libraries and frameworks, packages and infrastructure.

Exercism is unusual in the open source landscape. Exercism isn't a component or infrastructure. Exercism is an experience targeted at the end-user.

If you want to follow the high-level goings-on of the Exercism project, watch the [discussions][] repository, and sign up for the [newsletter][].

You can also check out our high-level [roadmap][].

## The Product

The product consists of a website and a command-line client (CLI).

We are currently investing our efforts in design research and product design towards a complete redesign and re-implementation of the website. As such, we would recommend that you do not invest time and effort in submitting changes to the website at this time.

You can read more about our decision to do a full redesign in the article [The Delightful Design of Exercism][design-of-exercism], and the results of our first six months of work in the [resulting design documents][ux-insights].

You can get an overview of how the current product is put together in the [architecture][] document.

## The Curriculum

The curriculum is much more like a traditional open source project than the product is. It consists of many small, well-defined components. If you wish to contribute to Exercism, we highly recommend contributing to the individual language tracks that make up the curriculum, or to the common pool of problem specifications.

You can read more about [what our aim is for a language track[goals-exercism].

### The Problem Specifications

A problem specification is a description of a problem to solve. This description is not specific to any particular programming language or library or tool.

An example is:

> Determine whether or not a word is an [isogram][].

You could do this on the back of a napkin, or on a whiteboard, or by writing code.

There are many ways to contribute to the problem specifications.

- fix typos
- improve exercise descriptions
- document edge cases
- discuss philosophical questions
- make up more exercises
- define canonical data-sets to make it easier to implement the exercise

Th common pool of problem specifications is maintained in the [exercism/problem-specifications][problem-specifications] repository. You can check out the [open issues][problem-specifications-issues].

### The Language Tracks

Each language track implements exercises. These may be based on a problem specification from the common pool, or it may be a custom exercise defined specifically for that programming language.

Each exercise consists of an mininum a README describing the problem to solve, and a collection of automated tests define the requirements of the solution. A good test suite will not mandate a particular approach, but will allow people to try many different approaches, and solve the exercise in many different ways.

There are many ways to [contribute to a language track][getting-started-track]. You can find the repositories for the current language tracks in the list of repositories tagged with [exercism-track][track-topic].

[exercism-io]: https://github.com/exercism/exercism.io
[cli]: https://github.com/exercism/cli
[isogram]: https://en.wikipedia.org/wiki/Isogram
[discussions]: https://github.com/exercism/discussions/issues
[newsletter]: http://tinyletter.com/exercism
[design-of-exercism]: http://tinyletter.com/exercism/letters/the-delightful-design-of-exercism
[problem-specifications]: https://github.com/exercism/problem-specifications
[problem-specifications-issues]: https://github.com/exercism/problem-specifications/issues
[getting-started-track]: /contributing-to-language-tracks/README.md
[ux-insights]: /about/conception/README.md
[architecture]: /about/architecture.md
[exercism-track]: https://github.com/search?q=org%3Aexercism+topic%3Aexercism-track
[roadmap]: /about/roadmap.md
