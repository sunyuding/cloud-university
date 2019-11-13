# Git
**Distributed Version Control System (DVCS)**

- Book: https://git-scm.com/book/en/v2

- Continuous improvement - **commits**
- Simultaneous stability and development - **branches**
- Improved quality - **pull requests**

## Repository
A series of **snapshots**, or **commits**. 

## Syntax
```bash
$ git [command] [--flags] [arguments]
```

```
$ git help
```
Read help
- `-f` or `--flag` Change the command's behavior
- `|` Or
- `[optional]`
- `<placeholder>`
- `[<optional placeholder>]`
- `()` Grouping
- `--` Disambiguates the command
- `...` multiple occurrences possible

```
$ git fakecommand (-p|--patch) [<id>] [--] [<paths>...] 
```
## Config
Setting Your User Name and Email
```
$ git config [--local|--global|--system] <key> [<value>]
$ git config --global user.name "Yudi"
$ git config --global user.email "yudi@example.com"
```
- The `--system` flag applies to every repository for all users on your computer
- The `--global` flag applies to every repository that you use on your computer
- No flag or `--local` applies only to the current repository (highest precedence)

Reading Your User Name And Email
```
git config <key>
```

## Working Tree
- Working Tree
    - A single commit's directories and files
- Staging Area/Index
    - 
- Local Repository
- Remote Repository

[ ] [Git: Merge Branch into Master](https://stackabuse.com/git-merge-branch-into-master/)

## Pull

Update the remote-tracking branches for the repository you cloned from, then merge one of them into your current branch:
```bash
$ git pull
$ git pull origin
```
Normally the branch merged in is the HEAD of the remote repository, but the choice is determined by the branch.<name>.remote and branch.<name>.merge options; see git-config[1] for details.

Merge into the current branch the remote branch `next`:
```bash
$ git pull origin <next>
```
This leaves a copy of next temporarily in FETCH_HEAD, but does not update any remote-tracking branches. Using remote-tracking branches, the same can be done by invoking fetch and merge:
```bash
$ git fetch origin
$ git merge origin/<next>
```
If you tried a pull which resulted in complex conflicts and would want to start over, you can recover with `git reset`.

A **pull** request is a request for others to review and approve the changes made to the project on a branch.

## Git: Merge Branch into Master
The `git` branch command is used to list all existing branches in a repository. An asterisk will appear next to the currently active branch.
```bash
$ git branch
* master
```
To create a new branch, we can use the command `git branch <new-branch>`. This will create a new branch mirroring the commits on the currently active branch.
```bash
$ git branch <new-branch>
$ git branch
* master
new-branch
```
Git does not actually create a new set of commits to represent the new branch. In Git, a branch is really just a **tag**. To start working on the new branch we first need to run the command `git checkout new-branch`. 
```bash
$ git checkout new-branch
Switched to branch ‘new-branch'
$ git branch
master
* new-branch
```
First we run `git checkout master` to change the active branch back to master. Then we run the command `git merge new-branch` to merge the new feature into the master branch. Note that `git merge` merges the specified branch into the currently active branch. So we need to be on the branch that we are merging into.
```
# ...develop some code...

$ git add –A
$ git commit –m "Some commit message"
$ git checkout master
Switched to branch 'master'
$ git merge <new-branch>
```

## Submodule
**Submodules** allow you to keep a Git repository as a subdirectory of another Git repository. This lets you clone another repository into your project and keep your commits separate.

**.gitmodules** file is a configuration file that stores the mapping between the project’s URL and the local subdirectory you’ve pulled it into.

Here we’ll clone a project with a submodule in it. When you clone such a project, by default you get the directories that contain submodules, but none of the files within them yet.

You must run two commands: `git submodule init` to initialize your local configuration file, and `git submodule update` to fetch all the data from that project and check out the appropriate commit listed in your superproject.

There is another way to do this which is a little simpler, however. If you pass `--recurse-submodules` to the `git clone` command, it will automatically initialize and update each submodule in the repository, including nested submodules if any of the submodules in the repository have submodules themselves.

If you already cloned the project and forgot `--recurse-submodules`, you can combine the git submodule init and git submodule update steps by running `git submodule update --init`. To also initialize, fetch and checkout any nested submodules, you can use the foolproof `git submodule update --init --recursive`.

```bash
$ git submodule update --init --recursive
```

## Fork
- [Forking Projects](https://guides.github.com/activities/forking/)
- [Fork a repo](https://help.github.com/en/articles/fork-a-repo)


- [ ] https://git-scm.com/book/en/v2/Git-Tools-Submodules

## Diff
If you want to see what you haven't git added yet:
```
$ git diff myfile.txt
```
or if you want to see already added changes
```
$ git diff --cached myfile.txt
```

## Notes
### [git discard all changes and pull from upstream](https://stackoverflow.com/questions/13781388/git-discard-all-changes-and-pull-from-upstream/46220797)
```
git reset --hard origin/master
git pull origin master
```


