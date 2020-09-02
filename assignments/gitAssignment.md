# Git Assignment

**INDIVIDUAL ASSIGNMENT**

**Value**: Part of in-class/short assignments grade

## Description

### Understanding the repo
To conduct this, you will have to download [handson.zip](handson.zip) and unzip it.
handson folder is a git repository. Using the command line change the directory to "handson/"


1. Describe what is the output of the following commands
    -  `git branch` 
    -  `git checkout BRANCH_NAME` (USE THE NAME OF AN EXISTING BRANCH)
    -  `git log --decorate`

```
git branch
feature-foo
master
// lists the available branches
 
git checkout feature-foo
Switched to branch ‘feature-foo’
// switches working branch 
 
git log --decorate
commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:29:22 2018 -0700
 
    Adding header of method foo()
 
commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:27:16 2018 -0700
 
    Adding class A skeleton
 
commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:26:44 2018 -0700
 
    Creating all files (all empty)
 
// shows references to each commit


```

2. Try `git log --graph --all`. What do you see?
```
This command shows an ASCII representation of the branches and commit history

```

3. Use `git diff BRANCH_NAME` to view the differences from a branch and the current branch.
   Summarize the difference from master to the other branch.

```
Method header foo() was added, and class B was removed.

```

4. Write a command sequence to merge the non-master branch into `master`

```
git checkout master
git merge feature-foo -m ‘Merge branch to master’

```


5. Write a command (or sequence) to (i) create a new branch called `math` (from the `master`) 
and (ii) change to this branch

```
git checkout -b math
```
   
6. Edit B.java adding the following source code below the content you have there
```java
System.out.println("I know math, look:")
System.out.println(2+2)
```

7. Write a command (or sequence) to commit your changes
```
git commit -a -m ‘Add two lines to B.java’

```

8. Change back to the `master` branch and change B.java adding the following source code (commit your change to `master`):
```java
System.out.println("Hello World")
```

9. Write a command sequence to merge the `math` branch into `master` and describe what happened
```
git merge math -m ‘Merge math to master’

Auto-merging B.java
CONFLICT (content): Merge conflict in B.java
Automatic merge failed; fix conflicts and then commit the result.

```
   
10. Write a set of commands to abort the merge
```
git merge --abort

```
   
11. Now repeat item 9, but proceed with the manual merge (Editing B.java). All implemented functions are needed. Explain your procedure
```
I opened B.java in Vim from the master branch and removed all of the conflict dividers and saved the file. 

```

12. Write a command (or set of commands) to proceed with the merge and make `master` branch up-to-date
```
git add B.java
git commit -m “merged and resolved the conflict in math”

```




