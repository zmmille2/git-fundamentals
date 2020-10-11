# Resolving Conflicts
So far, we've just covered the main flow, but working with software is never so simple; if it were, we wouldn't need the powerful version control systems we have.
`git` is great at handling changes, but sometimes it needs insight to know how to handle two people editting the same file at once.

## Cause a Conflict
In your repo, you should have your pull request (PR) open.

![The Github ribbon with 1 Pull Request.](../resources/active-pr.png)

Click on the PR tab pictured and create a new 
Let's open another PR with a branch another devleoper worked on.
Set the compare to `zmmille2/sample`, and the base to `main`.
Then, create a new PR.

![The comparing changes page.](../resources/new-pr.png)
(Yours will look slightly differently if you haven't made the PR in the past already.)

Github should allow you to just merge this PR.
However, going back to your PR, you'll see an issue...

![There is a conflict, as these two changes touch the same lines in the same file.](../resources/confict.png)

To fix conflicts, we're going to have to use `merge`s or `rebase`s.
While we'll go into the specifics of each in a moment, we'll start with `rebase`s.

## Fix a Conflict

Fixing conflicts also has a main loop.

**Follow along in VSCode!**

```bash
git checkout main
git pull
git checkout <BRANCH-NAME>
git rebase main
// resolve conflicts in your editor of choice
git push --force-with-lease
// conflict resolved!
```

Because we've covered some of these steps, we'll cover them a bit quicker...

### `git checkout main` and `git pull` and `git checkout <BRANCH-NAME>`
These three commands do what they look like.
At a high level, they make sure that your `main` branch has the changes in it that are causing the conflicts.
It also puts you back in the branch that you've been working in, where we can get to the meat of this fix.

### `git rebase main`
This one's a new command.
`rebase`ing rewinds your changes, takes the target branch (in this case, `main`), and replays the changes onto that branch.
We'll get into the specifics in the next section, but when you run this command, you'll see the conflict locally.

```bash
```

---
[Prev](02-main-flow.md) - [Home](../README.md) - [Next](04-merges-and-rebases.md)
