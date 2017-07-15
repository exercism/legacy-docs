# Pull Request Guidelines

1. Put the name of the exercise in the subject line of the commit.
   E.g. `hamming: Add test case for strands of unequal length`
1. The subject line should be a one-sentence summary, and should not include
   the word *and* (explicitly or implied).
1. Any extra detail should be provided in the body of the PR.
1. Don't submit unrelated changes in the same pull request.
1. If you had a bit of churn in the process of getting the change right,
   squash your commits. Refer to the guidelines on [squashing commits](/contributing/git-basics.md#squashing).
1. If you had to refactor in order to add your change, then we'd love to
   see two commits: First the refactoring, then the added behavior. It's
   fine to put this in the same pull request, unless the refactoring is
   huge and would make it hard to review both at the same time.
1. If you are referencing another issue or pull-request, for instance
   *closes #XXX* or *see #XXX*, please include the reference in the body of the PR,
   rather than the subject line. This is simply because the subject line doesn't
   support markdown, and so these don't get turned into clickable links. It makes
   it harder to follow and to go look at the related issue or PR.
1. Please also refer to the guidelines for [commit messages](/contributing/git-basics.md#commit-messages).

Once you've submitted a pull request, one or more of the track maintainers
will review it. Some tracks are less active and might not have someone
checking in every day. If you don't get a response within a couple of days,
feel free to ping us in the [support
chat](https://gitter.im/exercism/support).
