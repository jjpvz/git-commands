# Git Commands
## Recording Changes to the Repository
### Check Status of Files
`$ git status`
>Untracked > files that Git doens't know about

>Tracked > files that were in the last snapshot or newly staged

>Unmodified > tracked files that haven't been edited since last commit

>Modified > tracked files that have been edited since last commit

>Staged > untracked and/or tracked modified files that have been added to the index (staging area)

### Add Precisely This Content to the Next Commit
`$ git add . #add everything` or \
`$ git add <filename> #add particular file` or \
`$ git add -p #stage hunk` or \
`$ git add -p <filename> #stage hunk from particular file`

>Note following is only relevant for editing hunks:
-- press e
-- delete with 'delete key'
-- insert with 'insert key'
-- escape insert-mode with 'esc key'
-- quit with :q!
-- save and quit with :wq 

### Show Difference Working Directory and Index
`$ git diff #shows what needs to be staged` or \
`$ git diff --cached #shows what has been staged so far`

### Save Changes to Local
`$ git commit -m "<commit message>"`

## Viewing the Commit History
### List the Commits Made in Repository in Reverse Chronological Order
`$ git log` or \
`$ git log -p #shows difference introduced in each commit` or \
`$ git log --oneline #prints each commit on a single line` or \
`$ git log --graph #adds a nice little ASCII graph showing your branch and merge history`

## Undoing Things
### Redo a Commit on Local 
`$ git commit --amend #don't do this for pushed commits` :heavy_exclamation_mark: 

### Unstaging a Staged File
`$ git reset HEAD <file> #git status reminds us` or \
`$ git restore --staged <file>`

### Discard Changes in Working Directory

`$ git checkout -- <file> #git status reminds us` :heavy_exclamation_mark:
`$ git restore <file>` :heavy_exclamation_mark:

>Stashing and branching are generally better ways to go

## Tagging

### Listing Your Tags
`$ git tag`

>More on this later

## Git Aliases

### Examples
```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status

$ git config --global alias.unstage 'reset HEAD --'
```

## Branching
### List Branches
`$ git branch`

### Create Branch
`$ git branch <newbranchname>`

### Switch to Existing Branch
`$ git checkout <branchname>` or \
`$ git switch <branchname>`

### Create and Switch to New Branch
`$ git checkout -b <newbranchname>` or \
`$ git switch -c <newbranchname>`

### Return to Previously Checked Out Branch
`$ git switch -`

### Change Branchname
`$ git branch -M <newbranchname>`