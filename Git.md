# Git
**Distributed Version Control System (DVCS)**

- Book: https://git-scm.com/book/en/v2

- Continuous improvement - **commits**
- Simultaneous stability and development - **branches**
- Improved quality - **pull requests**

## Repository
A series of **snapshots**, or **commits**

## Pull

Update the remote-tracking branches for the repository you cloned from, then merge one of them into your current branch:
```bash
$ git pull
$ git pull origin
```
Normally the branch merged in is the HEAD of the remote repository, but the choice is determined by the branch.<name>.remote and branch.<name>.merge options; see git-config[1] for details.

Merge into the current branch the remote branch `next`:
```bash
$ git pull origin next
```
This leaves a copy of next temporarily in FETCH_HEAD, but does not update any remote-tracking branches. Using remote-tracking branches, the same can be done by invoking fetch and merge:
```bash
$ git fetch origin
$ git merge origin/next
```
If you tried a pull which resulted in complex conflicts and would want to start over, you can recover with `git reset`.

A **pull** request is a request for others to review and approve the changes made to the project on a branch.

