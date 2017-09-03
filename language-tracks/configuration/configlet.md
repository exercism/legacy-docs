# Configlet

You can download the latest release from the releases page in the [configlet repo](https://github.com/exercism/configlet/releases).

## Linting

The `lint` command helps ensure that:

1. all exercises have a unique uuid
1. all exercises have a test suite
1. all exercises have a reference solution
1. all the `exercises` that are listed in the configuration have, in fact, been implemented
1. all implementations are listed in the configuration
1. exercises that the maintainers have decided to forego do not have an associated implemention

A problem might be foregone for a number of reasons, typically because it's not a good fit for the language.

## Formatting

The `fmt` command is used to normalize the JSON format for the `config.json` file as well as the `config/maintainers.json` file.
This helps ensure that we don't get irrelevant, noisy diffs in these files.

This is especially useful because we sometimes need to make changes across all of the language tracks at the same time.
We tend to script these pull requests, and it's harder to review these when they include irrelevant whitespace changes.

## UUID Generation

The `uuid` command makes it easy to generate a new UUID for an exercise that is being added.
