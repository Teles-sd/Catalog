
# GIT


This is a guide for **git** commands and the Github CLI **gh**.
<!-- --><br/>

> **Notes:**
>
>> If you want a TL;DR just for starting a Repository right away go here: [Quick Start](#quick-start-basics).  
>>
>> For more informations you can see the topics in order starting here: [Work-Tree, Index & Commits](#work-tree-index--commits).  
>>
>> See the [Glossary](#glossary) for any terms you don´t understand.  
>> 
>> Or go to the [TABLE OF CONTENT](#table-of-content) for more topics.

<!-- --><br/>



------------------------------------

### TABLE OF CONTENT <!-- omit in toc -->

- [GIT](#git)
    - [GLOSSARY](#glossary)
    - [TERMINOLOGY](#terminology)
    - [PACKAGES](#packages)
    - [REFERENCES](#references)
    - [HELP](#help)
    - [QUICK START (BASICS)](#quick-start-basics)
    - [WORK-TREE, INDEX & COMMITS](#work-tree-index--commits)
      - [Work-Tree -> Index](#work-tree---index)
      - [Index -> Revision](#index---revision)
    - [LOGS & REFLOG](#logs--reflog)
      - [Log](#log)
      - [Log Graph](#log-graph)
      - [Reflog](#reflog)
    - [BRANCHES](#branches)
    - [SPELL COMMITS](#spell-commits)
    - [REMOTES](#remotes)
    - [DIFFS](#diffs)
    - [MERGE & REBASE](#merge--rebase)
      - [Merge](#merge)
      - [Rebase](#rebase)
    - [UNDO MISTAKES](#undo-mistakes)
      - [Amend](#amend)
      - [Stash](#stash)
      - [Restore (files)](#restore-files)
      - [Reset (index)](#reset-index)
      - [Revert (commits)](#revert-commits)
      - [Example cases](#example-cases)
    - [CONFIGS](#configs)
      - [Identity](#identity)
      - [Tools config](#tools-config)
      - [Save credentials](#save-credentials)
      - [Credentials cache](#credentials-cache)
- [GITHUB COMMAND-LINE INTERFACE](#github-command-line-interface)
    - [ISSUES](#issues)
	<!-- --><br/>



------------------------------------

### GLOSSARY

- **Repository** (aka. _Local Repository_):  
  A Git Repository is the '.git/' directory inside a project, containing all the necessary repository files.
  <!-- --><br/>


- **Work-tree** (aka. _Working-tree_, _Workspace_, _Working Directory_):  
  Place where the files of a project's Repository are.  
  It is the directory where you put all the files and subdirectories of your project.
  <!-- --><br/>


- **Path component**:  
  Directories and subdirectories inside the Work-tree that lead to a file.
  <!-- --><br/>


- **Path-name**:  
  Any file inside the Commits (inside the Repository) have a Path-name.  
  The Path name is all the Path components from the Top level to where this file is in the Work-tree.  
  :warning: Never start with slash.  
  Write as: `path/to/file`.
  <!-- --><br/>


- **Top level**:  
  The path to the Work-tree on the machine.
  <!-- --><br/>


- **Index** (aka. _Staging Area_):  
  Where the files from the project are placed by git before being committed.  
  "_Staged Files_" are files tracked in the Index and staged to commit.  
  "_Not Staged Files_" are files tracked in the Index but not staged.  
  "_Tracked Files_" were once Staged, but have had changes to it.  
  "_Untracked Files_" are the ones not added to the Index.  
  Files can be added and removed from Index at will, before committing.  
  <!-- --><br/>


- **Commit** (aka. _Revision_):  
  Record of changes to the Repository's files.  
  Commits usually contain a brief message/description.  
  Each Commit creates an _hash_ (aka. _SHA_ or _ID_) to keep record of what changed, when and by who.  
  "Commit" may also be referring to the _act_ of making a Commit.
  <!-- --><br/>


- **Refname**  (aka. _Refspec_, or just _Commit_):  
  Reference to a specific Commit.  
  Another way of referencing a Commit, rather than by it´s _hash_.  
  See the [Spell Commits](#spell-commits) Section.
  <!-- --><br/>


- **Branch**:  
  A succession of Commits on the project.  
  Or an active Line of development.  
  A Git Repository can have any number of Branches.
  <!-- --><br/>


- **HEAD** (aka. _tip of that Branch_):  
  Points to the last Commit to the current Branch.  
  <!-- --><br/>


- **Clean Work-tree**:  
  When the Working-tree is identical to the current HEAD, _i.e._ all it's modifications have been committed to the current Branch.
  <!-- --><br/>


- **Dirty Work-tree**:  
  When a Work-tree contains modifications which have not been committed to the current Branch.
  <!-- --><br/>


- **Remote** (aka. _Remote Repository_, _Upstream Repository_):  
  A Repository to track the project, but residing somewhere else.  
  Might be on another directory on the machine or in another machine, locally or remotely.
  <!-- --><br/>


- **Fetch**:  
  Get a Branches’ HEAD ref from a Remote repository.  
  This fetched HEAD will be referred to as "_FETCH_HEAD_".  
  Needed to find out which objects from the local Repository are missing on the Remote.
  <!-- --><br/>

- **Push**:  
  Updating a Remote Branch with a local Branch's content.  
  If the Remote HEAD is not ancestor to the local HEAD, the push fails.
  <!-- --><br/>


- **Merge**:  
  Incorporate, on current Branch, changes from other Branch's Commits since the time their histories diverged.
  Records all the results in a new Commit.  
  For a more in depth explanation go [here][Merge Rebase].
  <!-- --><br/>


- **Rebase**:  
  Incorporate on current Branch changes from other Branch's commit by rewriting the Commit history.
  Takes each Commit of the rebased Branch and produces a linear succession of new Commits.  
  For a more in depth explanation go [here][Merge Rebase].
  <!-- --><br/>


- **Nested repository**:  
  A Repository (and Work-tree) that is in another Repository's Work-tree.  
  Git do not store files or directories with a `.git/` Path component.  
  Thus, a Repository don't store another Repositories within it.  
  You can create a Git Repository within the Work-tree of another Git repository, but you can't add and commit one to the other.
  <!-- --><br/>


- **Submodules**:  
  A Git Repository that is referred to in another Git Repository.
  <!-- --><br/>
  <!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### TERMINOLOGY


| Term/Expression | Meaning |
| --------------: | :------ |
| `<description>` | To replace, or that will be replaced, according to description. |
|           `...` | Possible to repeated pattern.                                   |
|             `$` | Some command to be used on the Terminal (shell).                |
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PACKAGES


| Source |    Package    | Description |
| :----: | :-----------: | ----------- |
| pacman | git           | The fast distributed version control system. (pacman) <br/> The stupid content tracker. (man-page) |
| pacman | gigithub-clit | The GitHub CLI |
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



----------------------------------

### REFERENCES

- [Home Page][git]


- [Documentation][doc]


- [Atlassian Tutorials][atlassian]


- [Git Cheatsheet][cheat]


- [Github Guides][guides]


- [Mastering Issues - Github Guides][issues]


- [Github CLI][gh]
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



[git]:https://git-scm.com/ "Git Home Page"
[doc]:https://git-scm.com/doc "Git Documentation"

[atlassian]:https://www.atlassian.com/git/tutorials "Atlassian Tutorials"
[cheat]:https://ndpsoftware.com/git-cheatsheet.html#loc=index "Git Cheatsheet"

[guides]:https://guides.github.com/ "Github Guides"
[issues]:https://guides.github.com/features/issues/ "Mastering Issues"
[gh]:https://cli.github.com/ "Github CLI"

[Merge Rebase]:https://www.atlassian.com/git/tutorials/merging-vs-rebasing "Merging vs. Rebasing"
[gpg-signature]:https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification/about-commit-signature-verification#gpg-commit-signature-verification "GPG commit signature verification"

[tree1]:./imgs/git_commits_horiz.png
[tree2]:./imgs/git_commits_vert.png

------------------------------------

### HELP

- Help:

```shell
$ git help
```
<!-- --><br/>


- Manuals about specific Git´s commands:

```shell
$ git help <command>
```

```shell
$ man git-<command>
```
<!-- --><br/>


- Official Glossary (confusing a.f.):

```shell
$ man gitglossary
```

```shell
$ git help gitglossary
```
<!-- --><br/>


- More info on spell Commits:

```shell
$ man gitrevisions
```

```shell
$ git help gitrevisions
```
<!-- --><br/>


- REALLY good tutorials:  
  [Atlassian Tutorials][atlassian]
  <!-- --><br/>
  <!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>




------------------------------------

### QUICK START (BASICS)
<!-- --><br/>

> **Note:**
> 
> This is a "TL;DR section" for starting a Repository right away.
> For more details see the other sections.
> 
> **Tip:**
> 
> See [Identity](#identity) section for how to configure identity.
>

<!-- --><br/>



- Create a local Repository:

```shell
$ cd <path>
```

```shell
$ git init
```
<!-- --><br/>


- Add a Remote (previously created on the Github or other website):

```shell
$ git remote add <name> <url>`  
Eg.:  
```shell
$ git remote add origin https://github.com/<user>/<repo>
```
<!-- --><br/>


- Display Remotes:

```shell
$ git remote -v
```
<!-- --><br/>


- Fetch and Merge Branch from a Remote.  
  Not needed if the Remote is empty.

```shell
$ git pull <remote> <branch>`  
Eg.:  
```shell
$ git pull origin master
```
<!-- --><br/>


- Add all files from the Work-tree to Index:

```shell
$ git add .
```
<!-- --><br/>


- Display updates to the Index:

```shell
$ git status
```
<!-- --><br/>


- Commit contents of Index to current Branch, with a log message:

```shell
$ git commit -m '<log-message>'
```
<!-- --><br/>


- Update a Remote Branch with the current Branch's contents (Branches with same name):

```shell
$ git push <remote> <branch>`  
Eg.:  
```shell
$ git push origin master
```
<!-- --><br/>
<!-- --><br/>



- List local Branches in Repository:

```shell
$ git branch
```
<!-- --><br/>


- List Remote Branches:

```shell
$ git branch -r
```
<!-- --><br/>


- List all Branches:

```shell
$ git branch -a
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### WORK-TREE, INDEX & COMMITS
<!-- --><br/>

#### Work-Tree -> Index

- Display current Branch's Index (staged and untracked files):

```shell
$ git status
```
<!-- --><br/>


- List all file from Index AND Work-tree:

```shell
$ git ls-files
```
<!-- --><br/>


- Add specific file (or files) from the Work-tree to Index:

```shell
$ git add <file>
```

```shell
$ git add <file> ... <file>
```
<!-- --><br/>


- Add all files from the Work-tree to Index:

```shell
$ git add .
```
<!-- --><br/>


- Updated Tracked (in Index) files from Working-tree to Index:

```shell
$ git add -u
```

```shell
$ git add --update
```
<!-- --><br/>


- Remove file from Index and **Work-tree**:

```shell
$ git rm <file>
```
<!-- --><br/>


- Move file on Work-tree and Index:

```shell
$ git mv <file> <destination>
```
<!-- --><br/>
<!-- --><br/>




#### Index -> Revision

> **Tip:**
>
> It is a good practice ~~(that I do not have :smile: )~~ to not mix different topics in the same commit.
>

<!-- --><br/>


- Commit contents of Index to current Branch, with a log message:

```shell
$ git commit -m '<log-message>'
```

> **Tip:**
>
> By prefacing the Commit message with “Fixes”, “Fixed”, “Fix”, “Closes”, “Closed”, or “Close” followed by "#`<github-issue>`", when the commit is merged into main, it will also automatically close the issue.
> 
> See more on [Mastering Issues - Github Guides][issues].
> 

<!-- --><br/>


- Automatically add Staged files to Commit:

```shell
$ git commit -a
```

```shell
$ git commit --all
```
<!-- --><br/>


- Show summary of what's included on next commit.  
  DOES NOT Commit.

```shell
$ git commit --dry-run
```
<!-- --><br/>


- Commit only changes made on a specific Path-name (ignore Index):

```shell
$ git commit <path-name>
```
<!-- --><br/>


- Update the last commit by adding the currently staged changes:  
  :warning: **WARNING:** This command rewrites history. Never rewrite history of Remotes that other people work on.

```shell
$ git commit --amend
```
<!-- --><br/>


- Amend HEAD and suppress Editor´s opening:  
  :warning: **WARNING:** This command rewrites history. Never rewrite history of Remotes that other people work on.

```shell
$ git commit --amend --no-edit
```
<!-- --><br/>


- Amend HEAD and further edit the message (opens Editor):  
  :warning: **WARNING:** This command rewrites history. Never rewrite history of Remotes that other people work on.

```shell
$ git commit -m '<log-message>' --edit
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### LOGS & REFLOG
<!-- --><br/>

#### Log

**Follows _chronological_ order.**
<!-- --><br/>

- Display Commit history from current Branch:

```shell
$ git log
```

```shell
$ git log --oneline
```
<!-- --><br/>


- Limit the number of commits to output:

```shell
$ git log -<number>
```

```shell
$ git log -n <number>
```

```shell
$ git log --max-count=<number>
```
<!-- --><br/>


- Show only Commits done on the current Branch (excluding Commits done on other Branches before Merging):

```shell
$ git log --first-parent
```
<!-- --><br/>


- "Pretty" Log:

```shell
$ git log --pretty="format:%h %ar %s"
```
<!-- --><br/>
<!-- --><br/>



#### Log Graph

**Follows _topological_ ordering, not chronological order.**
<!-- --><br/>

- Display a log graph for the Commits and Merges:

```shell
$ git log --graph
```
<!-- --><br/>


- Display compact graph of all Branches:

```shell
$ git log --graph --oneline --all
```
<!-- --><br/>
<!-- --><br/>



#### Reflog

**Reflog records changes on the HEAD pointer.**  
That is, records updates to the tip of the Branch: switches, amends, resets...
<!-- --><br/>

- Display Reflog:

```shell
$ git reflog
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### BRANCHES


- Create a new Branch starting from current HEAD:

```shell
$ git branch <name>
```


- Create a new Branch starting from a previous commit:

```shell
$ git branch <name> <commit>
```
<!-- --><br/>
<!-- --><br/>



- List local Branches in Repository:

```shell
$ git branch
```

```shell
$ git branch -l
```

```shell
$ git branch -l '<pattern>'
```

```shell
$ git branch --list
```
<!-- --><br/>


- List Remote Branches:

```shell
$ git branch -r
```

```shell
$ git branch -rl '<pattern>'
```

```shell
$ git branch --remotes
```
<!-- --><br/>


- List all Branches:

```shell
$ git branch -a
```

```shell
$ git branch -al '<pattern>'
```

```shell
$ git branch --all
```
<!-- --><br/>
<!-- --><br/>



- Rename Branch:

```shell
$ git branch -m <branch> <new-name>
```

```shell
$ git branch --move <branch> <new-name>
```
<!-- --><br/>
<!-- --><br/>



- Switch Branch.
  Switching Branch updates Index and Work-tree.  
  Does not require a clean index and working tree.  
  But it is recommended Commit or Stash before switching.
  The operation is aborted if leads to loss of local changes.  

```shell
$ git switch <branch>
```
<!-- --><br/>


- Switch to last Branch:

```shell
$ git switch -
```
<!-- --><br/>
<!-- --><br/>



- Delete Branch:

```shell
$ git branch -d <branch>
```
<!-- --><br/>


- Delete Branch even if current Branch doesn't have all commits from it:

```shell
$ git branch -D <branch>
```
<!-- --><br/>


- Delete remote Branch from local Repo:

```shell
$ git branch -rd <branch>
```
<!-- --><br/>


- Delete remote Branch from remote Repo:

```shell
$ git push <remote> --delete <branch>
```
<!-- --><br/>


- Recover a deleted branch (search it on the Reflog):

```shell
$ git reflog
```

```shell
$ git branch <name> <commit>
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### SPELL COMMITS

**Refname (OR _REFSPEC_): How to refer to a specific Commit.**
<!-- --><br/>



- By **Hash** (a.k.a. _SHA-1_):

  The full SHA-1 object name is a 40-byte hexadecimal string.  
  It can be referred to by it's short version (a leading substring that is unique within the Repository).
  
    - See it's short version with:  
      ```shell
      $ git log --oneline
      ```
    
    - Or, it's full version with:  
      ```shell
      $ git log
      ```
      <!-- --><br/>



- **Refnames:**

| Ref             | Refers to |
| :-------------: | :-------- |
| HEAD            | The last Commit of current Branch. |
| `<branch-name>` | Will refer to the specified Branch's HEAD |
| FETCH_HEAD      | The last Commit of the Branch fetched from Remote with:<br/>`git fetch <remote> <branch>`. |
| ORIG_HEAD       | Records Commit before operations that move HEAD in drastic way (eg. `git merge <branch>`). |
| MERGE_HEAD      | Records Commit of the Branch that merges into current Branch. |
| CHERRY_PICK_HEAD| Records the Commit of:<br/>`git cherry-pick`.<br/>~~Doesn´t seems complicated, but I don´t know what that is.<br/>It has something to do with picking just some chunks of code to commit (I think).~~ |
<!-- --><br/>



- **Refnames for prior Commits:**

  - _Parent Commits_:
  
    A Commit might have multiple parent in case of a merge.  
    A Commit with the suffix `^` and a number (n) refers the n-th Parent of that Commit.

    `<commit>^<n>`  
    `<branch>^{<n>}`

    DOES NOT Follow chronological order.  
    Goes as in `git log --graph`.

    > `<commit>^` is equivalent to `<commit>^1`
    <!-- --><br/>

  - _Ancestor Commit_:
  
    A Commit with the suffix `~` and a number (n) refers the n-th Ancestor of that Commit, following only the first parents (ORIG_HEAD).
    
    `<commit>~<n>`
    `<branch>~{<n>}`
    
    DOES NOT Follow chronological order.
    Goes as in `git log --graph`.
    
    > `<commit>~`  is equivalent to `<commit>~1`
    >
    > `<commit>~3` is equivalent to `<commit>^^^`,
    > which is equivalent to `<commit>^1^1^1`,
    > but NOT `<commit>^3`.
    <!-- --><br/>

> **Example**
>
> Consider this Branch described and drawn below:
> 1. Commit `F` receives a Commit and becomes `E`.
> 1. Commit `E` receives a Commit and becomes `B`.
> 1. Commit `B` merges `C` and `D`; and becomes `A`.
>
> | From Left to Right | From bottom to top |
> | :----------------: | :----------------: |
> |    ![][tree1]    |    ![][tree2]    |
>
> In this case:
> 
> `A~1` = B
> `A~2` = E
> `A~3` = F        = `A^^^` = `A^1^1^1`
> 
> `A^1` = B        = `A^`
> `A^2` = C
> `A^3` = D
<!-- --><br/>



- More info on spell Commits:

```shell
$ man gitrevisions
```

```shell
$ git help gitrevisions
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### REMOTES

- Previously create a Remote Repository on Github or other website.

- If the Repository is a existent on-going project, don't initialize with README file to avoid errors on push.
<!-- --><br/>



- Add a Remote to Local Repository:

```shell
$ git remote add <name> <url>
```
Eg.:  
```shell
$ git remote add origin https://github.com/<user>/<repo>
```
<!-- --><br/>


- Display Remotes:

```shell
$ git remote
```

```shell
$ git remote -v
```
<!-- --><br/>


- Rename a Remote:

```shell
$ git remote rename <remote> <new-name>
```
<!-- --><br/>


- Remove a Remote:

```shell
$ git remote rm <remote>
```

```shell
$ git remote remove <remote>
```
<!-- --><br/>
<!-- --><br/>


- Delete an Upstream Branch:

```shell
$ git branch -rd <remote>/<branch>
```
<!-- --><br/>
<!-- --><br/>


- Update Branches seen from Remote:

```shell
$ git fetch <remote> <branch>
```
<!-- --><br/>


- Fetch and Merge Branch from Remote Branch:

```shell
$ git pull <remote> <branch>
```
Eg.:  
```shell
$ git pull origin master
```
<!-- --><br/>


- Download Repository a Remote (master branch):

```shell
$ git clone <url>
```
<!-- --><br/>


- Download a specific Branch from a Remote:

```shell
$ git clone -b <branch> <url>
```
<!-- --><br/>
<!-- --><br/>



- Push to a Remote Branch (Branches must have same name):

```shell
$ git push <remote> <branch>
```
<!-- --><br/>

- Push from a Branch to Another Branch:

```shell
$ git push <remote> <source_branch>:<destine_branch>
```
<!-- --><br/>


> :warning: **WARNING:**
>> Usually git refuses to update a Remote Branch that is not an ancestor of the local.
>> This can happen in cases the _history is rewritten_.
>> The flag `--force` disables these checks, and can cause the Remote to lose commits.
>> Use it with care.
<!-- --><br/>

- Force Push to Remote Branch:

```shell
$ git push <remote> <branch> --force
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DIFFS

- Almost all those commands can be used with a external tool intead of `diff`.  
  See [Tools Configuration](#tools-config) section to see how to define a `difftool`.

```shell
$ git difftool
```
<!-- --><br/>
<!-- --><br/>


- Get an an idea of the amount of work done:

```shell
$ git diff --stat
```
<!-- --><br/>
<!-- --><br/>



- View changes in Work-tree, relative to a Commit (default=HEAD):

```shell
$ git diff <commit>
```

```shell
$ git diff
```
<!-- --><br/>


- To examine the Staged changes:

```shell
$ git diff --cached
```

```shell
$ git diff <commit> --cached 
```
<!-- --><br/>


- View only the name of the files that have changes:

```shell
$ git diff --name-only <commit>
```

```shell
$ git diff --name-only
```
<!-- --><br/>


- View changes Between Commits:

```shell
$ git diff <commit>..<commit>
```

```shell
$ git diff --name-only <commit>..<commit>
```
<!-- --><br/>


- View changes in a specific file, relative to a Commit:

```shell
$ git diff <commit> <file>
```

```shell
$ git diff <file>
```
<!-- --><br/>


- View changes in Work-tree relative to the tip of another Branch:

```shell
$ git diff <branch>
```
<!-- --><br/>


- View changes in Work-tree relative to the tip of Remote Branch:

```shell
$ git fetch <remote> <branch>
```
```shell
$ git diff FETCH_HEAD
```
<!-- --><br/>
<!-- --><br/>



- View changes Between Commits on Github:

```
https://github.com/<user>/<repo>/compare/<commit>..<commit>
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### MERGE & REBASE

> :warning: **WARNING:**
> 
> Running `git merge` or `git rebase` with uncommitted changes (Dirty Work-tree) is highly discouraged.

> :warning: **WARNING:**
> 
> Never `git rebase` a public Branch.
> Also, avoid rebasing the master Branch.
> 

<!-- --><br/>
<!-- --><br/>



#### Merge

Incorporates, on current Branch, changes from other Branch's commit.  
Records the result in a new commit.  
For a more in depth explanation go [here][Merge Rebase].
<!-- --><br/>


- Merge other Branch's HEAD into current Branch:

```shell
$ git merge <branch>
```

```shell
$ git merge <branch> -m '<log-message>'
```
<!-- --><br/>


- Merge other Branch's commit into current Branch:

```shell
$ git merge <commit>
```

```shell
$ git merge <commit> -m '<log-message>'
```
<!-- --><br/>


- Perform the Merge but stop just before creating a merge commit.  
  Give the user a chance to inspect and further tweak the merge result before committing.  
  Also, to ensure your branch is not changed or updated by the merge command, use `--no-ff` to avoid fast-forward updates.

```shell
$ git merge --no-commit --no-ff <branch>
```
<!-- --><br/>


- To examine the staged changes:

```shell
$ git diff --cached
```
<!-- --><br/>


- If (and only if) the merge has resulted in conflicts, the following commands are available.  
  See [Tools Configuration](#tools-config) section to see how to define a `mergetool`.

```shell
$ git mergetool
```

```shell
$ git merge --continue
```

```shell
$ git merge --abort
```

```shell
$ git merge --quit
```
<!-- --><br/>
<!-- --><br/>



#### Rebase

Incorporates on current Branch changes from other Branch's commit.  
Does this by **rewriting the Commit history**.  
Takes each Commit of the rebased Branch and creates a linear succession of new Commits.

Rebase can also be done from the own Branch´s past Commit.  
This is done to Rewrite history.  
For a more in depth explanation go [here][Merge Rebase].
<!-- --><br/>


- Rebase current Branch starting on other Branch´s HEAD:

```shell
$ git rebase <branch>
```

```shell
$ git rebase -i <branch>
```
<!-- --><br/>


- Rebase current Branch starting on a previous Commit:

```shell
$ git rebase <commit>
```
<!-- --><br/>



- Interactive Rebase.  
  The next file that will open is **only** to declare to git what it is going to do.  
  In this file, Commits can be re-ordered.  
  :warning: Be careful not to erase a Commit. Erased Commits will be **lost**.  
  Every Commit needs a command to be specified:

| Command | What it does                                                       |
| :-----: | :----------------------------------------------------------------- |
|  pick   | Use commit as it is.                                               |
| reword  | Use commit, but edit the commit message.                           |
|  edit   | Use commit, but stop for manual amending.                          |
| squash  | Use commit, but combine into previous commit. Saves both messages. |
|  fixup  | Same as squash, except this Commit´s message is ignored.           |
|  drop   | Remove commit.                                                     |

- Save and close.  
  ONLY after this make the desired changes.
  <!-- --><br/>


- Interactive Rebase current Branch starting on a previous Commit:

```shell
$ git rebase -i <commit>
```
<!-- --><br/>


- If you use the ´edit´ command, after you´re done, use:

```shell
$ git rebase --continue
```
<!-- --><br/>


- Add change to old Commits:

```shell
$ git commit --fixup <wrong-commit>
```
```shell
$ git rebase -i --autosquash <wrong-commit>~1
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>


------------------------------------

### UNDO MISTAKES
<!-- --><br/>


#### Amend

Only used for changes on the very last Commit.

> :warning: **WARNING:** 
>> This command rewrites history.
>> Never rewrite history of Remotes that other people work on.
<!-- --><br/>


- Replace the HEAD by creating a new commit adding the current Index:

```shell
$ git commit --amend
```
<!-- --><br/>


- Amend HEAD with new message:

```shell
$ git commit --amend -m "<log-message>"
```
<!-- --><br/>


- Amend HEAD, suppress Editor´s opening:

```shell
$ git commit --amend --no-edit
```
<!-- --><br/>


- Amend HEAD and further edit the message (opens Editor):

```shell
$ git commit -m '<log-message>' --edit
```
<!-- --><br/>


- Automatically add Staged files:

```shell
$ git commit --amend -a
```

```shell
$ git commit --amend --all
```
<!-- --><br/>


- Get a summary without committing:

```shell
$ git commit --amend --dry-run
```
<!-- --><br/>


- Fix identity of previous commit.  
  See [Identity](#identity) section for how to configure identity.

```shell
$ git commit --amend --reset-author
```
<!-- --><br/>
<!-- --><br/>



#### Stash

Hides modifications (making the Work-Tree clean) to work on something else.
After saving the Stash, [Resets](#reset-index) Work-Tree and Index.
<!-- --><br/>


- Save local modifications to a new Stash:

```shell
$ git stash
```

```shell
$ git stash -m <log-message>
```
<!-- --><br/>


- List the saved Stashes:

```shell
$ git stash list
```

```shell
$ git stash list --oneline
```
<!-- --><br/>


- Show changes between Stash and it´s parent:

```shell
$ git stash show
```

```shell
$ git stash show --name-only
```

```shell
$ git stash show <stash>
```
<!-- --><br/>


- Apply Stash (default: last one) on top of current Work-Tree, and delete it:

```shell
$ git stash pop
```

```shell
$ git stash pop <stash>
```
<!-- --><br/>


- Apply last Stash on top of current Work-Tree, without deleting the Stash:

```shell
$ git stash apply
```

```shell
$ git stash apply <stash>
```
<!-- --><br/>


- If `stash-pop` or `stash-apply` results in conflicts, you have to resolve them manually.  
  You can make use of a external merge tool.
  See [Tools Configuration](#tools-config) section to see how to define a `mergetool`.

```shell
$ git mergetool
```
<!-- --><br/>


- Remove a Stash from the Stash-list:

```shell
$ git stash drop
```

```shell
$ git stash drop <stash>
```
<!-- --><br/>


- Remova ALL Stashes from the Stash-list:

```shell
$ git stash clear
```
<!-- --><br/>


- Create a Stash entry and return its object name, without storing it (only useful for scripts):

```shell
$ git stash create
```
<!-- --><br/>
<!-- --><br/>



#### Restore (files)

Restores the previous state of a file.
Can restore deleted files.

> :warning: **WARNING:**
>
> > Discarting uncommitted local changes cannot be undone.


- Restore a File from Index (default) to Work-tree (default):

```shell
$ git restore <file>
```

```shell
$ git restore -W <file>
```

```shell
$ git restore --worktree <file>
```
<!-- --><br/>


- Restore just a hunk of changes in a file (interactive):

```shell
$ git restore -p <file>
```

```shell
$ git restore --patch <file>
```
<!-- --><br/>


- Restore **whole** Work-Tree to match the Index (discarts ALL local Not Staged changes, leaves Work-Tree clean):

```shell
$ git restore .
```
<!-- --><br/>


- Restore a File from HEAD to the Index:

```shell
$ git restore -S <file>
```

```shell
$ git restore --staged <file>
```
<!-- --><br/>


- Restore a File from HEAD to Index and Work-tree:

```shell
$ git restore -SW <file>
```
<!-- --><br/>


- Restore to from a previous Commit:

```shell
$ git restore --source <commit> <file>
```
<!-- --><br/>
<!-- --><br/>



#### Reset (index)

> :warning: **WARNING:**
>> When Reseting to a Commit older than HEAD, it deletes Commits after it.
>> Be careful to not loose Commits by mistake.
>> This command _might_ rewrite history.
>> Never rewrite history of Remotes that other people work on.

- Reset only Index (default) to a previous Commit (default=HEAD):

```shell
$ git reset
```

```shell
$ git reset <commit>
```

```shell
$ git reset --mixed
```
<!-- --><br/>


- Reset Index AND Work-tree to a previous Commit (default=HEAD):

```shell
$ git reset --hard
```

```shell
$ git reset --hard <commit>
```
<!-- --><br/>


- Reset current HEAD (not Index, nor Working-tree) to a previous Commit:

```shell
$ git reset --soft <commit>
```
<!-- --><br/>
<!-- --><br/>




#### Revert (commits)

- Creates a new Commit that Reverts changes of a previous Commit without deleting it.
- Requieres Clean Work-Tree.

- Reverting the HEAD to a previous Commit:
```shell
$ git revert <commit>
```
<!-- --><br/>
<!-- --><br/>



#### Example cases

- Moving Commits from current Branch to a NEW Branch:

```shell
$ git reflog                      # write the hash of the one you wanna remove
$ git branch <branch> <commmit>
$ reset --hard <commmit>~1
```
<!-- --><br/>
<!-- --><br/>


- Moving `n` previous Commits from current Branch to an existing Branch:

```shell
$ git reset --soft HEAD~<n>
$ git stash
$ git switch <branch>
$ git stash pop
$ git add .
$ git status
$ git commit -m "<log-message>"
```

- Or:

```shell
$ git log --oneline               # write the hash of the one you wanna keep
$ git reset --hard HEAD~<n>
$ git switch <branch>
$ git reset --hard <commit>
```  
<!-- --><br/>
<!-- --><br/>


- Change Author of older Commits.
  See [Identity](#identity) section for how to configure identity.

```shell
$ git rebase -i <commit>  
```
Change command on the Commit from ´pick´ to ´edit´.  Save and Exit. Then:  
```shell
$ git commit --amend --reset-author --no-edit
$ git rebase --continue
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### CONFIGS

- Global config file:

```
~/.gitconfig
```
<!-- --><br/>


- Check personal configurations:

```shell
$ git config --list
```
<!-- --><br/>


- View all settings and where they are coming from:

```shell
$ git config --list --show-origin
```
<!-- --><br/>


- Reset some configuration:

```shell
$ git config --global --unset-all <config>
```

```shell
$ git config --unset-all <config>
```
<!-- --><br/>
<!-- --><br/>



#### Identity

The author of the commits.
<!-- --><br/>


- Configure Global User name:

```shell
$ git config --global user.name '<name>'
```
<!-- --><br/>


- Configure Global User e-mail:

```shell
$ git config --global user.email <email>
```
<!-- --><br/>


- Configure username for a URL:

```shell
$ git config --global credential.<url>.username <username>
```
Eg.:
```shell
$ git config --global credential.https://github.com.username <username>
```
<!-- --><br/>


- Configure User name and e-mail for a specific repo:

```shell
$ git config user.name '<name>'
```

```shell
$ git config user.email <email>
```
<!-- --><br/>


- Fix identity of previous commit:

```shell
$ git commit --amend --reset-author
```
<!-- --><br/>

- To verify identity on Github, follow [these steps][gpg-signature].
<!-- --><br/>
<!-- --><br/>



#### Tools config

> **Note:**
>> Other editors than Vim, Nano, Emacs..., might need other configurations.
>> Google it.
<!-- --><br/>


- Configure Global default text editor:

```shell
$ git config --global core.editor <text-editor>
```

```shell
$ git config --global core.editor vim
```

```shell
$ git config --global core.editor 'nano -w'
```

```shell
$ git config --global core.editor 'kate -b'
```
<!-- --><br/>


- Configure diff tool:

```shell
$ git config --global diff.tool <diff-tool>
```
<!-- --><br/>


- Configure Merge conflict diff tool:

```shell
$ git config --global merge.tool <diff-tool>
```
<!-- --><br/>


- For Meld:

```shell
$ git config --global diff.tool meld
```

```shell
$ git config --global difftool.prompt false
```

```shell
$ git config --global merge.tool meld
```

```shell
$ git config --global mergetool.prompt false
```
<!-- --><br/>
<!-- --><br/>



#### Save credentials

- Using the package 'libsecret' to store credentials:
  - On Arch:  
  
  ```shell
  $ git config --global credential.helper /usr/lib/git-core/git-credential-libsecret`  
  ```
  
  - On Fedora:  
  
  ```shell
  $ dnf install git-credential-libsecret
  $ git config --global credential.helper /usr/libexec/git-core/git-credential-libsecret
  ```
  
  - On Ubuntu:  
  
  ```shell
  $ cd /usr/share/git/credential/libsecret
  $ sudo make
  $ git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
  ```
  <!-- --><br/>
  <!-- --><br/>


- To make it so the keyring-daemon starts on login (**for SDDM**) make sure the following lines are on `/etc/pam.d/sddm` (at the end of the ´auth´, ´session´ and ´password´ sections):

```
auth       optional     pam_gnome_keyring.so
session    optional     pam_gnome_keyring.so auto_start
password   optional     pam_gnome_keyring.so use_authtok
```
<!-- --><br/>
<!-- --><br/>



#### Credentials cache

- Store password on cache (default: 15 min):

```shell
$ git config --global credential.helper cache
```
<!-- --><br/>


- Display time limit of credentials cache:

```shell
$ git config --global credential.helper
```
<!-- --><br/>


- Change time limit of credentials cache ('time' in seconds):

```shell
$ git config --global credential.helper 'cache --timeout=<time>'
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

# GITHUB COMMAND-LINE INTERFACE

- Authenticate with your GitHub account:

```shell
$ gh auth login
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### ISSUES

- List and filter issues in this repository:

```shell
$ gh issue list
```
```shell
$ gh issue list -l "<label>"
```
```shell
$ gh issue list -l "<label>" -l "<label>"
```
```shell
$ gh issue list --search "<search-term>"
```
```shell
$ gh issue list --state <state>
```
<!-- --><br/>


- Display the title, body, and other information about an issue:

```shell
$ gh issue view <number>
```
<!-- --><br/>


- Quickly open an item in the browser:

```shell
$ gh issue view <number> --web
```
```shell
$ gh issue view <number> -w
```
<!-- --><br/>
<!-- --><br/>



Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------

