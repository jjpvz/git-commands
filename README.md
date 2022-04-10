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
-- delete whole line 'dd'
-- quit with :q!
-- save and quit with :wq 

### Show Difference Working Directory and Index
`$ git diff #shows what needs to be staged` or \
`$ git diff --cached #shows what has been staged so far`

### Save Changes to Local
`$ git commit -m "<commit message>"`

## Stashing
### Stash the Changes in a Dirty Working Directory Away
`$ git stash #saves your local modifications away and reverts the working directory to match the HEAD commit` or \
`$ git stash -m "<stash message>"`

### List Modifications Stashed Away
`$ git stash list`

### Inspect Modifications Stashed Away
`$ git stash show`

### Remove Stash from List of Stashes in Repository
`$ git stash drop <stashid>`

### Apply Stash to Top of Current Working Directory and Remove From List of Stashes
`$ git stash pop <stashid>`

### Apply Stash on Top of Current Working Directory Without Removing From List of Stashes
`$ git stash apply <stashid>`

### Remove All Stashes From Repository
`$ git stash clear`

## Viewing the Commit History
### List the Commits Made in Repository in Reverse Chronological Order
`$ git log` or \
`$ git log -p #shows difference introduced in each commit` or \
`$ git log --oneline #prints each commit on a single line` or \
`$ git log --graph #adds a nice little ASCII graph showing your branch and merge history`

### Show Current Commit
`$ git show`

## Undoing Things
### Reset Branch Pointer to Point to a Different Commit
`& git reset --hard HEAD #point to commit currently sitting on` or \
`& git reset --hard HEAD^ #point to commit's parent` or \
`& git reset --hard HEAD^^ #point to commit's grandparent`

### Bring Updates in from another branch (rebase branch)
First go to feature branch,
`$ git switch <feature branchname>`

and then rebase this branch on another branch,
`$ git rebase <branchname>`

and then in case of conflicts,
`$ git status`

fix conlicts and then,
`$ git rebase --continue #when rebase conflicts have been resolved` or \
`$ git rebase --abort #when having problems and want to start over or abort`

and then in case of no conflicts check status,
`$ git status #branches have diverged`

and then,
`$ git push #rejected`
`$ git push -f #force push`

### Move commit to another branch and delete commit from old branch
First,
`$ git show #show current commit`

and then,
`$ git switch <branch> #switch branches`

and then,
`$ git cherry-pick <commit hash> #commit hash shown when 'git show', make copy of commit`

### Redo a Commit on Local 
First, 
`$ git add <filename/ -p/ .>`

and then, or skip first command and only edit commit message by doing,
`$ git commit --amend #don't do this for pushed commits` :heavy_exclamation_mark: or
`$ git commit --amend -m "<new commit message>" #don't do this for pushed commits` :heavy_exclamation_mark:

### Unstaging a Staged File
`$ git restore --staged <file> #git status reminds us`

### Discard Changes in Working Directory
`$ git checkout -- <file> #git status reminds us` :heavy_exclamation_mark: or 
`$ git restore <file> #git status reminds us` :heavy_exclamation_mark: or
`$ git restore . #discard all changes in working directory and go back to last commit`

>Stashing and branching are generally better ways to go

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

### Get Branch From Remote on Local
First,
`$ git fetch --all #fetch all branches` or \
`$ git fetch origin <branchname> #fetch this one branch`

and then,
`$ git switch <branchname> #move to branch`

## Tagging
### Listing Your Tags
`$ git tag`

### Creating Annotated Tags
`$ git tag -a <tagname> -m "<tag message>"`

> Semantic Versioning = [major].[minor].[patch]-[build/beta/rc]

### Tagging After the Fact
`$ git tag -a <tagname> <commit hash>`

### Sharing Tags
`$ git push origin <tagname>` or \
`$ git push origin --tags`

### Deleting Tags
`$ git tag -d <tagname> #local` or \
`$ git push origin --delete <tagname> #remote`

### Checking out Tags
`$ git show <tagname>`

## Git Aliases
### Examples
```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status

$ git config --global alias.unstage 'reset HEAD --'
```

### Show All Commands and Command Aliases
`$ git help -a #-a stands for --all`
