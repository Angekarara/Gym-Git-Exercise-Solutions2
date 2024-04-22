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
