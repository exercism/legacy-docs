# READMEs

Exercise READMEs are generated and committed to the repository.

## Generating a README

### Setup

Install [configlet][]. You will need version 3.0.0 or higher.

If any of the exercises in the track are based on problems in the [problem-specifications][] repository, then you will
need to have a copy of that repository locally on disk, in the same directory as your track.

```
.
├── the-track/
└── problem-specifications/
```

### Generation

Assuming that you are in the root of the track repository, generate the README for an exercise with the slug `foo` using the following command:

```
configlet generate . --only foo
```

The command is build up as follows:

* `configlet` - the name of the tool
* `generate` - the subcommand that directs the tool to generate READMEs
* `.` - the path to the root of the repository
* `--only foo` - a flag specifying which exercise to generate. If you leave off the flag, the tool will generate all the READMEs.


## The README Template

Each track has a default template in `$TRACK_ROOT/config/exercise-readme.go.tmpl`, and an exercise may override that template by creating a `$TRACK_ROOT/exercises/$SLUG/.meta/readme.go.tmpl` file.

The template is written using Go's [text/template][text-template] package.

There are a number of values available in the template:

`.Spec` represents the problem specification, which is either a shared specification from [problem-specifications][], or a custom specification found in the exercise's `.meta` directory. The following values on `.Spec` can be referenced within the template:

- `.Spec.Slug` - the exercise's slug
- `.Spec.Name` - the wordified slug
- `.Spec.Description` - the contents of the optional `$TRACK_ROOT/exercises/$SLUG/.meta/description.md` file
- `.Spec.Source` - a textual description of where the idea for the exercise came from (optional)
- `.Spec.SourceURL` - a link to something about the source (optional)
- `.Spec.Credits` - combines source and source_url into a readable bit of metadata

In addition to the values on `.Spec`, there are two additional bits of text that can be included:

- `.Hints` - the contents of the optional `$TRACK_ROOT/exercises/$SLUG/.meta/hints.md` file.
- `.TrackInsert` - the contents of the `$TRACK_ROOT/config/exercise-readme-insert.md` file.

### Go's Text/Template Package

You don't need much of the Go text/template language. The three things that are used in the default template are probably all you need:

* `{{ .Something }}` outputs a value
* `{{ with .Something }} ... {{ . }} ... {{ end }}` will conditionally output contents between the `with` and `end` markers if `.Something` is not empty. To refer to the value of `.Something`, use `{{ . }}`. The `...` represents any text that you want to output there.
* `{{-` and `-}}` remove preceding and following whitespace.

### Default Template

The default contents of `$TRACK_ROOT/config/exercise-readme.go.tmpl` is below.

```
# {{ .Spec.Name }}

{{ .Spec.Description -}}
{{- with .Hints }}
{{ . }}
{{ end }}
{{- with .TrackInsert }}
{{ . }}
{{ end }}
{{- with .Spec.Credits -}}
## Source

{{ . }}
{{ end }}
## Submitting Incomplete Solutions
It's possible to submit an incomplete solution so you can see how others have completed the exercise.
```

## Philosophical Considerations

### Description

The problem descriptions in the [problem-specifications][problem-specifications] repository tread a very fine line between useful ambiguity and confusing vagueness. Because the shared problem description is the same whether you're solving the problem in C++ or in Lua, it needs to be high-level enough to allow for the syntactic, semantic, and philosophical differences in the various languages.

Having said that, each track is free to write a more specific description if they want to by creating their own `description.md` file and placing it in the exercise's `.meta` directory.

### Track Hints

The `$TRACK_ROOT/config/exercise-readme-inserts.md` gets included in _all_ the exercise READMEs for the track, and mustn't refer to specific problems or files. It should contain helpful, generic information about solving an exercism problem in the language of the track, for example hints about how to run the tests or where to get help.

### Exercise Hints

Anything that is specific to just one exercise, should be added to the `$TRACK_ROOT/exercises/$SLUG/.meta/hints.md` file.

[problem-specifications]: https://github.com/exercism/problem-specifications/tree/master/exercises
[configlet]: https://github.com/exercism/configlet
