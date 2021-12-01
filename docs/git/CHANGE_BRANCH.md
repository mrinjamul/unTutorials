# Change main branch with new branch

Change the main branch with new branch.
and sync up with local git repository.

```
git branch -m master trunk
git fetch origin
git branch -u origin/trunk trunk
git remote set-head origin -a
```
