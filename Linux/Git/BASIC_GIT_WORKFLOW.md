[TOC]

## BASIC GIT WORKFLOW

An introduction to Git and a few of its core features. 

 ### Hello Git

Git is a software that <u>allows you to keep track of changes made to a project over time</u>. Git works by recording the changes you make to a project, storing those changes, then allowing you to reference them as needed.

We'll learn Git by using it to help us write a screenplay called *Harry Programmer and the Sorcerer's Code*.

We’ll get started by taking a look at the screenplay project.

 In **scene-1.txt**, add this text:

```
Harry Programmer and the Sorcerer’s Code: Scene 1
```

### git init

Now that we have started working on the screenplay, let’s turn the **sorcerers-code **directory into a Git project. We do this with:

```bash
git init
```

The word `init` means *initialize*. The command sets up all the tools Git needs to begin tracking changes made to the project.

In the terminal, initialize a new Git project.

Notice the output:

```bash
Initalized an empty git repository in /home/ccuser/workspace/sorcerers-code/.git/
```

The Git project was created.