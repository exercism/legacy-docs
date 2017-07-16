# Exercises

Each exercise should be implemented idiomatically for the language in question.
Keep the [goals of Exercism][goal] in mind when considering new exercises or changes to existing ones.

**Exercises should not enforce a single way to solve the problem, if possible.** The more interesting exercises allow several approaches, and create rich opportunities for discussing trade-offs when people submit their solutions.

Sometimes it's tempting to expand the exercise to cover more cases or a broader topic.

This might be the right thing to do. Or it might add more work with little additional value. The right answer might also be to invent a new exercise to cover the proposed ideas. Consider whether this should be discussed just among the maintainers of a single language track, or whether it should be raised to all track maintainers via an issue in the [problem-specifications][] repository.

Don't be afraid to skip (or 'forego') exercises that don't make sense in the language, or that are not particularly interesting.

For more nitty-gritty details about what to consider concerning exercises, see [reviewing pull requests](/you-can-help/review-pull-requests.md).

## Files

Each exercise has corresponding metadata in the track's [`config.json`][config-json]. Use the slug to define the directory name for the exercise.

Further, the exercise should contain:

* a test suite containing automated tests that define the requirements for completing the exercise.
* a README describing the exercise to the user, along with any hints or instructions to help them solve it.
* a `.meta` directory containing any files that are required to define the exercise, but which should not be delivered to the user.

```
exercises/
└── foo/
    ├── .meta
    │   ├── example-solution.ext   # (required)
    │   ├── description.md         # (maybe)
    │   ├── metadata.yml           # (maybe)
    │   ├── hints.md               # (optional)
    │   └── readme.go.tmpl         # (optional)
    ├── hello-world-test.ext
    ├── hello-world.ext
    └── README.md # (generated)
```

The `.meta` directory may contain:

* _(required)_ a reference solution which can be used to verify the soundness of the exercise test suite.
* _(optional)_ a `readme.go.tmpl`, used to generate the README if it does not use the track's general exercise README template.
* _(optional)_ a `hints.md` file, where hints to the user about the exercise can be added to be included in the exercise README. If you have a `readme.go.tmpl` file, you can include the hints directly in the template. The `hints.md` file is useful if the exercise relies on the track-level template.
* _(it depends)_ a problem specification. These files are only necessary if the exercise is not based on a specification from the [shared pool of problem specifications][problem-specifications].
  * `metadata.yml`
  * `description.md`

Read more about [exercise READMEs][readmes], [test suites][tests], and the [reference solution][solution].

[problem-specifications]: http://github.com/exercism/problem-specifications
[goal]: /about/goal-of-exercism.md
[config-json]: /language-tracks/configuration/README.md
[readmes]: /language-tracks/exercises/anatomy/readmes.md
[tests]: /language-tracks/exercises/anatomy/test-suites.md
[solution]: /language-tracks/exercises/anatomy/reference-solution.md
