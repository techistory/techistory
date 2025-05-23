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
