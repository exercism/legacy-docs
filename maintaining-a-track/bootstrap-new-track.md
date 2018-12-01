# How to bootstrap a new track

**Only owners of the organization can create new repositories.**

## One-time setup

Run this setup the first time you are bootstrapping a new track.

1. Install [hub][].
2. Clone the [request-new-language-track][] repository.
3. Clone the [tools][] repository.
4. Follow the instructions in the [tools README][clone-tracks] to clone all the existing tracks.
5. Create a [saved reply][saved-replies] with the following checklist, this is the new track checklist:

```markdown
- [ ] Run bootstrap script
  `TRACK_ID=<id> LANGUAGE=<language> bin/bootstrap`
- [ ] Turn on [Travis CI][travis]
- [ ] If Windows-specific language, turn on [AppVeyor][appveyor]
- [ ] If Mac-specific language, turn on [Circle CI][circle]
  Add it as a Linux project, then switch it to OS X in _Project Settings -> Build Environment_
- [ ] Add as a submodule to [trackler][]
  `TRACK_ID=<id>; git submodule add https://github.com/exercism/$TRACK_ID tracks/$TRACK_ID`
- [ ] Create [new team][new-team] for language
- [ ] Add bootstrapped repository to team **with write access**
- [ ] Invite maintainer to team

[travis]: https://travis-ci.org/profile/exercism
[appveyor]: https://ci.appveyor.com/projects/new
[circle]: https://circleci.com/gh/organizations/exercism/settings#projects
[trackler]: https://github.com/exercism/trackler/tree/master/tracks
[new-team]: https://github.com/orgs/exercism/new-team
```

## Bootstrap a Track

Follow these steps to bootstrap a new track for a maintaner to start working on.

1. Add the "new track" label.
2. Confirm maintainer
- If the requestor is volunteering, that's fine.
- If the requestor is volunteering someone else for the job, confirm with that person.
- If there is no maintainer, label with "needs maintainer"
3. Once a maintainer is confirmed, add the "new track" checklist as a reply.
4. Once the checklist is complete, let the requestor/maintainer know that the repo is ready for them,
  and point them to the launch checklist issue.

[saved-replies]: https://github.com/blog/2135-saved-replies
[request-new-language-track]: https://github.com/exercism/request-new-language-track
[tools]: https://github.com/exercism/tools
[clone-tracks]: https://github.com/exercism/tools#scripts
[hub]: http://github.com/github/hub
