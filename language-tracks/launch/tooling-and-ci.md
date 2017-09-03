# Tooling and continuous integration

Since reference solutions tend to not be named what the code expects, and they don't live where the test suite expects to find them, we often need to write a bit of extra tooling to make it easy to work on the exercises as a maintainer or contributor.

There are two use cases that we want to account for:

- make it easy to run all the exercises against their respective reference solutions with a single command
- make it easy to run a single exercise test suite against it's reference solution for a faster feedback cycle when working on a particular exercise

You might find that you need to copy some files around to get everything set up relative to each other.
Sometimes your script will need to edit something in the test suite to get it to find or recognize the reference solution.

Either way, you don't want to move things around or edit things in place within the repository.
That's a recipe for accidentally committing the changes.

If you do need to move, rename, or edit, your best bet is to write a script that copies everything into a temporary directory, and does it there.
Then you can just delete the temporary directory instead of worrying about putting things back the way they were.

## Continuous integration

By default we use Travis CI.
If we have Windows-specific stuff we'll use AppVeyor, and for Mac-specific stuff we'll use Circle CI.
We're not tied to any of these choices, it's just the way things have worked out.
If you want to use some other service, that's fine.

CI should do a few things:

- run the track-level linting to make sure that the track is configured correctly
- run the full test suite for all the exercises to make sure that all the exercises make sense

For a couple of examples, check out the PHP track, which uses [make][], and the Ruby track which uses [rake][].

[make]: https://github.com/exercism/php/blob/master/Makefile
[rake]: https://github.com/exercism/ruby/blob/master/Rakefile
