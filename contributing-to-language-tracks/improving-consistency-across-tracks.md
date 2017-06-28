# Improving Consistency Across Tracks

[blazon]: https://github.com/exercism/blazon
[problem-specifications]: https://github.com/exercism/problem-specifications/tree/master/exercises

## Canonical Data

Each exercise has a generic, language-agnostic problem description, which
can then be implemented in any of the Exercism language tracks.

A great test suite will help people solve the problem gradually.

We want to avoid

* too much redundancy
* steps that are too big

Once we've found a good set of tests, we formalize the inputs and outputs and
store it in a file called `canonical-data.json` alongside the language-agnostic
problem description in the [problem-specifications][] repository.

This makes it easier to port the exercises to new language tracks, as well as
propogate changes to the exercises that have already been implemented in
many tracks.

## Extracting Canonical Test Data

Each of the exercises in the [common pool of exercises][problem-specifications-exercises] can have a
`canonical-data.json` file alongside the other files defining the exercise:

```
exercises/<slug>/
├── canonical-data.json
├── description.md
└── metadata.yml
```

This JSON file should contain the generic (i.e. language independent) test data for that exercise.

There are [open issues][canonical-data-issues] for all of the exercises that are missing canonical data.
The open issue has a link to a page that contains an up-to-date list of all the language tracks that
have implemented the exercise, as well as links to view the implementations.

Open each implementation in a separate browser tab. Navigate to the test files and read through the tests.
Look for test cases that all/many of the languages have in common and identify outliers that only appear in one or two languages.

Based on your findings, decide on a sensible set of test cases.

Here are some considerations that may help:

* Try to stick to test cases that already occur in many languages so it is feasible for the track maintainers to adapt to the canonical set.
* All tests should be essential to the problem. Ensure people can get the first test passing easily. Then each following test should ideally add a little functionality. People should be able to solve the problem a little at a time. Avoid test cases that don't introduce any new aspect and would already pass anyway.
* The test cases should not require people to follow one very specific way to solve the problem, e.g. the tests should avoid checking for helper functions that might not be present in other implementations.
* Performance tests should not be included in the canonical test data.

Once you've decided on a set of test cases, create the `canonical-data.json` file following the guidelines in [problem-specifications's README][data-format-docs].

If you are unsure about any of the considerations make a pull request with an initial proposal and ask the community for help.

## Using Canonical Data to Implement Exercises

When porting an exercise to a language track, the canonical data file
makes it easy to select and implement test cases.

If the track uses test generators (check the README), then you may want to
write a generator rather than hand-code the test suite.

Some things vary from language to language, so don't feel constrained
to implementing exactly what is in the `canonical-data.json` file.

## Evolving Exercises

Over time we find that the problem definitions can be improved in various ways.

When they do, we need to notify all of the tracks that have an implementation
of that problem so that they can update it.

We've built some tooling for this, [blazon][blazon], to make it easier to manage.

The process goes like this:

**Open an issue** in the problem-specifications repository describing the problem, the fix,
and the reasoning behind it. Link to any relevant discussions. This is the _parent
issue_.

In the comment of the issue, **draft the body of an issue** which will be
submitted to each of the language tracks that have implemented this problem.

This should contain:

- a description of the edge case or change
- explicit instructions about what change to make
- a note saying "if this isn't relevant in this language track, close the
  issue"
- a link to the canonical data (if it exists)
- a link to the parent issue.

Linking back to the parent issue is important for two reasons:

1. It provides context. If someone wants to know more about the issue,
   they can follow links to read the history.
2. It will show a _living TODO list_. The parent issue will have a list
   of links to the open issues, showing whether the issue is open or
   closed. Once all of the child issues are closed, then we can
   close the parent issue.

It's worth drafting this in a comment because other people will often weigh in
to help make it as clear as possible, or add any missing context, and it's
easier to fix this _before_ it get submitted to a bajillion different repos.

**Create a text file** containing the issue template that you drafted.

The first line of the file will be used as the issue title. Make it
descriptive. It should contain the slug of the relevant exercise.

**Download [blazon][blazon]** and use it to submit the issue.

    $ blazon -exercise=<slug> -file=<filename>


[problem-specifications-exercises]: https://github.com/exercism/problem-specifications/tree/master/exercises
[canonical-data-issues]: https://github.com/exercism/problem-specifications/issues?utf8=%E2%9C%93&q=is%3Aissue%20is%3Aopen%20label%3A%22cross-track%20consistency%22%20canonical-data.json
[data-format-docs]: https://github.com/exercism/problem-specifications#test-data-format-canonical-datajson
