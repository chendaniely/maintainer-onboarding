---
title: "Infrastructure for Lesson Maintenance"
teaching: 30
exercises: 30
questions:
- "How do I review pull requests?"
- "How do I make changes to pull requests?"
- "How do I accept pull requests?"
- "What should I know about how the lessons are formatted?"
objectives:
- "Understand the structure of the lesson template - know which elements generate the various parts of the lesson page." 
- "Navigate to the correct file and element to update each section - including instructor notes, setup, questions, timings, learning objectives, key points, and glossary."
- "Be familiar with the various callout boxes uses in The Carpentries lesson template and be able to use them appropriately." 
keypoints:
- "Make a branch to create a pull request."
- "The Carpentries lessons share a consistent style, which is controlled by [styles](https://github.com/carpentries/styles) and documented in the [lesson-example](https://carpentries.github.io/lesson-example/)"
---

## Maintainers and Forked Repositories

Congratulations! You're a lesson Maintainer!
If this is the first time you are maintaining a project where you and other people are going to be submitting changes
there are two perspectives you need to keep in mind:
one of the "contributor" and one of the "maintainer".

- Contributors: cannot directly `push` code to the repository
- Maintainers: *can* directly `push` code to the repository

![](../fig/git-maintainer_contributor_diagram.png)

### Our recommended workflow: Pushing and pulling to a remote (non-fork)

The 
[Software Carpentry Git lesson](https://swcarpentry.github.io/git-novice/) and
[Library Carpentry Git lesson](https://librarycarpentry.org/lc-git/)
show you how you can interact with a repository from an owner and Maintainer point of view
because you are allowed to `push` directly to your project on GitHub (see label 1)

As a Maintainer to one of our lessons,
you will be able to interact with the lesson just like it was your own repository (see label 1).
The only difference is the account the repository is under.
So instead of `username/repo` it will be something along the lines of `carpentries/repo`.
This means when you get the `git clone` url, you will have to get it from the `carpentries/repo` location,
not your own.

In this setup, since you are `clone`ing down from the original `carpentries` repo,
the remote will be your `origin`.
This is same workflow as if you are working on your own personal repository,
and you can `git push origin gh-pages`.

> ## An alternative workflow: Pushing and pulling to a remote (fork)
> 
> Some Maintainers choose to work using the forking model of collaboration.
> Even though they have access to the original "upstream" Carpentries repository,
> they will make a "fork" of the Carpentries repository so they have a copy (i.e., fork) in their own account
> (see label 2).
> Using this workflow gives you (the Maintainer) the same workflow as any other contributor to your lesson
> (since contributors will also need to work on a fork).
> 
> Once you fork the repository, there will be the original "upstream" `carpentries/repo` and your own "fork", `username/repo` (see label 2).
> You can `clone` your `username/repo` down to your computer like any other repository you want to work on locally and push and pull your changes to your remote (label 3).
> Because the repository you `clone`d from is your own "fork" (`username/repo`),
> the version in your account that you cloned from is the "origin" repository (see the blue colored "origin" label in the diagram).
> You can then issue a pull request (PR) to the original `carpentries/repo` repository (see label 4).
> 
> For PRs from non-maintainers you will review these changes and ask for changes if needed.
> As the Maintainer, you can review and/or accept these PRs (including your own)
> because as a Maintainer you will have the repository permissions (in `carpentries/repo`)
> to accept the PR (see label 5).
> 
> As more changes come in and get accepted, from other contributors and accepted by you or other Maintainers,
> the forked repository (bottom right quadrant) and your own local copy (bottom left quadrant) will be out of sync.
> You won't be able to "fork" the original `carpentries/repo` again, so you will need to set the original `carpentries/repo` as
> *another* remote to get things synced up.
> You do this by adding the original `carpentries/repo` repository as another remote, typically named `upstream` (see blue text).
> To syncronise the work so your local and remote copy, you will `git pull upstream gh-pages` to get the upstream changes (see green label 6),
> and then `git push origin gh-pages` to synconise your own forked remote (i.e., GitHub) copy.
{: .callout}

## Practice using the recommended workflow

We will now practice using the recommended workflow for pushing and pulling to a remote. 

You will be assigned to a breakout group of 2-3 people. Once you are in breakout rooms, decide who will play 
the role of the Maintainer ("M"), and who will be the contributor ("C"). 

> ## Working on the `gh-pages` branch (10 minutes)
>
> 1. M: Create a repository: `<date>-collab-example` and create it with at least a `README.md` file so the repository is not completely empty.
> 1. M: Add C as a collaborator under the repository settings.
> 2. C: Accept the collaboration invitation (check your e-mail)
> 3. M + C: `clone` the repository to your local machine
> 4. M + C: Both add your name to the `README.md` file
> 5. M + C: `add` and `commit` your changes
> 6. M + C: `push` your changes to the remote
> 7. M + C: someone will have a merge conflict
{: .challenge} 

> ## Working on a new branch (15 minutes)
> 
> 1. Make sure that your local version is up-to-date: `git pull origin gh-pages`
> 2. Create a new branch: `git checkout -b BRANCH_NAME` or `git switch -c BRANCH_NAME`
> 3. Make changes, `add`, `commit`, and `push` the changes
> 4. Create a PR
{: .challenge}

> ## Practice using the fork workflow (Optional)
> 
> Working on the `gh-pages` branch
> 
> 1. C: fork the repository from M
> 2. C: `clone` from your respitory (`c/<date>-collab-example`)
> 3. M + C: Both add your name to the `README.md` file
> 4. M + C: `add` and `commit` your changes
> 5. M + C: `push` your changes to the remote (C: it will be your `origin`)
> 6. C: Issue the PR
> 7. M: Review and merge the PR
> 8. C: Setup the upstream remote
> 9. C: Sync the upstream changes to your local machine and your fork
> 
> Repeat but using a branch
> 
> 1. Make sure that your local version is up-to-date: `git pull origin gh-pages`
> 2. Create a new branch: `git checkout -b BRANCH_NAME` or `git switch -c BRANCH_NAME`
> 3. Make changes, `add`, `commit`, and `push` the changes
> 4. Create a PR
> 5. M: Review and merge the PR
> 6. C: Setup the upstream remote
> 7. C: Sync the upstream changes to your local machine and your fork
{: .solution}

> ## Questions and Answers (5 minutes)
> Please add questions to the Etherpad.
{: .challenge}

## The Carpentries Lesson Template

The template for Carpentries lessons is managed through the [styles
repository](https://github.com/swcarpentry/styles), and documented on 
the [lesson-example repository](https://carpentries.github.io/lesson-example/). 

> ## Who Maintains the Lesson Template? 
> Which is maintained by the
> [Lesson Infrastructure Committee](https://carpentries.org/lesson-infra/). The
> activity of the Committee was put on hold during the COVID-19 pandemic but is
> set to resume in late 2021. In the meantime, the 
> [Curriculum Team](https://carpentries.org/core-team-projects/#curriculum-team), with the
> help of [Maxim Belkin](https://github.com/maxim-belkin), has been maintaining
> this repository.
{: .callout}

### Lesson homepage

The lesson homepage is built from the `index.md` file and
provides an overview of the lesson, including
any prequisites, an introduction to the
dataset used, a schedule showing
the episodes and the time alloted for each, and any other
information learners will need for the lesson.

The schedule will automatically be included in the lesson homepage based on information present in the
episode files.

### Episode files

The majority of a lessons content is in its episode files.
Episode files are stored in the `_episodes/` folder within your lesson repo (or in `_episodes_rmd/` for lessons written in R).
Episode file names must start with a two-digit identifier number (e.g. `01`) followed
by a short descriptive name, separated by a dash (`-`). For example `02-loop.md`, `03-lists.md`.
The numeric identifier is used to place your episode files in the correct sequence within the lesson.
Episode files are written in *Markdown* or *RMarkdown*.

#### Episode headers

Each episode starts with a YAML header, that looks something like this:

```
---
title: "What is the shell?"
teaching: 5
exercises: 0
questions:
- "What is the shell?"
- "What is the command line?"
- "Why should I use it?"
objectives:
- "Describe the basics of the Unix shell"
- "Explain why and how to use the command line"
keypoints:
- "The shell is powerful"
- "The shell can be used to copy, move, and combine multiple files"
---
```

The information
stored in the YAML header is used by the lesson template to populate important parts of the lesson webpage.

For example, "questions" are scraped from each episode file and added to the schedule on the lesson homepage. 

> ## Scavenger Hunt (5 minutes)
> Identify the file and lines of the file that control the following output for your lesson. 
> Add the file name and copy the relevant lines to the Etherpad. 
> - Questions (for episode 1)
> - Timings (for episode 1)
> - Learning objectives (for episode 1)
> - Key points (for episode 1)
> - Instructor notes
> - Setup instructions
> - Glossary
{: .challenge}

For a step-by-step guide to how the lessons are structured, and what syntax to use to add
code chunks, exercises, and other elements, please read the 
[technological introductions chapter](https://cdh.carpentries.org/technological-introductions.html) 
of The Carpentries Curriculum Development Handbook.

For a more in-depth guide, read through the [lesson example](https://carpentries.github.io/lesson-example/). 

> ## New Template Coming
> We are in the beta testing phase for a new lesson template that is designed to be 
> more user friendly for both contributors and Maintainers. Information about
> the new template is available in [this blog post](https://carpentries.org/blog/2020/08/lesson-template-design/). 
> Announcements will be made to the official Maintainers channels as we approach a launch date.
{: .callout}
