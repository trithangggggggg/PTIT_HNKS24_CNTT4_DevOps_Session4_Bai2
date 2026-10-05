# Git Branch Practice

Main branch: Add important project information.
Feature update: Add new feature information.

Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git status
fatal: not a git repository (or any of the parent directories): .git
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git init
Initialized empty Git repository in D:/RIKKEI/DevOpsFundalmental/Session04/bai2/.git/
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git branch -M main
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git config --local user.name "Trithang"
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git config --local user.email "trithang2006vn@gmail.com"
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git config --local user.name
Trithang
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git config --local user.email
trithang2006vn@gmail.com
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> Set-Content README.md "# Git Branch Practice"
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> type README.md
# Git Branch Practice
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git add README.md
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git commit -m "Initial commit"
[main (root-commit) 8ead489] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git switch -c feature-update
Switched to a new branch 'feature-update'
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git branch
* feature-update
  main
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> Set-Content README.md @"
>> # Git Branch Practice
>>
>> Feature update: Add new feature information.
>> "@
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git add README.md
warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git commit -m "Update README in feature branch"
[feature-update d38d06a] Update README in feature branch
 1 file changed, 2 insertions(+)
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git switch main
Switched to branch 'main'
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git branch
  feature-update
* main
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> Set-Content README.md @"
>> # Git Branch Practice
>>
>> Main branch: Add important project information.
>> "@
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git add README.md
warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git commit -m "Update README in main branch"
[main 5544808] Update README in main branch
 1 file changed, 2 insertions(+)
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git merge feature-update
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git status
On branch main
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git add README.md
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git commit -m "Merge feature-update into main"
[main ae6e1f2] Merge feature-update into main
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> git log --graph --oneline
*   ae6e1f2 (HEAD -> main) Merge feature-update into main
|\
| * d38d06a (feature-update) Update README in feature branch
* | 5544808 Update README in main branch
|/
* 8ead489 Initial commit
PS D:\RIKKEI\DevOpsFundalmental\Session04\bai2> type README.md
# Git Branch Practice

Main branch: Add important project information.
Feature update: Add new feature information.