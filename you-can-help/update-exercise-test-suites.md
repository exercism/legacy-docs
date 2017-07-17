# Updating an Exercise Test Suite

Once you [find the correct repository](#language-track-repositories),
you can [fork it](https://help.github.com/articles/fork-a-repo/) and then [clone it](https://help.github.com/articles/cloning-a-repository/).

The README in each individual language track repository covers how to set
up the development environment for that language.

Often all you need is a running language environment along with the relevant
testing library.

If the test suite was generated, then editing the solution will require a
couple of extra steps. This is covered in detail in a [separate section of
this guide](#updating-a-generated-test-suite).

The test suite is usually named with _test_ or _Test_ in the filename, though
some language tracks have other conventions (e.g. _spec_ is fairly common, and
sometimes it's just a matter of a different file extension).

If you're unsure where to make the change, ask us, and we'll help you figure it out.

Once you've updated the test suite, there are a few things you'll want to check.

- Make sure the [reference solution](#reference-solution) is still passing.
- If the exercise is [versioned](#exercise-versioning), and the change will
  mean that existing solutions on the site will not pass the new tests, then
  increment the version number, both in the test and in the reference solution.
- Run the full, track-level test suite, if available.
  If the track has a way to automatically run all the tests against their
  reference solutions, it will be documented in the README.
- Run [configlet](#track-level-linting-with-configlet), the track-level linter.

You can also take a look at the `.travis.yml` file to see what the continuous
integration system will do to verify the track.

Take a look at our [pull request guidelines](#pull-request-guidelines).
You don't need to get it perfect the first time around; we'll work with you to
get the patch merged.

## Updating a Generated Test Suite

Some language tracks are experimenting with generating test suites from shared
test data. This is because various interesting edge cases are discovered as
people discuss solutions, but these edge cases are usually then only added
to a single language track. By standardising the inputs and outputs, it becomes
easier to improve the exercises across all the languages.

There are two possible scenarios, described below.

1. You want to change or add inputs or outputs.
1. You want to change something about the test suite itself.

Once you've made the change, then follow the instructions about verifying your change
and submitting a patch as described above, in the section about [updating an exercise
test suite](#updating-an-exercise-test-suite).

### Changing Inputs and Outputs

If you want to add a new test or change some inputs or outputs, then the change
needs to be made in the [exercism/problem-specifications repository](https://github.com/exercism/problem-specifications),
not directly to the test suite itself.

Find the JSON file for the problem in question. For example, if you want to change
the Clock problem, then look for `exercises/clock/canonical-data.json`. Each 
change should also bump the version of the test data. For more information,
see the [test data versioning](README.md#test-data-versioning) section of the 
README.

Submit a pull request with the change.

When that pull request has been merged, then the various languages that implement that
problem will need to have their test suites regenerated. Track maintainers can do this,
though we're always happy if you want to submit a patch with the regenerated test suite.

The instructions for regenerating a test suite should be described in the README
of the language-specific repository.

Follow the guidelines for setting up a development environment, verifying the change,
and submitting a pull request, as described in the [main section about updating an
exercise test suite](#updating-an-exercise-test-suite).

### Changing the Structure

If you are not changing inputs/outputs, but rather the structure of the test suite,
then that change will need to be made within the generator itself. It lives in
the language-specific repository along with the exercises, and the process for
regenerating the exercise should be described in the README of the repository.

Follow the guidelines for setting up a development environment, verifying the change,
and submitting a pull request, as described in the [main section about updating an
exercise test suite](#updating-an-exercise-test-suite).
