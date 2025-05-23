Git is like SCLM with a lot more bells and whistles.

- SCLM DEV is the untracked (by Git) local computer changes.
- SCLM INT is the Git staging area (where ADDed stuff lives before commit)
- SCLM SYS lives both locally and remotely (on GitHub). It is the history of changes, and is synced back and forth along with PRD when PUSH and PULL are executed.
- SCLM PRD lives both locally and remotely (on GitHub). It is the commited code. PUSH and PULL sync this to GitHub or locally respectively.

Note, PULL (updating local from newer GitHub code) should rarely be used. Better to make all changes locally and keep the GitHub repo updated with repeated PUSHes.

| Command                             | Description                                                                    |
| :---------------------------------- | :----------------------------------------------------------------------------- |
| git status                          | Get repo status                                                                |
| [_make changes locally_]            | Like editing in SCLM DEV (local computer)                                      |
| git add .                           | Push DEV to INT (local computer)                                               |
| git commit -m [_comment_]           | Push INT to SYS (local computer)                                               |
|                                     | Updates branch and logs change history (think of SYS as the change log)        |
| git push origin main                | Push SYS to PRD (GitHub)                                                       |
| [_make changes on github_]          | Like editing directly in PRD (GitHub)                                          |
| [_commit changes button on GitHub_] | Commit updates branch and logs change history (think of SYS as the change log) |
| git pull origin main                | Pull PRD back to DEV (local computer)                                          |
|                                     | Pulling from main syncs local "DEV" and "SYS" (the change history) from GitHub |
