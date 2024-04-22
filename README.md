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

### Exercise 2

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git pull origin main
remote: Enumerating objects: 2, done.
remote: Counting objects: 100% (2/2), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (2/2), 1.73 KiB | 110.00 KiB/s, done.
From github.com:Angekarara/Gym-Git-Exercise-Solutions
 * branch            main       -> FETCH_HEAD
   e236394..64bf75f  main       -> origin/main
Updating e236394..64bf75f
Fast-forward
 README.md                | 285 +++++++++++++++++++++++++++++++++++++++++++++++
 index.html => about.html |   2 +-
 home.html                |   0
 services.html            |  11 ++
 team.html                |   9 ++
 5 files changed, 306 insertions(+), 1 deletion(-)
 rename index.html => about.html (86%)
 create mode 100644 home.html
 create mode 100644 services.html
 create mode 100644 team.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git add services.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git commit -m "changes on service file"
[ft/service-redesign e8b8194] changes on service file
 1 file changed, 2 insertions(+), 2 deletions(-)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 316 bytes | 316.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/service-redesign
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git add services.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git commit -m "service changes"
[main 2e0745e] service changes
 1 file changed, 2 insertions(+), 2 deletions(-)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 310 bytes | 310.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
   64bf75f..2e0745e  main -> main

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git diff main
diff --git a/services.html b/services.html
index 4490bed..9ae7f05 100644
--- a/services.html
+++ b/services.html
@@ -3,9 +3,9 @@
   <head>
     <meta charset="UTF-8" />
     <meta name="viewport" content="width=device-width, initial-scale=1.0" />
-    <title>services1</title>
+    <title>services3</title>

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git merge ft/service-redesign
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main|MERGING)
$ git add services.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main|MERGING)
$ git commit -m"changes"
[main c5fa93d] changes

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 209 bytes | 209.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
   2e0745e..c5fa93d  main -> main
```

## Bundle 3

### Exercise 1

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git status
On branch ft/team-page
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   team.html

no changes added to commit (use "git add" and/or "git commit -a")

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git add team.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git commit -m"new changes"
[ft/team-page be3dade] new changes
 1 file changed, 1 insertion(+), 1 deletion(-)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 286 bytes | 286.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/team-page
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/team-page -> ft/team-page

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git log
commit be3dade3982c80997cfc70b8af067406006017d1 (HEAD -> ft/team-page, origin/ft/team-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:25:38 2024 +0200

    new changes

commit 1019e128f85b4d11963c2685f0a532118f70319c (origin/main, main, ft/contact-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:18:38 2024 +0200


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/team-page)
$ git checkout ft/contact-page
Switched to branch 'ft/contact-page'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git log ft/team-page
commit be3dade3982c80997cfc70b8af067406006017d1 (origin/ft/team-page, ft/team-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:25:38 2024 +0200

    new changes

commit 1019e128f85b4d11963c2685f0a532118f70319c (HEAD -> ft/contact-page, origin/main, main)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:18:38 2024 +0200


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git cherry-pick be3dade3982c80997cfc70b8af067406006017d1
[ft/contact-page 617683a] new changes
 Date: Mon Apr 22 13:25:38 2024 +0200
 1 file changed, 1 insertion(+), 1 deletion(-)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git add contact.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git commit -m "contact page"
[ft/contact-page df6f7eb] contact page
 1 file changed, 11 insertions(+)
 create mode 100644 contact.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git push
fatal: The current branch ft/contact-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/contact-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git push origin ft/contact-page
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 705 bytes | 705.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/contact-page
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/contact-page -> ft/contact-page

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/contact-page)
$ git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git add faq.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git commit -m "faq file"
[ft/faq-page e7be806] faq file
 1 file changed, 11 insertions(+)
 create mode 100644 faq.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git push origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 416 bytes | 416.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/faq-page
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/faq-page -> ft/faq-page

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git log
commit e7be806166af931b348522200a798795c0687c2c (HEAD -> ft/faq-page, origin/ft/faq-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 14:10:23 2024 +0200
This reverts commit e7be806166af931b348522200a798795c0687c2c.

    faq file

commit df6f7eba83ee2e650af1ab4fccabb577d190cecb (origin/ft/contact-page, ft/contact-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:59:11 2024 +0200


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git revert e7be806166af931b348522200a798795c0687c2c
hint: Waiting for your editor to close the file... Vim: Error reading input, exiting...
Vim: Finished.
error: There was a problem with the editor 'vi'.
Please supply the message using either -m or -F option.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git revert e7be806166af931b348522200a798795c0687c2c
error: your local changes would be overwritten by revert.
hint: commit your changes or stash them to proceed.
fatal: revert failed

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git log
commit e7be806166af931b348522200a798795c0687c2c (HEAD -> ft/faq-page, origin/ft/faq-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 14:10:23 2024 +0200

    faq file

commit df6f7eba83ee2e650af1ab4fccabb577d190cecb (origin/ft/contact-page, ft/contact-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:59:11 2024 +0200


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git revert df6f7eba83ee2e650af1ab4fccabb577d190cecb
error: your local changes would be overwritten by revert.
hint: commit your changes or stash them to proceed.
fatal: revert failed

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git log
commit e7be806166af931b348522200a798795c0687c2c (HEAD -> ft/faq-page, origin/ft/faq-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 14:10:23 2024 +0200

    faq file

commit df6f7eba83ee2e650af1ab4fccabb577d190cecb (origin/ft/contact-page, ft/contact-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Mon Apr 22 13:59:11 2024 +0200


Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git add .

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git commit -m "new changes"
[ft/faq-page 2cdc9d0] new changes
 1 file changed, 11 deletions(-)
 delete mode 100644 faq.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git push origin ft/faq-page
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 223 bytes | 223.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
   e7be806..2cdc9d0  ft/faq-page -> ft/faq-page
```

### Exercise 2

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/faq-page)
$ git checkout -b ft/home-page-redesign
Switched to a new branch 'ft/home-page-redesign'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git checkout main
M       README.md
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   about.html

no changes added to commit (use "git add" and/or "git commit -a")

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git add .

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git commit -m "new changes"
[main 9bf4358] new changes
 2 files changed, 239 insertions(+), 1 deletion(-)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 1.76 KiB | 602.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
   1019e12..9bf4358  main -> main

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git che
checkout      cherry        cherry-pick

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git status
On branch ft/home-page-redesign
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git add home.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git commit -m "changes on home"
[ft/home-page-redesign da3d9d0] changes on home
 1 file changed, 11 insertions(+)

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git push origin ft/home-page-redesign
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (13/13), 1.22 KiB | 250.00 KiB/s, done.
Total 13 (delta 8), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (8/8), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Angekarara/Gym-Git-Exercise-Solutions/pull/new/ft/home-page-redesign
remote:
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
```

## Bundle 4

### Exercise 1

```bash
Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (ft/home-page-redesign)
$ git checkout main
M       README.md
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git remote add git-copy git@github.com:Angekarara/Gym-Git-Exercise-Solutions2.git

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git add home.html

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git commit -m "home changes"
[main 53cd77d] home changes
 1 file changed, 11 insertions(+)
 Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push origin main
git push git-copy main
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:Angekarara/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
Enumerating objects: 60, done.
Counting objects: 100% (60/60), done.
Delta compression using up to 4 threads
Compressing objects: 100% (58/58), done.
Writing objects: 100% (60/60), 11.83 KiB | 504.00 KiB/s, done.
Total 60 (delta 32), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (32/32), done.
To github.com:Angekarara/Gym-Git-Exercise-Solutions2.git
 * [new branch]      main -> main

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git pull origin
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 898 bytes | 128.00 KiB/s, done.
Merge branch 'main' of github.com:Angekarara/Gym-Git-Exercise-Solutions
Merge branch 'main' of github.com:Angekarara/Gym-Git-Exercise-Solutions
#
From github.com:Angekarara/Gym-Git-Exercise-Solutions
   1f40f33..78e6b63  main       -> origin/main
hint: Waiting for your editor to close the file... Vim: Error reading input, exiting...
Vim: Finished.

error: There was a problem with the editor 'vi'.
Not committing merge; use 'git commit' to complete the merge.

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main|MERGING)
$ git commit
[main 6f2b68b] Merge branch 'main' of github.com:Angekarara/Gym-Git-Exercise-Solutions

Ange@amica MINGW64 ~/Gym-Git-Exercise-Solutions (main)
$ git push origin
Enumerating objects: 13, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 1.37 KiB | 700.00 KiB/s, done.
Total 7 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 4 local objects.
To github.com:Angekarara/Gym-Git-Exercise-Solutions.git
   78e6b63..6f2b68b  main -> main

```
