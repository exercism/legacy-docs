# Implement the first exercise

This will likely be a program that outputs _Hello, World!_.
In some rare cases, this might not be the best choice.
If so let's discuss how to proceed.

The point of this exercise is to quickly make sure that everything is wired together correctly.
This will confirm that the user has the programming environment installed correctly, that they know how to run the tests, and are able to make it pass.
Beyond this, it also ensures that they have the Exercism command-line client (CLI) installed and configured, and that the site delivers the correct files for the exercise without delivering any unnecessary artifacts.
Lastly it ensures that the user is familiar with the cycle of downloading an exercise using the CLI, solving a problem in their local development environment, and submitting their solution back to the site.

In other words, this isn't really about learning anything about the language itself yet.
We're aiming for something dead simple.

This section assumes that the exercise is a literal _Hello, World!_ program based on the [Hello World problem specification](https://github.com/exercism/problem-specifications/blob/master/exercises/hello-world/).

We're going to need:

* a directory for the exercise
* a test suite
* a (complete) reference solution
* a stub (incomplete) solution
* a README (generated)
* some configuration

## Create the directory

Each exercise gets its own directory within the `exercises` directory.
Create a directory named `hello-world`.

```
exercises/hello-world/
```

## Write the test suite

The typical implementation of Hello World is [described in the canonical-data.json](https://github.com/exercism/problem-specifications/blob/master/exercises/hello-world/canonical-data.json) file.
There is usually just one test, and it expects the string "Hello, World!".

The test suite can live in a file directly in the `hello-world` directory, or you can create subdirectories if that makes sense for the language. E.g. in Java convention would put the test suite in `exercises/hello-world/src/test/java/HelloWorldTest.java`.

Do whatever is idiomatic for the lanugage, but keep it as simple as reasonably possible.

The test should be failing at this point.

## Write the reference solution

Write a solution that passes this test.
This is not going to be delivered to the user, it's only used to verify that the test suite is in good shape.

Once it's working, copy the reference solution into a directory called `.meta` within the `hello-world` directory.
This might not ultimately be where the reference solution lives, but for now it's a good start.

There are two common strategies for naming the reference solution file so it is identifiable as such.
First, you can give the file a specific name, e.g. `example-solution.ext`.
Or, you can name the file the way you would in a real program (e.g. `hello-world.ext`), and use the containing path to identify it as the reference solution (e.g. (`solution/hello-world.ext`).

Here's what your exercise directory might look like at this point.

```
exercises/
└── hello-world
    ├── .meta
    │   └── reference
    │       └── hello-world.ext
    ├── hello-world.ext
    └── hello-world-test.ext
```

## Implement the stub solution

The stub solution should be the reference solution, but with the actual "Hello, World!" missing.
People should not have to worry about how to write the basic syntax, only fill in the blank.

This is the file that the test suite should be looking for by default.

If you run the tests now, they should be failing again.

Eventually we're going to need some tooling that will let us run the test suite against the reference solution without stomping on any existing files, but don't worry about that quite yet.

## Create the README

The README gets generated from a few different pieces.
At minimum you'll need:

- the README template
- a local copy of the problem-specifications repository
- the Configlet tool

These are described below.
You can also find more detail in the reference documentation about [exercise readmes](https://github.com/exercism/docs/blob/master/language-tracks/exercises/anatomy/readmes.md).

### The README template

You should have a `config` directory at the root of your repository, containing a file named `exercise_readme.go.tmpl`.
If you don't, then your repository might have been bootstrapped before we introduced the README templates.
You can copy whatever you're missing from the [exercism/request-new-language-tracks](https://github.com/exercism/request-new-language-track/tree/master/config) repository, which we use to bootstrap new track repositories.

By default the template uses metadata from the problem-specifications repository to put together the README.
It can include other stuff, too, but for now just get the basics wired together.

### The problem specification

Clone the [problem specifications repository](https://github.com/exercism/problem-specifications).
Configlet expects the track repository to live side-by-side with the problem-specifications repository.

```
.
├── your-track
│   └── exercises
│       └── hello-world
│           ├── .meta
│           │   └── reference
│           │       └── hello-world.ext
│           └── hello-world-test.ext
└── problem-specifications
    └── exercises
        └── hello-world
            ├── canonical-data.json
            ├── description.md
            └── metadata.yml
```

It's possible to override this location if you need to.

### The Configlet tool

Download the [latest release of Configlet](https://github.com/exercism/configlet/releases/latest), extract the archive, and put it in your PATH.

Generate the README for the exercise with the command:

```
configlet generate <path/to/track-repository> --only hello-world
```

From within the track repository the command would be:

```
configlet generate . --only hello-world
```

### Exercise configuration

The track has a `config.json` file, which contains an empty `"exercises"` array.
You'll need to add an object to the array following the details the [exercise configuration](/language-tracks/configuration/exercises.md) docs.

Verify the configuration by running `configlet lint .`.
You may need to add some [track-level configuration](/language-tracks/configuration/track.md).

Once `lint` is error free, run `configlet fmt .`, this will format the configuration files `config.json` and `maintainers.json`. Formatting will ensure that both files have consistent JSON syntax and indentation.  Finally, formatting normalizes and alphabetizes the exercise topics within `config.json`.
