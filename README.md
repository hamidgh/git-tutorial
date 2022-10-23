
# Setup Git (Tutorial Part 1)
### To initialize a git repository 
    git init

# Main Commands (Tutorial Part 2)
### To add (stage) a single file 
    git add <FILE/PATH>
### To add (stage) multiple files (will add new/edited/deleted files)
    git add .
### Commit staged files
    git commit -m "<YOUR COMMIT MESSAGE>"
### Add origin
    git remote add origin <ORIGNIN URL>
### Push to branch
    git push

# Undo Commands (Tutorial Part 3)
### Un-Stage
    git restore --staged <FILE/PATH>
### Un-Commit
    git reset --soft HEAD~1
### To add only modified and deleted files and not untracked (new) files
    git add -u

# branch Commands (Tutorial Part 4)

### See the list of the local branches
    git branch
### Create new branch locally
    git checkout -b <BRANCH NAME>
### Push local branch to upstream (the remote repo)
    git push remote --set
### Switch between branches
    git checkout <BRANCH NAME YOU WANT TO SWITCH TO>

# Merge Commands (Tutorial Part 5)

### Merge a branch into another branch
    git merge <BRANCH NAME YOU WANT TO BE MERGED>
### Merge a branch with an extra merge commit
    git merge <BRANCH NAME YOU WANT TO BE MERGED> --no-ff

# Rebase Commands (Tutorial Part 6)

### Rebase a branch to have the changes if the other branch
    git rebase <BRANCH NAME YOU WANT TO PULL THE CHNAGES>
### Squash multiple commits into 1 commit    
    - git rebase -i HEAD~<NUMBER OF COMMITS YOU WANT TO SQUASH>
    - It will show the last n commits that you requestd in the last command
    - Hit letter S to start modifiying and replace `pick` with `s` for the commits you want to squash
    - Always keep the first commit, that one cannot be marked with `s`
    - When you finished editing hit escape button and then type `:wq` and then hit enter
    - Now you can modify the commit message and remove the other commit messages
    - You can hit `s` letter again to start editing and you can delete the commit mesages you don't want
    - When you finished editing hit escape button and then type `:wq` and then hit enter
    - Now you can push the changes to the repository by sending command `git push --force`

### attach some changes to the previous commit 
    git commit --amend
### attach some changes to the previous commit without modifying the commit message
    git commit --amend --no-edit

# Resolve Rebase/Merge conflicts (Tutorial Part 7)

### resolve merge conflicts
    Use WebStorm tool and right click on any source file and select Git
    From git menu select `Resolve Conflicts ...` it wil show bellow options
    accept yours: disregard their chnages and only apply your changes 
    accept theirs: disregard your changes and only apply their changes
    resolve merge: manually go through the changses and check what should be included
### resolve rebase conflicts
    accept yours: disregard their chnages and only apply your changes 
    accept theirs: disregard your changes and only apply their changes
    resolve merge: manually go through the changses and check what should be included

# Handy commands (Tutorial Part 8)

### stash: You can save your un-staged changes on git and apply it again
    To save and remove your local changes use this command: git stash
    To apply the changes tha tyou saved use this command: git stash pop
### patch: Share your code change with someone else via a file
    to create the file: 
        git diff > patchFileName.patch
    to apply the file changes, copy it in the root directory of your repository and run this command: 
        git apply patchFileName.patch
### cherry-pick: If you want to only apply 1 commit to your branch
    get the commit ID of that commit and run this command
        git cherry-pick <COMMIT ID THAT YOU WANT TO HAVE>

# Other useful commands (Tutorial Part 9)

### delete all local changes including commits or staged files (**dangerous**)
    git reset --hard @{u}
### revert a specific merge commit
    git revert -m 1 <MERGE COMMIT ID>
### get logs for all git commits
    git log

# Cleanup commands (Tutorial Part 10)

### remove un-staged file
    git checkout <FILE/PATH>
### remove all un-staged files
    git checkout —- .
### remove untracked files
    git clean -df
### switched to previous branch
    git checkout -