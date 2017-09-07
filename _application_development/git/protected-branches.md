---
title: Protected branches
position: 3
---

There's only one rule about the `master` branch: **anything in the `master` branch is always deployable**.

### Why we don't work directly in `master`

`master` should be treated like a _golden master_ version of your code. Code that is on the `master` branch is presumed to have been thoroughly tested, carefully reviewed, and actively running in your production environment. Additionally, developers working on new features use the repository's `master` branch as the base of their new feature branch, so any issues that might exist on `master` will be present in their feature branch.

### Protecting `master`

Instead of working in master, changes should be merged in via Pull Requests from other feature branches or from a fork. Refer to [the workflow guide](../../workflow) to learn how to create feature branches and how to merge your work via Pull Request.

It is a good practice to protect the `master` branch to encourage code reviews before changes are merged and deployed. This will prevent work from being performed directly on `master`, and will foster collaboration among CoA developers.

1. In your repository navigation to Settings > Branches
2. Under "Protected Branches" select `master`
3. Enable the following settings:
   1. Protect this branch
   2. Require pull request reviews before merging
   3. Dismiss stale pull request approvals when new commits are pushed
   4. Include administrators

Some developers have (rightly) expressed concern about this review process potentially delaying critical fixes from going in in response to a fire drill. Fret not! Owners of the repository and the Organization it lives in can always force the merge even if the PR hasn't been reviewed by a 3rd-party.
