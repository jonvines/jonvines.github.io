---
layout: post
title:  "Migrating from mercurial to git"
date:   2017-04-21 11:30:00 +0100
categories: mercurial git migration
excerpt: Self remembrance of migrating from Mercurial repositories to Git repositories.
published: true
---

Having done this migration path a few times now, and having to remind myself from a couple of sources with a couple of caveats I'm including a quick guide for the migration of single branch mercurial repositories to git repositories.

For full disclosure, a lot of this was taken from this [stack overflow ticket](http://stackoverflow.com/questions/16037787/convert-mercurial-project-to-git). Specifically Timmmm's answer.

1. Open command line, and create the an empty directory for the git repository
2. `git init --bare .git` in the new directory
3. `cd` to your mercurial repository
4. `hg bookmarks master` in the mercurial repository
5. `hg push c:/path/to/repository`
6. Go back to the git repository `git config --bool core.bare false`
7. All files were in a deleted state for me, so ran `git checkout master`
8. `git remote add origin ssh://path/to/repo`
9. `git push`

If you've not applied a .gitignore file, add one now. To pick up .gitignore and apply to the repository, run the command `git rm -r --cached`
