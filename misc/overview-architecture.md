# Architecture of Exercism

The main components that make up Exercism are:

- [the website](#the-website)
- [the CLI](#the-cli)
- [the API](#the-api)
- [Trackler](#trackler)

### The Website

The [exercism.io](http://exercism.io/) website is a vital part of the [product](https://github.com/exercism/exercism.io/blob/master/docs/overview-of-exercism.md#the-product). The community uses the site to:

- get an overview of the available problems and languages
- provide and receive feedback
- learn by reading code
- find links to useful learning resources

### The CLI

The Command Line Interface (CLI) provides a way to fetch exercises and submit solutions to the site. It is a stand alone library so you don't need any particular language environment in order to use it.

You can read more about the CLI in the corresponding GitHub [repository](https://github.com/exercism/cli).

### The API

Exercism provides an [API](https://github.com/exercism/x-api) to serve the exercises to people using the command-line client. The API is also consumed by the Exercism website.

### Trackler

The [Trackler](https://github.com/exercism/trackler) is a Ruby gem that bundles the data for the exercises of all language tracks, providing a unified interface to the entire curriculum.
