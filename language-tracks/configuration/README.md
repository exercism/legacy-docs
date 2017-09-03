# Configuration

## Track-level configuration

The configuration for a language track lives in a file named `config.json` in the root of a repository.

This is used by the website as well as a lot of the tooling in order to properly combine all the disparate language track repositories into a coherent experience and curriculum.

## Dependencies

The `config.json` is used by [trackler][], which is a light wrapper around the entire Exercism curriculum, and [configlet][], which is the tool that we use to verify the configuration.

## Automated verification of `config.json`

We have [automated linting of the track configuration][configlet-lint].

[configlet-lint]: /language-tracks/configuration/configlet.md
[trackler]: https://github.com/exercism/trackler
[configlet]: https://github.com/exercism/configlet
