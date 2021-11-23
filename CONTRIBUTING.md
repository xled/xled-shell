Contributing
============

* Start with a fork of the repo on GitHub.
* Clone your fork locally.
* Ensure you have installed `shellcheck` binary.
* Install pre-commit hook (which will run sanity checks on local commits):

```
    $ pre-commit install
```

Please follow [Github Flow](https://guides.github.com/introduction/flow/index.html).

This is a rough outline of the workflow:

* Create a topic branch from where you want to base your work. This is usually `main`.
* Make commits of logical units.
* Make sure your commit messages are in the proper format (see below).
* Push your changes to a topic branch in your fork of the repository.
* Submit a pull request.
* Rebase and force-push to your fork's branch as necessary.

Thanks for you contributions!


Commit message
--------------

This is an example of a commit message:

    add a cluster test command

    this uses tmux to setup a test cluster that you can easily kill and
    start for debugging.

This allows the message to be easier to read on github as well as in various
git tools.

* First line is a subject **subject** which contains brief description of the
  change.
  - use imperative, present tense: **change**, not *changed* nor *changes*
  - no dot (.) at the end
  - max 72 chars

* The **body** describes *why* the change is necessary.
  - like `<subject>`, use imperative, present tense
  - include motivation for the change and contrasts with previous behavior
  - wrap lines at 72 chars when possible

For more details on commits see https://chris.beams.io/posts/git-commit/ .
