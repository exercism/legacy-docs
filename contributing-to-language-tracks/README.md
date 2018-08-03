# Getting Involved in an Exercism Language Track

[repositories]: http://exercism.io/repositories
[triaging-issues]: /you-can-help/triage-issues.md
[reviewing-prs]: /you-can-help/review-pull-requests.md
[porting]: /you-can-help/implement-an-exercise-from-specification.md
[problem-specifications]: https://github.com/exercism/problem-specifications
[blazon]: https://github.com/exercism/blazon
[blazon-process]: /you-can-help/improve-exercise-metadata.md
[fixing-readmes]: /language-tracks/exercises/anatomy/readmes.md

The Exercism language tracks are a great way to get involved in:

- A programming language you love.
- A programming language you're curious about.
- Open source (in general).

_If you haven't used Exercism before, then it could be worth submitting solutions to a couple of exercises._
_It doesn't matter which language track you submit to, it's just to get a feel for what a language track consists of._

## About the language tracks

Each language track lives in its own repository, which means that you can contribute
to a track without having to know anything about the rest of the Exercism ecosystem.

Also, each track is focused, containing implementations of trivial exercises and the tools
to make development easier, so there's no big codebase to get acquainted with.

You can see a list of all the available tracks by looking at the [exercism-track topic on the Exercism org](https://github.com/search?q=topic%3Aexercism-track+org%3Aexercism&type=Repositories) on GitHub.

Some tracks are active on the website (see https://exercism.io/#explore-languages if logged out, or http://exercism.io/tracks regardless of whether you're logged in). Tracks that are not active on the site are either in progress, or someone was optimistic but it never got any traction and they didn't get it to the point where it could launch.

## Ways to contribute

There are a number of ways to contribute to a track. All of them are sorely needed, and greatly appreciated!

First, orient yourself.
Read the README, and look through the open issues and pull requests, and get a feel for what's going on.

You can pick up an open issue, or help with:

* Improving product-facing copy/documentation
* Improving contributor-facing documentation and tooling
* Improving existing exercises
* Adding more exercises
* Triaging issues
* Review pull requests

### Improve product-facing copy/documentation

The main introduction page for a track can be seen on the website by going to https://exercism.io/tracks/$TRACK_ID.

For example, here's the [R track](https://exercism.io/tracks/r).

There are three pieces of content that come from the track repository:

- the blurb, which is right under that track name in the header. It lives in `config.json` as a top-level key "blurb".
- the "about" section, which is in `docs/ABOUT.md`
- the code example, which is in `docs/SNIPPET.txt`

We also have guides that are linked to from each exercise page:

- Installing the language (`docs/INSTALLATION.md`)
- Running the tests (`docs/TESTS.md`)
- Learning the language (`docs/LEARNING.md`)
- Useful language resources (`docs/RESOURCES.md`)

### Improve contributor-facing documentation

It's not always obvious how to get started contributing to a language track.
As you get involved, help improve the README in the track repository.

* Are there undocumented dependencies?
* How do you run the tests? Is there a way to run all the tests for all the exercises?
* Are there any naming conventions for files or types or classes or functions?
* Is there any tooling that we're using? Linters?
* Is there continuous integration? Are there any gotchas?

### Improve existing exercises

#### Exercise READMEs

If the README is ambiguous or confusing, then there's almost certainly
something we can do to clarify.

Or maybe you found a typo (you wouldn't be the first).

The READMEs are generated, and all the details are explained [here][fixing-readmes].

#### Test Suites

* Did the test suite force you towards a certain solution? (It shouldn't.)
* Did you come across a solution that passed the tests, but that had a bug?
  (Maybe we're missing a test case.)

The test suite is straight forward to find: look in the `exercises`
directory in the language track repository for the directory named after the
slug of the exercise. The test file will be right there.

That said, some test suites are generated based on the `canonical-data.json`
file found in [problem-specifications][]. The README for the language track repository
should tell you what you need to know.

For every change that you make to the test suite, ask yourself: **Should this
change also affect other language tracks that implement the same exercise?**

If you think it might, open a discussion in the [problem-specifications][] repository and get
other track implementors' feedback on the subject.

If this change should affect the broader Exercism curriculum, then use the
issue in [problem-specifications][] to:

- Hash out all the details together.
- Figure out the necessary changes to the `canonical-data.json` for the
  exercise (if it exists).
- Draft an issue that can be submitted to all the tracks that implement the
  exercise using the [blazon][] tool (which automates the tedious parts).
  More about that [here][blazon-process].

#### Exercise metadata

Exercises have topics and a difficulty score in the `config.json` file in the track.
These are used to help filter exercises on the site.

#### Reordering Exercises

We don't have a formal process for deciding how the exercises should be
ordered.  We also don't have any particular guidelines yet, about which
optional exercises should be unlocked by which core exercises.

The order of the core exercises is decided by the `exercises` array in `config.json`.

### Adding Hints

Sometimes an exercise is in the right place in the sequence, but it's really
hard to figure out how to solve it anyway.

In this case consider whether there's a blog post or some documentation that
you could point people to, and add it to `$ROOT/exercises/$SLUG/.meta/hints.md` in the exercise directory
in the language track. If the file doesn't exist, create a new one.

### Add new exercises

The easiest way to add a new exercise is to find an exercise that has already been implemented in another language
track, and port it over to your target language.

We've got [a guide][porting] that walks you through how to find an exercise to port, and the things to
keep in mind when implementing it.

### Triage issues

A great issue is detailed and actionable.
When they're not, you can help ask the questions to make them so.
For more detailed suggestions about things to keep in mind when triaging, check out [this documentation][triaging-issues].

### Review pull requests

We always need more eyeballs on pull requests. On language tracks most pull requests tend to be related to
the exercises themselves, and we have [detailed documentation][reviewing-prs] that should help
you get started with code reviews.

## Want to help keep an eye on things?

We can always use an extra pair of eyes.
Go to the repository for the language you've chosen, click the _Watch_ button, and select _Watching_.
This will notify you of any new issues, pull requests, or comments in the repository, which is a great way
of getting acquainted with the people involved and the issues that tend to come up.

