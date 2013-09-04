Labs Workflow
=============

This is a step-by-step document for the Labs development workflow. TL;DR: It's
basically the
[GitHub Workflow](http://scottchacon.com/2011/08/31/github-flow.html).

This guide assumes a basic knowledge of git

Abbreviated version
-------------------

- Master is stable and can be deployed always.
- New changes are developed in feature-specific branches.
- Code is reviewed and merged through pull-requests on GitHub.
- Commits are squashed before being merged to keep the master history clean.

Full version
------------

### I. Create a new branch and open a PR

1. Make sure you're synced with master: `git checkout master` and `git pull`.
1. Checkout a new branch with a descriptive name and prefix it with your name:
`git checkout -b kyle-add-search`.
1. Make your changes and commit them: `git add file1`, `git add file2`, `git
commit -m "useful message"`.
1. Open a pull request as soon as you have some code committed (even if it's
not working), and describe your changes. @-mention any anyone who should be
watching this PR. If there's a technical spec for your change, link to it.

### II. Editing and reviewing

1. Continue making changes and updating the PR as necessary.
1. When your feature is in a complete state and ready to review, do an
   interactive rebase against master and squash your commits:

```
git checkout master
git pull
git checkout kyle-add-search
git rebase -i master
```

1. Fix any merge conflicts and force-push to update your branch: `git push -f
kyle-add-search`. **Do not force push to master.**
1. If there are any tests in your projects, be sure to run them now.
1. Assign a reviewer to the PR. Be sure to draw the reviewer's attention to
any specific questions you have.
1. Repeat this process based on reviewer comments until you get an "LGTM"
("Looks Good to Me"). Then merge your PR through GitHub and delete the branch.
1.  You can then remove the local branch by doing `git branch -d
branchname`.

See [Labs Code Review](code-review.md) for more info on the code review
process.
