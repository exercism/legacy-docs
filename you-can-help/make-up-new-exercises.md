# Implementing a Completely New Exercise

## Generic or Custom

Before adding a new exercise, consider whether this is an exercise that is relevant to just one language, or could be reused or adapted across multiple Exercism language tracks.

If your exercises is relevant to several tracks, then you will create a _generic_ problem specification in a shared repository. If your exercise is relevant only to a specific programming language, then you will create a _custom_ specification within the language track repository.

## Problem Specification

Whether you are creating a generic or a custom exercise, the basic idea is the same. Some details will differ, and these are described in detail below.

* First, choose a name for your exercise. The name must be unique. Verify the list of [generic problem specifications][spec-exercises], as well as the language track in question (navigate to the `exercises` directory in the repository).
* Derive the _slug_ of the exercise from the name by making the name all lowercase and separating words using hyphens.
* Write a _blurb_, which is a one-sentence summary of the problem to be solved.
* Write a more detailed _description_ of the problem to be solved.
* Reference the _source_ of inspiration for the exercise.

The basic problem specification consists of two files. Where these files live will depend on whether you're creating a generic or custom exercise.

The `description.md` contains a general description of the problem to be solved described in plain text, without a title/header. It will likely be two or three paragraphs. Try to make the description independent of any programming language. Think about whether the description would work for someone who wanted to solve this problem on the back of a napkin using pen and paper.

The `metadata.yml` contains the blurb and source. It has the following structure:

```
---
blurb: "A one-sentence summary of the problem to be solved."
title: "An *optional* field containing the name of this exercise if it contains punctuation or capitalization other than the first letter of each word."
source: "A textual description of where this was found, or what inspired it."
source_url: "http://example.com/reference"
```

### Generic Problem Specifications

Generic problem specifications live in the [exercism/problem-specifications][problem-specifications] repository, with the [exercises directory][spec-exercises].

A generic specification consists of three files in a directory named after the slug (`hello-world`, in this case):

```
exercises/
└── hello-world
    ├── canonical-data.json
    ├── description.md
    └── metadata.yml
```

The `canonical-data.json` file contains a set of sample test inputs and outputs that make up a reasonable test suite. Since you are creating a new exercise, you might want to implement a test suite for the track in question and then create the canonical data, based on your discoveries and insights from having written an actual test suite.

Some general guidelines:

* All tests should be essential to the problem.
* Ensure people can get the first test passing easily. Then each following test should ideally add a little functionality. People should be able to solve the problem a little at a time.
* Avoid test cases that don't introduce any new aspect and would already pass anyway.
* The test cases should not require people to follow one very specific way to solve the problem, e.g. the tests should avoid checking for helper functions that might not be present in other implementations.
* Performance tests should not be included in the canonical test data.

The expected format for the `canonical-data.json` file can be found in the [canonical schema](https://github.com/exercism/problem-specifications/blob/master/canonical-schema.json).

Once your pull request to the problem-specifications repository is merged, you can follow the directions for [implementing an exercise from specification][porting-an-exercise].

### Custom Problem Specifications

Within the language track repository, the metadata files need to go in a `.meta` directory within the exercise directory when you submit your implementation of the exercise.

```
exercises/
└── hello-world
    └── .meta
        ├── description.md
        └── metadata.yml
```

Once you've defined these, you can submit them along with your pull request that [implements the exercise][porting-an-exercise].

[problem-specifications]: https://github.com/exercism/problem-specifications
[spec-exercises]: https://github.com/exercism/problem-specifications/tree/master/exercises
[porting-an-exercise]: /you-can-help/implement-an-exercise-from-specification.md
