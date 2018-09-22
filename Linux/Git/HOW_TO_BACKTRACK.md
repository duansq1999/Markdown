[TOC]

## HOW TO BACKTRACK

 Learn about a few different ways to undo changes made to a Git project and when to use them.

### Backtracking Intro

When working on a Git project, sometimes we make changes that we want to get rid of. Git offers a few eraser-like features that allow us to undo mistakes during project creation. In this lesson, we'll learn some of these features.

To start out, let's review the basic Git workflow.

You are in a Git project titled **hamlet-prince-of-denmark**. In the code editor, you'll be working on **scene-5.txt**. Here, Hamlet encounters the ghost of his father. Add this text to the file:

```
Ghost: 
My hour is almost come,
When I to sulphurous and tormenting flames
Must render up myself.
```

From the terminal, add **scene-5.txt** to the staging area.

Commit the changes to the repository with a good commit message.

### head commit

In Git, the commit you are currently on is known as the `HEAD` commit. In many cases, the most recently made commit is the `HEAD` commit.

To see the `HEAD` commit, enter:

```bash
git show HEAD
```

The output of this command will display everything the git log command displays for the `HEAD` commit, plus all the file changes that were committed.

Enter the command to show the `HEAD`commit.

Notice the output. The ghost's most recently added line is in green text.

### git checkout

What if you decide to change the ghost's line in the working directory, but then decide you wanted to discard that change?

You could rewrite the line how it was originally, but what if you forgot the exact wording? The command

```bash
git checkout HEAD filename
```

 Change the ghost's words in some way. Here's a fun suggestion:

From the terminal, use `git diff` to see the difference between **scene-5.txt** as it appears in the working directory vs. how it appears in your last commit.

You may need to press `q` on your keyboard to restore the terminal.

Use the new Git command to restore the file in your working directory to look as it did when you last made a commit.

Notice that the changes you made to the ghost's line have been discarded.

### more git add

The **hamlet** repository we are working on contains five files. In Git, it's common to change many files, add those files to the staging area, and commit them to a repository in a single commit.

For example, say you want to change the character "LARRY" to "LAERTES" in the script. The name currently appears in two files. After you change the name in both files, you could add the changed files to the staging area with:

```bash
git add filename_1 filename_2
```

Note the word `filename` above refers to the name of the file you are adding to the staging area, such as **scene-3.txt**.

The code editor is open to **scene-3.txt**and **scene-7.txt**. In **scene-3.txt**, everywhere you see the name "LARRY" change it to "LAERTES."

 ### git reset I

