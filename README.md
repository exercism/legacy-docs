# Documentation

_Project-wide documentation for Exercism._

This documentation is aimed at anyone wanting to contribute to the Exercism ecosystem or find help with an issue. // Reword -- some statement about the audience and intent of these docs

See below for an [Overview of Exercism][link]. If you need help navigating this documentation, see [What would you like to do?][link]. Otherwise, see the full [Table of contents][link] below.

## Overview of Exercism

Exercism—as an open source project—has two distinct parts.

1. The Product
2. The Curriculum

The product consists of a website and a command-line client (CLI). We are currently redesigning the website, and recommend that you do not invest time and effort in submitting changes to the website at this time.

The curriculum is much more like a traditional open source project than the product is. It consists of many small, well-defined components. If you wish to contribute to Exercism, we highly recommend contributing to the individual language tracks that make up the curriculum, or to the common pool of problem specifications. (A problem specification is a description of a problem to solve. An exercise is an implementation of that problem in a particular language. Language tracks are made up of exercises.)

To learn more about Exercism overall, see the [Overview][link].

## What would you like to do?

[I want to report an issue.][link-to-topic]

[I want to get started contributing to Exercism.][link-to-topic]

[I want to create a new language track.][link-to-topic]

[I am a maintainer of a language track and I want to learn more about my role.][link-to-topic] # Or move this into a separate set of documentation?

## Table of contents

- Landing page
- Overview
    - Architecture
    - Glossary
    - Philosophy // content from `./about/conception`
- Want to get started contributing to Exercism? // `./contributing-to-language-tracks/README`
    - // content from `./you-can-help`
- Language tracks/
    - REFERENCE DOC // I would make this all one long file detailing the structure of a language track (what are the files that should go into a language track repo?); use headers for hierarchy, rather than separating into multiple files. You could also write a generator that produces a repo with all the necessary files!
        - about.md
        - exercises
            - about.md
            - <exercise>.<extension>
            - <example>.<extension>
        - configuration.json
        - etc.
    - GETTING STARTED // simple tutorial on creating a new language track -- essentially `./language-tracks/launch/README.md`
- For language track maintainers/
    - Introduction
    - // other files from `./maintaining a track`
- Reporting issues
- Contributing // combine all the files in `./contributing-to-language-tracks` into one contributing.md file

---

We are working to improve this documentation.

If you find any part of it confusing, or if you can't figure out how to get started with something, then rest assured **it's not you, it's us!** Please [open a new issue](https://github.com/exercism/docs/issues) to describe what you were hoping to contribute with, and what you're wondering about, and we'll figure out together how to improve the documentation.
