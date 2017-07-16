# Track-Level Linting With Configlet

If the `config.json` file is incomplete or broken, a lot of other things break. To make things easier we made a small tool, [configlet][] to help verify the config.

The `configlet` tool ensures that:

1. all the `exercises` that are listed in the configuration have, in fact, been implemented
1. all exercises have a sample solution
1. all implementations are listed in the configuration
1. `foregone` problems do not have an associated implemention

A problem might be foregone for a number of reasons, typically because it's a bad exercise for the language.

## Installation

You can download the latest release from the releases page in the [configlet repo](https://github.com/exercism/configlet/releases), or you can use the `bin/fetch-configlet` command from the root of the language track repository, which will make a guess at what operating system and architecture you have and attempt to download the right one.

## Usage

If you are standing at the root of the language track repository, call:

```
bin/configlet lint .
```

Notice the dot. This says _check the config of the language track that is stored right here_.

[configlet]: https://github.com/exercism/configlet#configlet
