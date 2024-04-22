# Gym-Git-Exercise-Solutions

## Bundle 1

### Exercise 1

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions
$ git init
Initialized empty Git repository in C:/Users/amica/Gym-Git-Exercise-Solutions/.git/

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (master)
$ git branch -m master main

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git add .

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git commit -m "my commit"
[main (root-commit) e236394] my commit
 2 files changed, 10 insertions(+)
 create mode 100644 README.md
 create mode 100644 index.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git remote add origin git@github.com:Angekarara/Gym-Git-Exercise-Solutions.git

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push -u origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 436 bytes | 109.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git branch dev

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git branch
  dev
* main

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout dev
Switched to branch 'dev'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git branch test

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git checkout test
Switched to branch 'test'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (test)
$ git checkout dev
Switched to branch 'dev'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git branch -d test
Deleted branch test (was e236394).
```

### Exercise 2

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git add home.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash
Saved working directory and index state WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash list
stash@{0}: WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git add about.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash
Saved working directory and index state WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash list
stash@{0}: WIP on dev: e236394 my commit
stash@{1}: WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git add team.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash
Saved working directory and index state WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash list
stash@{0}: WIP on dev: e236394 my commit
stash@{1}: WIP on dev: e236394 my commit
stash@{2}: WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{1} (cf633267a8bfccb4b1f9e6b8b427865d193d1b59)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash stash@{2}
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'stash@{2}'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash list
stash@{0}: WIP on dev: e236394 my commit
stash@{1}: WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash stash@{1}
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'stash@{1}'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash stash@{1}
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'stash@{1}'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash stash@{1}
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'stash@{1}'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        deleted:    index.html

Dropped stash@{1} (d7e2714d9f5552b9a50056b14e3b6e961300e3dd)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git add .

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git commit -m "new changes"
[dev 84874f6] new changes
 3 files changed, 66 insertions(+), 1 deletion(-)
 rename index.html => about.html (86%)
 create mode 100644 home.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash list
stash@{0}: WIP on dev: e236394 my commit

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git stash pop
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped refs/stash@{0} (f9192c70eff85e32a65aea340c7fba26ecb4738f)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git push
fatal: The current branch dev has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin dev

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git push origin dev
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 1.03 KiB | 350.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/dev
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      dev -> dev

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git rsest
git: 'rsest' is not a git command. See 'git --help'.

The most similar command is
        reset

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git reset
```

## Bundle 2

### Exercise 1

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git branch ft/bundle-2

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git branch
* dev
  ft/bundle-2
  main

  Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (dev)
$ git checkout ft/bundle-2
M       README.md
Switched to branch 'ft/bundle-2'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/bundle-2)
$ git status
On branch ft/bundle-2
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        services.html
        team.html

no changes added to commit (use "git add" and/or "git commit -a")

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/bundle-2)
$ git add services.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/bundle-2)
$ git commit -m "services file"
[ft/bundle-2 67035d6] services file
 1 file changed, 11 insertions(+)
 create mode 100644 services.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/bundle-2)
$ git push origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 428 bytes | 214.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/bundle-2
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
```
