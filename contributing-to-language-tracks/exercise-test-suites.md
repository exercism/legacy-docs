At the most basic level, Exercism is all about the tests. They drive the user's implementation forward and tell them when the exercise is complete.

The utmost care and attention should be used when adding or making changes to the tests for an exercise. When implementing an exercise test suite, we want to provide a good user experience for the people writing a solution to the exercise. People should not be confused or overwhelmed.

We simulate Test-Driven Development (TDD) by implementing the tests in order of increasing complexity. We try to ensure that each test either

- helps triangulate a solution to be more generic, or
- requires new functionality incrementally.

The characteristics of a good individual test are:

- a clear name or description that reveals the intent of the test
- a minimal amount of setup
  - Temporary variables should be avoided unless they add to the test's clarity.
  - Well named test helpers can be employed to encapsulate shared setup between tests.
  - Test helpers should be extremely simple, and branching logic inside a helper is to be avoided.
- a manageable increase in complexity from the previous passing test 
- introduces a single new requirement
- a minimal number of expectations required to specify the change (one expectation is preferred)
- a readable and understandable failure message
- adherence to the testing idioms of the language and testing framework of the track
- does not duplicate the expectations of another test

The test suite of an exercise should be guided by the common specifications laid out by the `canonical-data.json` file of each exercise in [x-common](https://github.com/exercism/x-common) if it is available. The specifications there provide good defaults for:

- the order of the tests
- the descriptions of the tests
- the inputs and expected outputs of each test

Feel free to implement a test generator for your track if you feel it would aid in creating test suites from `canonical-data.json`.

The specifications in `canonical-data.json` are the strongly recommended defaults, but if you have a good reason (language idioms, etc) then don't hesitate to deviate from them.

If there is no `canonical-data.json` file for the exercise then we recommend using  http://x.exercism.io/problems/hello-world (replace hello-world with the exercise in question) or http://exercism.io/languages/vimscript/todo (replace vimscript with your track) to find other implementing tracks.
