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
`$ git add <filename> #add particular file`

### See What is Still Unstaged
`$ git diff` or \
`$ git diff --cached #see what has been staged so far`

### Save Changes to Local
`$ git commit -m "<commit message>"`

