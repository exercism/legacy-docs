# Git Basics

If you're concerned that you haven't done it right, don't worry. Submit your pull request, and we'll help you get the details sorted out.

## Getting the Code

We recommend forking the project first, and then cloning the fork.

```bash
git clone git@github.com:<YOUR_USERNAME>/<REPO_NAME>.git
```

This will give you a remote repository named `origin` that points to your own copy of the project.

In addition to this, we recommend that you add the original repository as a secondary remote.

```bash
git remote add upstream https://github.com/exercism/<REPO_NAME>.git
```

The names `origin` and `upstream` are pretty standard, so it's worth getting used to the names in your own work.

## Branches

When working on your fork it tends to make things easier if you never touch the master branch.

The basic workflow becomes:

* check out the master branch
* pull from `upstream` to make sure everything is up to date
* push to `origin` so you have the latest code in your fork
* check out a branch
* make the changes, commit them
* rebase onto the upstream master (and resolve any conflicts)
* push your branch up to `origin`
* submit a pull request

If you're asked to tweak your work, you can keep pushing it to the branch, and it automatically updates the pull request with the new commits.

## Commit Messages

Commit messages are communication and documentation. They're a log of more
than just _what_ happened, they're about _why_ it was done.

The longer a project is active, the more people involved, the larger the
codebase, the more important it is to have good commit messages.

There's an excellent lightning talk by Ryan Geary called [Do Your Commit
Messages
Suck?](https://www.youtube.com/watch?v=8YjSty6bfog).
It's funny and enlightening, and you should watch it.

Two articles that have very clear guidelines about how to write
excellent commit messages are Tim Pope's
[A Note About Git Commit Messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
and Chris Beams' [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/).
Please read them.

### Examples

Imagine that you're submitting a new problem called "spinning-wheel" to the Ruby track.

Here's a fairly typical set of commits that you might end up making:

```bash
433a0e1 added spinning wheel tests
1f7d4aa pass spinning wheel
cf21737 oops
be4c410 rename example file
bb89a77 update config
```

All of these commits are about a single thing: adding a new problem. They
should be a single commit. They don't have to start out that way (life is
messy), but once you're done, you should squash everything into one commit,
and rename it cohesively:

```bash
f4314e5 add spinning wheel problem
```

## Resetting `master`

If you've already made changes on your master so that it has diverged from the
upstream you can reset it.

First create a backup of your branch so that you can find any changes. Just in
case.

```bash
git checkout master
git checkout -b backup
git checkout master
```

Next, fetch the most recent changes from the upstream repository and reset master to it.

```bash
git fetch upstream
git reset --hard upstream/master
```

If you do a git log at this point you'll see that you have *exactly* the
commits that are in the upstream repository. Your commits aren't gone, they're
just not in master anymore.

To put this on your GitHub fork, you'll probably need to use the `--force` flag:

```bash
git push --force origin master
```

## Squashing

Squashing commits into a single commit is particularly useful when the change
happened in lots of little (sometimes confusing) steps, but it really is one
change.

There are a number of ways to accomplish this, and many people like to use an
[interactive rebase](#interactive-rebase), but it can be tricky if you haven't set git up to open
your favorite editor.

An easier way to do this is to un-commit everything, putting it back into the
staging area, and then committing it again.

Using the example from above, we have 5 commits that should be squashed into one.

```bash
433a0e1 added spinning wheel tests
1f7d4aa pass spinning wheel
cf21737 oops
be4c410 rename example file
bb89a77 update config
```

To un-commit them, use the following incantation:

```bash
$ git reset --soft HEAD^^^^^
```

Notice that there are 5 carets, one for each commit that you want to
un-commit. You could also say:

```bash
$ git reset --soft HEAD~5
```

If you do a `git status` now, you'll see all the changed files, and they're
staged and ready to commit. If you do a `git log`, you'll see that the most
recent commit is from someone else.

Next, commit, as usual:

```bash
$ git commit -m "Add spinning wheel problem"
```

Now if you do a `git status` you may get a warning saying that your origin and
your branch have diverged. This is completely normal, since the origin has 5
commits and you have 1 (different) one.

The next step is to force push this up to your branch, which will
automatically update the pull request, replacing the old commits with the new
one.

```bash
$ git push --force origin spinning-wheel
```

## Resources

If you're completely new to git, there are a number of resources that can help
get you feeling more comfortable with it.

* [Git Immersion](http://gitimmersion.com/)
* [GitHug](https://github.com/Gazler/githug)
* [Try GitHub](http://try.github.io)

If you've been using git for a while, but it feels like repeating magical
incantations (while praying that nothing goes wrong), then you may find these
helpful:

* [Git for Ages 4 and Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4) - video of a presentation/demo
* [Think Like a Git](http://think-like-a-git.net/)
* [Explain Git with D3](https://onlywei.github.io/explain-git-with-d3/) - interactive site
* [Pro Git](http://git-scm.com/book/en/v2) - "The Book" for learning Git in detail
* [Git Branching Tutorial](http://pcottle.github.io/learnGitBranching/) - interactive tutorial, very visual

## Rebasing

You'll often be asked to rebase your branch before we merge a pull request as Exercism likes to keep a linear project commit history. This is accomplished with git rebase. It takes the current branch and places all the commits at the front of the branch that you're rebasing with.

For example, rebasing the current branch on top of upstream/master:
```
 git rebase upstream/master
```
Project commit history:
```
                       -- current branch --
                      /
--- master branch ----
```

### Interactive Rebase
The rebase command has an option called `-i, --interactive` which will open an editor with a list of the commits which are about to be changed. This list accepts commands, allowing the user to edit the list before initiating the rebase action.

Using the example from above, we have 5 commits that should be squashed into one.

```bash
433a0e1 added spinning wheel tests
1f7d4aa pass spinning wheel
cf21737 oops
be4c410 rename example file
bb89a77 update config
```

To interactively rebase, use the following incantation:

```bash
$ git rebase -i HEAD~5
```
This will bring up an editor with the following information:

```bash
pick 433a0e1 added spinning wheel tests
pick 1f7d4aa pass spinning wheel
pick cf21737 oops
pick be4c410 rename example file
pick bb89a77 update config

#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

By choosing the `reword` command for the top commit and choosing the `fixup` command for the remaining commits, you will be able to squash the commits into one commit and provide a descriptive summary of the entire change

```bash
reword 433a0e1 added spinning wheel tests
fixup 1f7d4aa pass spinning wheel
fixup cf21737 oops
fixup be4c410 rename example file
fixup bb89a77 update config
```

[Further Reading](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
