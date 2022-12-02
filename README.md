# Learn about github

# [Github guides (https://github.com/git-guides/)](https://github.com/git-guides/git-init)

---


- Create a file

1. Create `index.html` file
```bash
touch index.html
```

2. Create `practice.py` file
```
touch practice.py
```


- Open up a file called `practice.py`

```bash
code practice.py
```


- When we have one `master` branch, and another branch called `login`, we want to merge the `login` branch to master branch

```bash
git merge login
```

- When we want to see the previous commits in one line

```bash
git log --oneline
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
git show 66e21c1
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



- When we want to revert to a certain version `66e21c1`

```bash
git checkout 66e21c
```

or if we want to change the specific file only

```bash
git checkout 66e21c README.md
```
