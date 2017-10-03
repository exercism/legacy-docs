# Anatomy of an Exercise

TODO: expand on notes below.

## README

TODO

## Test Suite

TODO

## Supporting Files

TODO (boilerplate, header files, etc)


## Exercise metadata

Each exercise's metadata lives in a directory under `exercises/`

```
exercises/
├── accumulate
│   ├── description.md
│   └── metadata.yml
├── ...
├── minesweeper
│   ├── canonical-data.json
│   ├── description.md
│   └── metadata.yml
├── ...
└── zipper
    ├── description.md
    └── metadata.yml
```

There are three metadata files:

* `description.md` - the basic problem description
* `metadata.yml` - additional information about the problem, such as where it came from
* `canonical-data.json` (optional) - standardized test inputs and outputs that can be used to implement the problem


### Description.md

TODO: Format specification, example.

### Metadata.yml

TODO: Format specification, valid/required/default keys, example.

### canonical-data.json

TODO: Link to existing documentation.


## Reference Solution

The reference solution is named something with `example` or `Example` in the path.

The solution does not need to be particularly great code, it is only used to verify
that the exercise is coherent.

If you change the test suite, then make sure the reference solution is fixed
to pass the updated tests.
