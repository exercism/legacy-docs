# Introductory copy

The aim of the introductory copy is to entice someone into wanting to try the language out.

We're not looking for Wikipedia-level detail.

## Introductory blurb (~30 words)

```
config.json
```

We need a very short plain-text blurb of about 30 words (a couple of sentences).

The goal is to give someone a really quick feel for what the language is about and why it might appeal to them.

The blurb is stored in the `config.json`, in a top-level key named `"blurb"`.

## About (~120 words)

```
docs/ABOUT.md
```

The blurb is closely followed by an "about" section on the main track page.

This provides a bit more detail about the language.
It might talk about its history, design goals, or about what the language is a great fit for, etc.
This should be 70-120 words split over 1-3 paragraphs. This text should be a friendly, genuine sales pitch for why someone should learn a language.

It should not be an in-depth introduction, and it should not be a quote from another source, though it can certainly point people to other sources if they want to learn more.
It can be in markdown format, but should only contain links and emphasis (bold, italic).

For inspiration, check out the `ABOUT.md` files from [the Go track](http://github.com/exercism/go/tree/master/docs/ABOUT.md) and [the R track](http://github.com/exercism/r/tree/master/docs/ABOUT.md).

## Code snippet

Next to the "About $LANGUAGE" on the track page, there will be a small code snippet.

The goal of the snippet is to give people a quick idea of what the syntax of the language looks like.
It doesn't need to be sophisticated, and it doesn't need be be copy/pastable into a REPL.

It should be **10 lines** maximum, and no more than **40 columns** wide.
