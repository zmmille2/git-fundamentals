# Main Flow
To really get started with `git`, let's cover the main flow.
Note that this section is going to move fast, and there may be some unfamiliar terminology - that's ok!
We'll cover this as a starting point, and dissect it later.

**Follow along in VSCode!**

```bash
git checkout main
git pull
git checkout -b <BRANCH_NAME>
// Make changes in your favorite editor!
git add .
git commit -m "A message"
git push
// Make a pull request
```
## `git checkout main`
Make sure you're on the default branch for your repository.
**This repository uses `main`.**

NOTE: While `main` is gaining popularity as the default branch, old repositories will likely refer to `master` here.
On the landing page of the project, you can see the branch name near the top left.

![TODO: ADD IMAGE HERE](../resources/todo.png)

## `git pull`
This will `pull` in the most recent changes from the remote branch.

## `git checkout -b <BRANCH_NAME>`
**Create a new branch called `<BRANCH_NAME>` to start working in.**
Call it whatever you like - your name, or your Github alias, for example.
Notably, this will be based off the branch that you were in when you ran the command.

## Make changes in your favorite editor
You can use VSCode here if you like, or the terminal.
**Change instances of `<BRANCH_NAME>` with whatever you called your branch!**

## `git add`
Now you have changes in your working directory.
If you run `git status` from your `git-fundamentals` directory, you can see `git` is aware of these changes, but that they aren't staged for commit.

```bash
zach@US0003EMPL001 git-fundamentals % git status
On branch zmmille2
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   topics/02-main-flow.md

no changes added to commit (use "git add" and/or "git commit -a")
```

On the fourth line, `git` helpfully tells us we should `add` to update what will be committed, so make sure to run `git add topics/02-main-flow.md`.

## `git commit -m "A message"`

Now, your `git status` should look like this:

```bash
zach@US0003EMPL001 git-fundamentals % git status
On branch zmmille2
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   topics/02-main-flow.md
```

Again from `git-fundamentals`, run `git commit -m ""` with a helpful message in the quotes.
It can be whatever you like, but there are [some great guidelines](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53) on how to write good ones.
These messages help future you and developers like you!

For now **let's run `git commit -m "Updates branch name variable to <BRANCH_NAME>"`** (But update that instance too).

## git push

Now `git status` should look like this:

```bash
zach@US0003EMPL001 git-fundamentals % git status
On branch zmmille2
nothing to commit, working tree clean
```

If we run `git push`, `git` may complain about not having an upstream, and ask you to tell it what to use.

```bash
fatal: The current branch <BRANCH_NAME> has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin <BRANCH_NAME>
```

Either run the provided command, or run this:
```bash
git config --global push.default simple
```
There's a good post [here](https://stackoverflow.com/questions/948354/default-behavior-of-git-push-without-a-branch-specified) talking about why this is the case.

## Pull Requests

Finally, let's make a pull request showcasing these changes.
Luckily, after a `push`, there should be a link to make a pull request right away.



---
[Prev](01-fork-and-clone.md) - [Home](../README.md) - [Next](03-resolving-conflicts.md)
