# Architecture of Exercism

The main components that make up Exercism are:

- [the website](#the-website)
- [the CLI](#the-cli)
- [the API](#the-api)
- [Trackler](#trackler)

### The Website

The [exercism.io](http://exercism.io/) website is a vital part of the [product](https://github.com/exercism/docs/blob/master/about/README.md#the-product). The community uses the site to:

- get an overview of the available problems and languages
- provide and receive feedback
- learn by reading code
- find links to useful learning resources

### The CLI

The Command Line Interface (CLI) provides a way to fetch exercises and submit solutions to the site. It is a stand alone library so you don't need any particular language environment in order to use it.

You can read more about the CLI in the corresponding GitHub [repository](https://github.com/exercism/cli).

### The API

The API that services the command-line client lives in the [Exercism website repository](https://github.com/exercism/website).

### Trackler

The [Trackler](https://github.com/exercism/trackler) is a Ruby gem that bundles the data for the exercises of all language tracks, providing a unified interface to the entire curriculum.
