# Learn about git/github

# [Github guides (https://github.com/git-guides/)](https://github.com/git-guides/git-init)

---

# When we already have projects saved in our local computer, we want to upload our files on github for the first time!

Let's say that we have project files saved in our local computer

We should create a repository on github.com website. We can't create github repository on bash.

And we should go to our root directory in our local computer and there on bash,

```
$ git init
$ git status
$ git add .
$ git status
$ git commit -m "first commit"
$ git remote add <name of the github repository> <url for github repository>
$ git remote -v
$ git push <name of the github repository>
```

# Code explain

## 1.

```
$ git init
```

This initializes git with default branch called `master`

If we want to set a default branch called `main`, we should write

```
$ git init -b main
```

This will set `main` as default branch.

## 2.

```
$ git status
```

This is always a good practice. This checks what has changed in the file, what files were added, etc.

## 3.

```
$ git add .
```

This adds the entire files that are located in the current working directory to the staging area.

If we want to add a specific file, we can write

```
$ git add README.md
```

This will add only `README.md`

## 4.

```
$ git status
```

Now you will see that `README.md` was updated.

## 5.

```
$ git commit -m 'first commit`
```

This actually becomes a change(commit) in the repository with a message `first commit`.

## 6.

```
$ git remote add <name of the github repository> <url forgithub repository>
```

This one is important, this connects the current local directory in our computer to the repository that was just created on github.com

The real example would be like

```
$ git remote add lets_git_it https://github.com/kjs29/lets_git_it.git
```

Another thing is, we can say like this

```
$ git remote add origin https://github.com/kjs29/lets_git_it.git
```

## 7.

```
$ git remote -v
```

We can check our remote URL by using this code.

## 8.

```
$ git push origin <name of the github repository>
```

We upload the local project files that are on staging area to the repository on github.com

Actual example would be like

```
$ git push origin lets_git_it
```

We can also say 

```
$ git push origin main
```

---

# Useful codes

- Create a file

1. Create `index.html` file

```bash
$ touch index.html
```

2. Create `practice.py` file
```
$ touch practice.py
```


- Open up a file called `practice.py`

```bash
$ code practice.py
```

- After modifying the code, we want to see the difference in our files

```
$ git diff
```

- When we have one `master` branch, and another branch called `login`, we want to merge the `login` branch to master branch

```bash
$ git merge login
```

### Viewing commits, viewing the changes

- When we want to see the previous commits in one line

```bash
$ git log --oneline
```

The result will look like this

```
745d4ce (HEAD -> master, origin/master, origin/HEAD) fist commit
66e21c1 Update README.md
8558b0a Update README.md
41c083c Create why config?.md
0e82175 Update README.md
868263e Update README.md
a0ad01e Update README.md
a9fcb5e Delete 11.30.md
38c6acb Create README.md
c649dfc Create 11.30.md
```

- To see what we changed in the commit `66e21c1`

```bash
$ git show 66e21c1
```

The result will look like this

```
commit 66e21c1aa6e46a2b4f15fe78b60fdc506b02fbe7
Author: kjs29 <96529477+kjs29@users.noreply.github.com>
Date:   Fri Dec 2 15:05:09 2022 -0600

    Update README.md

diff --git a/README.md b/README.md
index fcfb538..f8f17a0 100644
--- a/README.md
+++ b/README.md
@@ -23,3 +23,10 @@ touch practice.py

---snip---

```

or we can code like this to view the changes in each commit.

```bash
$ git log -p
```



### Undo/ Revert

# Before going over undo/revert in git, we need to understand this concept first.

## Git has three states.

### 1. Modified

You changed the file still, but you haven't added the file to the staging area yet.

### 2. Staged

Think of `staged` state as checked files for the commit state

### 3. Committed

Files that are `committed` state are safely stored and they are also ready to be pushed(uploaded) on github.

Here are the steps

1. We modify files in `working tree` - currently in modified state

ex. adding files, deleting files, modifying files

2. We choose what files to be staged in staging area

ex. `$ git add random.txt`, `$ git add .`

After we type `$ git add random.txt` now the `random.txt` is in staging area. Or it is in `staged` state.

If we want to put the `random.txt` back into modified state, or if we want to take `random.txt` out of `staging area` we can use this code

```
$ git reset random.txt
```

Let's say that we are ready to add `random.txt` to staging area

```
$ git add random.txt
```

3. and we are ready to commit.

```
$ git commit -m "added random.txt"
```

Now the `random.txt` file is in committed state which is ready to be pushed(uploaded) on github.

---

After commit, when we want to revert. It is like `ctrl + z`.

```bash
$ git checkout HEAD <filename>
```


HEAD means the current commit.


- When we want to revert to a certain version `66e21c1` (after commits)

```bash
$ git checkout 66e21c
```

or if we want to change the specific file only

```bash
$ git checkout 66e21c README.md
```
