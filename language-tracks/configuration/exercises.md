# Exercise configuration

The `exercises` consists of an array of objects, each of which defines the metadata for an exercise.

## The exercise object

Each object consists of the following keys:

* **uuid** (string) - a unique identifier across all Exercism tracks
* **slug** (string) - a unique, human-readable identifier _within_ the track
* **core** (boolean) - whether or not this exercise is part of the core set of exercises necessary to complete the track
* **unlocked_by** (string) - the core exercise that an optional exercise depends on
* **difficulty** (integer) - a rough estimate of the difficulty level of the exercise on a scale of 1 to 10.
* **topics** (array of strings) - topics covered in this exercise

The UUID must never change once the track has been added to the site.
All other values can be updated.

### UUID

This must be unique to this particular exercise implementation across all of Exercism's tracks, and must never change.
[Configlet][configlet] has a `uuid` subcommand (`configlet uuid`), but you can use any UUID generator tool to create it.

### Slug

The slug is used in a lot of places: URLs, directory names, as options to commands on the command line, and more.
It is a normalized, human-readable version of the exercise name and must be unique within a given track.
In other words you wouldn't have two `clock` exercises in the same track, but you might have a `clock` exercise in lots of different language tracks.

You can change the slug for an exercise.
This will not break anything for people who have submitted solutions to the exercise, as long as the UUID remains the same.
You'll need to make a few changes in the project outside of just editing the slug in the `config.json` file.
Let `configlet lint .` guide you.

### Core

Each track consists of a set of 8-20 core exercises.
In order to complete the track, you must complete all of the core exercises.

Each core exercise should ideally unlock a handful of optional exercises.

For more about why we've structured the tracks in this way, read the [Progression](/about/conception/progression.md) document.

### Unlocked by

Any exercise that is not a core exercise is optional.
All optional exercises should be unlocked by one of the core exercises.
Set the value of `unlocked_by` to the slug of the core exercise that is the prerequisite for getting access to this exercise.

### Difficulty

We show the difficulty of an exercise on the website.
This lets people filter and choose when they have a lot of optional exercises available to them.

A rough estimate will do.
Use a scale from 1 to 10.

### Topics

We show the topics for an exercise on the website.
This lets people optimize the learning experience to their own interests—skipping topics that they are not interested in, or that they already know a lot about, and doing deeper dives into topics that they're curious about.
Take a look at the (non-exhaustive) [topics list][topics] for suggestions of topics to add.

## Deprecating exercises

Exercises can be deprecated, in which case they must have the following:

- **uuid**
- **slug**
- **deprecated** (boolean, true)

All other fields in deprecated exercises can be deleted.

[configlet]: /language-tracks/configuration/configlet.md
[topics]: https://github.com/exercism/problem-specifications/blob/master/TOPICS.txt
