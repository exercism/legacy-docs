# Tooling and continuous integration

We typically implement a track test suite that can run both locally and on Travis CI.
The track test suite should verify that each exercise makes sense, by running the exercise tests against the example solution.

**Definition of terms**

- **exercise test suite**: the test suite that is delivered to Exercism users as part of an Exercism exercise
- **track test suite**: the test suite that helps ensure that all of the exercise test suites in a language track are solvable

**Background**

When implementing an exercise test suite, we want to provide a good user experience for the people writing a solution to the exercise. People should not be confused or overwhelmed.

In most Exercism language tracks, we simulate Test-Driven Development (TDD) by implementing the tests in order of increasing complexity. We try to ensure that each test either

- helps triangulate a solution to be more generic, or
- requires new functionality incrementally.

Many test frameworks will randomize the order of the tests when running them. This is an excellent practice, which helps ensure that subsequent tests are not dependent on side effects from earlier tests. However, in order to simulate TDD we want tests to run *in the order that they are defined*, and we want them to *fail fast*, that is to say, as soon as the test suite encounters a failure, we want the execution to stop. This ensures that the person implementing the solution sees only one error or failure message at a time, unless they make a change which causes prior tests to fail.

This is the same experience that they would get if they were implementing each new test themselves.

Most testing frameworks do not have the necessary configuration options to get this behavior directly, but they often do have a way of marking tests as _skipped_ or _pending_. The mechanism for this will vary from language to language and from test framework to test framework.

Whatever the mechanism—functions, methods, annotations, directives, commenting out tests, or some other approach—these are changes made directly to the test file. The person solving the exercise will need to edit the test file in order to "activate" each subsequent test.

Any tests that are marked as skipped will not be verified by the track test suite unless special care is taken.

Additionally, in some programming languages, the name of the file containing the solution is hard-coded in the test suite, and the example solution is not named in the way that we expect people to name their files.

We will need to temporarily (and programmatically) edit the exercise test suites to ensure that all of their tests are active. We may also need to rename the example solution file(s) in order for the exercise test suite to run against it.

**Avoiding accidental git check-ins**

It's important that if we rewrite files in any way during a test run, that these changes do not accidentally get checked in to the git repository.

Therefore, many language tracks write the track test suite in such a way that it _copies_ the exercise to a temporary location outside of the git repository before editing or rewriting the exercise files during a test run.

**Working around long-running track test suites**

Usually as people are developing the track, they're focused on a single exercise. If running the entire track test suite against all of the exercises takes a long time, it is often worth making it possible to verify just one exercise at a time.

**Example build file**

The PHP track has created a [Makefile][make]. The Ruby track uses Rake, which is a tool written in Ruby, allowing the track maintainers to write custom code in the language of the track to customize the build with a [Rakefile][rake].

[make]: https://github.com/exercism/xphp/blob/master/Makefile
[rake]: https://github.com/exercism/xruby/blob/master/Rakefile
