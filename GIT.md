# GIT

This is a guide on operating git.

You should be familiar with [branching](https://www.atlassian.com/git/tutorials/using-branches) in git. 

## fork

Problem: It can be a painful situation if everybody pushes code to the `master` branch. When multiple people are working on a codebase, we want the workflow to be as efficient and streamlined as possible. If everybody pushes to a single branch, there is no way we can get the work done without dealing with conflicts.  

Solution: each contributor creates a copy of this repository into his/her GitHub account. Contributor then works on the code in a separate branch. When contributor is done with the task in hand, he/she makes a pull request to the master branch of the main repository.

Example scenario: I want to work on a feature in the [scrawl](https://github.com/scrawlapp/scrawl) repository.

1. I fork the repository and get it into my personal account.
2. I clone the forked repository into my computer.
3. I make sure that I have two references (described later). 
    - One that points to the forked repository on my personal account.
    - One that points to the main repository from where I got my fork. 
4. I create a separate branch for my feature.
5. I work on my code, make commits, and keep pushing this branch to my personal account. 
6. When I am ready, I make a pull request.
7. The pull request gets accepted by the maintainers of the main repository.
8. I delete my feature branch (not the master branch). 
9. I might want/have to work further in this codebase so I need to fetch the latest commits from the main repository into my master branch.
10. When I want to work on anything else after this, I start from step 4.

## references

References can be thought of as places on the internet where a repository exists. You need two references to get started with. One is the conventional `origin` reference which points to your forked repository and another is a reference to the main repository of the organisation.

do:
``` bash
git remote # to check what references you have
git config --get remote.< name of reference >.url # to check what the reference points to
```

if you do not have an origin setup:
```bash
git remote add origin https://github.com/your_username/repo_name.git
```

add a reference to the main repository: 
```
git remote add upstream https://github.com/organisation_name/repo_name.git
```

*upstream* is just a conventionally accepted name. You could name it something else too.

## handy list of commands

If you want to fetch from `upstream` in order to sync your personal repository with the main repository:
```
git checkout master
git fetch upstream
git merge upstream/master
```

Branching:
```
# for switching to a branch that exists
git checkout <branch_name>

# for creating a new branch and switching to it as well
git checkout -b <branch_name>
```
Pushing: 
```
git push <reference_name> <branch_name>
```

## writing good commits

### What is good?

1. A good commit message is detailed.
2. It focusses on the *why* more than the *what* or the *how*. What you do is tracked by Git already. How you do it is visible to the reader of your code already. 

### Use the editor method to write commits

We are used to writing: 
```bash 
git commit -m "a message"
```
**Avoid that.**

Just run `git commit` and it will open up an editor.
 
To configure your *"default"* editor:
```bash
git config --global core.editor <name>

# name could be nano/emacs/vim/whatever you like
```

### structure of the commit

A good commit message is broken down into three parts:

```
> Top

> Middle

> Bottom
```
with *exactly* one-line spacing vertically between sections.

<br>
 
The *top* should follow the format:
```
<type>: <summary or the subject line> 
```

where *type* is one of:

    feat: The new feature you're adding to a particular application
    fix: A bug fix
    style: Feature and updates related to styling
    refactor: Refactoring a specific section of the codebase
    test: Everything related to testing
    docs: Everything related to documentation
    chore: Regular code maintenance

**The net length of the top should not be more than 50 characters.**

Do not end the subject line with a period.
<br>

The *middle* (or the body):
```
Elaborate your work. Do not assume the reviewer understands what the original problem was, ensure you add it. Do not think your code is self-explanatory.
```

The *bottom* section is optional. Use it if you want to link the commit to an issue.
<br>
