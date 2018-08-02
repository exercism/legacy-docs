# Anatomy of an exercise

Exercises on Exercism typically are an implementation of an existing problem, as described in the [problem-specifications](https://github.com/exercism/problem-specifications) repository.

Each exercise must be implemented in a directory within the `./exercises` which can be found in the root of the repository.

The directory must be named with kebab-case (lowercase, hyphenated).
All the files within it can be named to match the conventions of the language.

In order to integrate with the command-line client and the website, a few things need to be in place:

- an [exercise README](readmes.md)
- a [test suite](test-suites.md)
- a [reference solution](reference-solution.md)

If the exercise needs any supporting files such as boilerplate, header files, etc, these can be added in the exercise directory tree.
They will automatically be delivered along with the test suite and README.
