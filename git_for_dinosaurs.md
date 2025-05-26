Git is like SCLM with a lot more bells and whistles. Note, SCLM SYS is the key metaphor and where all the action is. In Git, the "SYS" entity is an exquisitly versioned code museum that maintains a complete copy of every version of every module in a given branch of the repository. The Git equivalent of SCLM PRD is merely the visible top layer (most recent version) of the archealogical history of the code in that (SYS) branch. Each branch is a separate SCLM SYS/PRD.

Think of a Git branch as a push-down stack where the most recently added element is "PRD" and the entire stack (including PRD) is "SYS". If you have no branches other than "main" (or "master"), then you have only one SYS/PRD stack to worry about. With some fancy scripting, SLCM allows for multiple DEV/INT levels (that don't even allow you to promote to SYS), but Git flips the script and gives you tools to manage multiple SYS/PRD "stacks" (Git calls them branches). This guide won't discuss branches (other than main) since a single "branch" is enough to worry about for now. Main is walking. More branches is running. Learn to walk first.

- SCLM DEV - Untracked (by Git) local computer changes. Is "empty" when there are no changes compared to "PRD".
- SCLM INT - Git staging area (where ADDed changed stuff sits before commit).
- SCLM SYS - Lives both locally (on PC) and remotely (on GitHub). It is the full history of all versions of the code in the current branch, and is updated by "git commit" (on PC) or pressing the "Commit Changes" button on GitHub after making changes there. (Syncing between PC and GitHub with push or pull still needs to be done).
- SCLM PRD - There is no explicit Git entity equivalent to PRD. But it can be thought of as the most recent version of code visible in SYS. It is not really a separate entity like in SCLM, but merely the most recently commited stuff. It is the tip of the iceberg that we think of as "The Branch" (main or otherwise).

Note, PULL (updating local from newer GitHub code) should rarely be used. Better to make all changes locally and keep the GitHub repo updated with repeated PUSHes.

| Command                                                    | Description                                                                                         |
| :--------------------------------------------------------- | :-------------------------------------------------------------------------------------------------- |
| git status                                                 | Get repo status                                                                                     |
| git branch -a                                              | List all branches in the repository. Current branch is starred.                                     |
| [_make changes locally_]                                   | Like editing in SCLM DEV (local computer)                                                           |
| git add .                                                  | Push all of DEV to INT (on the current branch) (local computer)                                     |
| git diff [--staged]                                        | See diff between DEV and INT or INT and SYS (--staged)                                              |
| git commit -m [_comment_]                                  | Push INT to SYS (on the current branch) (local computer)                                            |
|                                                            | Updates branch and logs change history (think of SYS as the change log)                             |
| git push [origin] [_branch_]                               | Push SYS to PRD (GitHub)                                                                            |
| [_make changes on github_]                                 | Like editing directly in PRD (GitHub)                                                               |
| [_commit changes button on GitHub_]                        | Commit updates branch and logs change history (think of SYS as the change log)                      |
| git pull [origin] [_branch_]                               | Pull PRD back to SYS/PRD (current branch copy on local computer)                                    |
|                                                            | Pulling from GitHub syncs local repo with remote repo                                               |
|                                                            | Reminder: pushing is preferable to pulling (because of the consistency of working on only one side) |
|                                                            |                                                                                                     |
| git remote -v                                              | Display current remote repository(s)                                                                |
| git remote add _name_ git@github.com:techistory/_name_.git | Add repository alias (git default is ORIGIN, but _techistory_ or _scripts_ is more specifc)         |
|                                                            | ORIGIN is ok because each ".git" control area is independent of each other.                         |
| git remote remove _name_                                   | Remove repository alias                                                                             |

- origin is an alias for the GitHub URL (or SSH session partner) for this user (e.g. techhistory)
