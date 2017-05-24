# Exercise READMEs

[x-common]: http://github.com/exercism/x-common/tree/master/exercises
[trackler]: https://github.com/exercism/trackler
[trackler-readme]: https://github.com/exercism/trackler/blob/master/lib/trackler/implementation.rb#L40-L42

READMEs are automatically generated in the [trackler][] gem, which is a
light-weight wrapper around all of the exercise data for all of the Exercism
tracks.

The READMEs are assembled from files that live in different repositories:

* `description.md` contains the basic description of the problem
* `metadata.yml` contains some generic metadata about the problem
* `TRACK_HINTS.md` (or `SETUP.md`, which is the deprecated name of this file) contains hints that apply to all exercises in a given language track
* `HINTS.md` contains hints that only apply to a single exercise

In addition, there's some hard-coded, generic stuff that lives in the
[file that assembles the README][trackler-readme] within the trackler gem.

To complicate matters, an exercise might be based on one of the problem specifications in the [common pool][x-common],
or it could be a custom exercise invented just for the track in question.

The first thing to check is whether or not this comes from the common pool of exercises. If so, it will appear in the
[`exercises` directory of the common pool][x-common].

If it exists you'll see a directory for the exercise, which contains the `description.md` and the `metadata.yml`. The
directory may also contain other files.

For example, for an exercise named `foo` from the common pool, you'll find the files in `exercises/foo`.

```
$ tree x-common/exercises/foo/
x-common/exercises/foo/
├── description.md
└── metadata.yml
```

If the exercise is _not_ one of the exercises from the common pool, then those two files will live in the `.meta` directory
of the exercise implementation within track itself.

For example, for an exercise named `bar`, you'll find the files within `exercises/bar/.meta`:

```
$ tree -a the-track/
the-track/
└── exercises
    └── bar
        ├── .meta
        │   ├── description.md
        │   └── metadata.yml
        └── bar_test.ext
```

The other two files, `TRACK_HINTS.md` (or `SETUP.md`) and `HINTS.md` will both be in the track's repository.

`TRACK_HINTS.md` is at the root of the repository, whereas `HINTS.md` will either be in the directory of the
exercise implementation, or in the `.meta` directory.

If the text you're trying to fix is not in any of those files, then you'll need to look at the hard-coded
text in the [Trackler file that assembles the README][trackler-readme].

## Philosophical Considerations

### Description

The problem specification (`description.md`) treads a very fine line between useful ambiguity and confusing vagueness.
Because the problem description is the same whether you're solving the problem in C++ or
in Lua, it needs to be high-level enough to allow for the syntactic, semantic, and philosophical
differences in the various languages.

Within this purposeful ambiguity lies opportunities for making an exercise description more clear.

Typical issues to be attentive to:

- poorly worded sentences
- outdated information
- incorrect directives
- typos

### Track Hints

The `TRACK_HINTS.md` (or `SETUP.md`) gets included in _all_ the exercise READMEs for the track,
and mustn't refer to specific problems or files.

It should contain helpful, generic information about solving an exercism problem in the target language,
for example hints about how to run the tests or where to get help.

### Exercise Hints

Anything that is specific to just one exercise, should be added to the `HINTS.md` file.
