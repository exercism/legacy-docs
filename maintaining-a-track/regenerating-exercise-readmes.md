# Regenerating Exercise READMEs

In order to give maintainers more control over the contents and formatting of each exercise README, it is generated from a template that the maintainers control. However, in order to avoid having to reinvent the universe from scratch when porting a new exercise from a shared specification, this README can be generated based on the specification description and other metadata.

## Setup

Install [configlet][]. You will need version 3.0.0 or higher.

If any of the exercises in your track are based on problems in the [problem-specifications][] repository, then you will
need to have a copy of that repository locally on disk, in the same directory as your track.

```
.
├── your-track/
└── problem-specifications/
```

## Generating the READMEs

Call the `configlet generate` command with the path to the track.

If you are in the track's root directory, then call it with `.`:

```
configlet generate .
```

By default this generates all the READMEs for all the exercises. In order to generate the README for a particular exercise, pass the `--only` flag with a slug:

```
configlet generate . --only hello-world
```

## The README Template

The template can be found at `$TRACK_ROOT/exercises/$SLUG/.meta/readme.go.tmpl`, and is written using Go's [text/template][text-template] package.

There are a number of values available in the template:

`.Spec` represents the problem specification, which is either a shared specification from [problem-specifications][], or a custom specification found in the exercise's `.meta` directory. The following values on `.Spec` can be referenced within the template:

- `.Spec.Slug` - the exercise's slug
- `.Spec.Name` - the wordified slug
- `.Spec.Description` - the contents of the `description.md` file
- `.Spec.Source` - a textual description of where the idea for the exercise came from (optional)
- `.Spec.SourceURL` - a link to something about the source (optional)
- `.Spec.Credits` - combines source and source_url into a readable bit of metadata

In addition to the values on `.Spec`, there are two additional bits of text that can be included:

- `.Hints` - the contents of the optional `HINTS.md` which lives in the root of the exercise directory.
- `.TrackInsert` - the contents of the `EXERCISE_README_INSERT.md` file, which lives in the track's `docs` directory.

### Default Template

The default contents of `.meta/readme.go.tmpl` is:

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

[configlet]: https://github.com/exercism/configlet
[text-template]: https://golang.org/pkg/text/template/
[problem-specifications]: https://github.com/exercism/problem-specifications

