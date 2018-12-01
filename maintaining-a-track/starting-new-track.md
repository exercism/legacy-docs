# Starting a New Language Track

You want to start a new language track for `exercism`, that's great! There's a few things to check first:

**Does Exercism already support the language?**

Check [this list][trackler-tracks], which contains both the active and inactive tracks on the site.

If you find the language, follow the links from that list to view the repository.
The `config.json` file has an `active` key, which will be true or false.
If the track is active, then refer to the docs on [contributing to a language track][contributing-to-track].
If the track is innactive, do something else.

**Has someone else asked for it?**

Do a search in the [resquest-new-language-track][request-language-track-repo] repository for the name of the language. Remember to check both open and closed issues.
A closed issue will have the reasoning why the track was closed without being added.
If the issue is open, reply to it explaining that you want to maintain that track.

[new-issue]: https://github.com/exercism/request-new-language-track/issues/new
[request-language-track-repo]: https://github.com/exercism/request-new-language-track
[trackler-tracks]: https://github.com/exercism/trackler/tree/master/tracks
[contributing-to-track]:https://github.com/exercism/docs/tree/master/contributing-to-language-tracks

**No one has asked for the track I want yet.**

If you're interested in adding problems for a language that we don't yet have,
open an issue in the https://github.com/exercism/request-new-language-track repository.
Follow the issue template to get started.

## Beta-Testing a Language Track

---
For a track that is set as `"active": false` in the `config.json`, `exercism fetch`
will not automatically pull down problems. You can still test the language by
fetching problems directly, e.g.:

```shell
exercism fetch cpp bob
```

This will allow you to do some dry-run tests of fetching exercises,
double checking the instructions for each problem and submitting the
problem solution for peer review.

It is recommended that you configure a [Travis continuous integration build](http://travis-ci.org)
with your language track to verify that your example problem solutions
satisfy the tests provided for each problem.

You can include advice and helpful links for your language track in the
`SETUP.md` file.

## How to improve the process for the next new maintainer

It's crucial that we improve the documentation and instructions for launching a track.
The best people to discover issues with our current process are new maintainers, launching a track for the first time.
Unfortunately, that's the worst possible time for them to fix the documentation, because they've got the least amount of knowledge about how Exercism is put together.

The files in [resquest-new-language-track][request-language-track-repo] repository serve as a template for a new track.
Some files get edited and added to the track, others are used to [create new issues in the track][issue-templates], but are not added to the new repository.
If new maintainers have questions, look at these files, as they're the most likely culprit with confusing or missing information.

When that happens, we should tweak the documentation for clarity.
Open a new pull request to the [resquest-new-language-track][request-language-track-repo] repository, not their language respository. Be sure to tag the maintainer to review it so they can confirm it would eliminate their question or confusion.
If it's still confusing, they'll know, and figuring out how to explain it will help us fix it.

In some cases, we might discover that we're missing high-level documentation that should live here in the [docs][] repo.
In that case case we should open an issue or pull request [here][docs], proposing the new documentation. Tag the new
maintainer here, as well, to get their input on the new docs.

## How to make maintaning your new track fun

Ideally a track will have several maintainers. This makes the discussions more lively and interesting, and it makes the track more resilient to illnesses, job changes, new babies, and all the other excitement that real life<sup>TM</sup> brings.
We encourage you to recruit others to help you maintan your track. More hands can help make the work more lively and spread the workload.

### More Lively

We've noticed that as soon as there are at least two people maintaining the same track we get rich discussions about quality and idioms.
There's a lot more activity, and as a result it's a lot more fun.

### Helps to Spread the Workload

We don't want to burn people out.
It's really nice to be able to go on vacation or get busy at work without worrying too much about a growing backlog of unanswered issues and unreviewed and unmerged pull requests.

### Caveat

Something to keep in mind while working with more people is it the chance for diffusion of responsibility.
If you're unfamilliar with the term, it generally refers to the phenomena where a single person is less likely to take responsibility for an action or inaction if there are others present.
You can work with your other maintainers to avoid this by clearly communicating and dividing tasks.

[checklist]: https://github.com/exercism/request-new-language-track/blob/master/CHECKLIST.md
[docs]: https://github.com/exercism/docs
[issue-templates]: https://github.com/exercism/request-new-language-track/blob/master/bin/bootstrap#L67-L73

## How to bootstrap a new track

If you're an organization owner looking for the checklist and guide to boostrap a new track, please refer to the [bootstrapping a new track documentation][bootstrap-track].

[bootstrap-track]:https://github.com/exercism/docs/blob/master/maintaining-a-track/bootstrap-new-track.md
