# Track Configuration

The configuration for a language track lives in a file named `config.json` in the root of a repository.

This file has the following keys:

* **language** (string) the official name of the programming language.
* **active** (boolean) whether the track is active on the site.
* **foregone** (array of strings) a list of problem specification slugs that the track maintainers have decided not to implement.
* **exercises** (array of objects) the metadata for implemented exercises.
* **test_pattern** (string) _(optional)_ a regex pattern that test filenames will match. It is used to determine which files will be visible on a problem's test-suite page on the exercism.io site. The default value used if this key is not present is `/test/i`.
* **ignore_pattern** (string) _(optional)_ a regex pattern that will cause files matching it to not be served by the `exercism fetch` command. The default value used if this key is not present is `/example/i`.
* **solution_pattern** (string) _(optional)_ a regex pattern that matches solution files in the track repository. If not present, it defaults to `/[Ee]xample/`

## Exercise metadata

The `exercises` consists of an array of objects, each of which defines the metadata for an exercise.

Each object consists of the following keys:

* **uuid** (string) - this must be unique to this exercise across all of Exercism's tracks, and must never change. This can be generated using any UUID generator tool. If you don't have a favorite, try [uuidgenerator.net](https://www.uuidgenerator.net/).
* **slug** (string) - this must be unique _within_ a track, but can exist in multiple tracks. The slug can change.
* **core** (boolean) - whether or not this exercise is part of the core series of exercises for the track. If you complete all the core exercises in a track, you complete the track. Exercises that are not core are optional. Each core exercise will ideally unlock several exercises.
* **unlocked_by** (string) - for exercises that have `"core": false`, the slug of the exercise that is a prerequisite for getting access to this exercise.
* **difficulty** (integer) - a rough estimate of the difficulty level of the exercise on a scale of 1 to 10.
* **topics** (array of strings) - topics covered in this exercise

Exercises can be deprecated, in which case they must have the following:

- **uuid**
- **slug**
- **deprecated** (boolean, true)

All other fields in deprecated exercises can be deleted.

## Dependencies

The `config.json` is used by [trackler][], which is a light wrapper around the entire Exercism curriculum, and [configlet][], which is the tool that we use to verify the configuration.

## Automated verification of `config.json`

We have [automated linting of the track configuration][configlet-lint].

[configlet-lint]: /language-tracks/configuration/linting.md
[trackler]: https://github.com/exercism/trackler
[configlet]: https://github.com/exercism/configlet
