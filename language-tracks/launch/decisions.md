# Make some decisions

There are a few things we need to figure out to start.

As you make decisions document them in the README.md of the repository.

Some of these topics might not be relevant.
That's fine—just move on.
The harder the decision was to make, the more important it is to document it thoroughly.
What trade-offs did you consider?
What tipped your gut feeling in one direction or the other?
What sealed the deal?

We want to make sure that as contributors and maintainers come onto the project, we don't have to re-hash the same decisions over and over again.
We might change our minds about things later, which will be much easier if we know the background for the choices that have been made so far.

### Programming language variants

If there are multiple variants of the language, which one should we support?

What is the official name of the language or variant?
Are we likely to support multiple variants in the future?

### Language name and track ID

Before we can bootstrap a new track repository we need to settle on both the name by which we refer to the programming language itself as well as the URL-friendly ID that will be used everywhere.

Sometimes these are the same aside from capitalization (e.g. _Haskell_ vs `haskell`, _Go_ vs `go`), other times the track ID is a normalized version of the language name (e.g. _C#_ vs `csharp`, _C++_ vs `cpp`, _PL/SQL_ vs `plsql`).

### Installation and dependencies

Ideally people should be up and running as quickly and smoothly as possible, while also using commonly used tools.
Remember also, that people will be developing on multiple platforms, so we should consider how this will work for Linux, Windows, and MacOS.

We want to avoid having people set up an environment with niche tools.
This is in part because it's harder to search for answers when you get stuck if it's a home-grown project used by a small group of people.
Also, becoming fluent in a language is not just about the syntax, but also familiarity with the basics of the ecosystem.
At the same time, we don't want to force people through endless painful setup.

We should discuss the various options and trade-offs.

### Testing framework

All of the exercises are based on providing a failing test suite for people to run and make pass, so we need to pick a testing framework.

If there are multiple testing frameworks available, we'll need to figure out which one is the best fit.
In general we prefer tools in the standard library if they're available, and if not we aim for a third party library that is widely used.
If there is a choice between several common libraries, then consider a few factors:

* Is one of them easier to install?
* Is one of them easier to get help with or search for resources about?
* Is one of them simpler than the other either in syntax or conceptually?

Remember that all Exercism exercises are by nature very small, so there's no need for the complexity that real-world projects sometimes require.

### Naming conventions

There are a number of considerations to take into account when deciding on a naming scheme for exercise files.

1. The naming scheme should be idiomatic for the language and testing framework.
1. If the command to run the tests is different for different exercises, we want to be able to generate the command.
1. The Exercism tooling needs to be able to identify the test file and reference solution.

In Exercism we want to be as true to the language as possible, since we're aiming to get people conversant with the common idioms and practices as possible.

In some programming languages it might not make sense to talk about "test file" and "solution file".
That's probably fine, but it might require us to jump through some hoops to get everything working.

The naming convention must be consistent.
