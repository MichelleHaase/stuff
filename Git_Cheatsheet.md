# Basic Git commands 

### help for mess ups
[Oh shit Git](https://ohshitgit.com/)

### git clone   
    clones a remote Repository

### git add \<filename>   
    adds file from WDir to staging area

### git status   
    shows if there're untracked changes

### git commit    
    commits the changes to local Repository.   
    -m "Informative Text" - flag for direct commit message in command   
    -a - adds all changes in tracked files, doesn't add new files


### git push   
    syncs the local with the remote repository(uploads changes)

### git mv \<oldFilename> \<newFilename>   
    renames the file, on the lvl of the operating system there is no renaming, files locations get deleted and the new name inserted at the same place. if no new name is inserted (actual deletion) the data stays and gets overwritten when new data is created in the memory space it is. Git cant discern between deleting an d renaming if its done outside of the git command because it just gets a new Address (name) for the Data, which would lead to the creation of new file in the repository with the same data but a new name. This can cost a lot of space and more important does not connect the old file to new named one. with git mv instead of just mv this is avoided,

### git rm   
    same problem as with mv. Removes a file directly from Git not just the local repo, no add needed its automatically staged   

    git rm --cached stops the tracking of file in git without deleting it locally

### git pull    
    updates the local repository to the state of the remote one 
    pull requests can be made through the CLI but the webversion is a lot less complicated

### git diff HASH -- \<filename>   
    shows the difference from the file at point HASH to the main file 

### git log   
    shows all previous  Log entries for the repository including commithashes

### git restore --source=commithash \<filename>   
    gets the file as it was in the old commit
    --source=main -  with main (master in GitLab) instead of HASH the most currently pushed file gets used again. if you want to go back to a former version of file make sure the the Head(current WDir file) is on the Main(most recently pushed file) so that you stay in the main branch (so you don't actually go back to the file but reupload it as the newest Version).

### git checkout commithash
    restores all files to version of the old commit
    git checkout <branch> -  switches to a different branch 
    git checkout -b <branch> - creates branch and switches to it


### git branch <branch_name>
    creates a new branch 
    doesn't automatically check out the branch git checkout <branch_name> needed
    git branch - without anything gives anm  overview over all branches
    git branch -D <branch_name> - deletes the branch

### git reset

    --hard <commithash> - completely reverts to previous version
    --hard origin/master - reverts code back to remote Repo status
    --soft <commithash> /origin/master just changes the head, staged changes stay untouched
    --mixed <commithash> /origin/master (default) moves head to commithash unstages the current changes but leaves the WDir untouched

### git merge <branch_name>
    merges the branch <branch_name> with the current branch, so to merge into main, first checkout main then merge the side branch in. This creates a merge commit that needs to be commit before pushing. If the main branch is directly behind the side branch (no commits on master since the side branches creation) Git does a fast-forward merge and no commit is needed.
    -ff - automatically starts a fast-forward merge but aborts if it's not possible

### git tag -a <tagname> -m "Tag message"
    creates an Annotated tag with eg versionnumber as tagname and message a note to it. committing and pushing that tag makes the code at that current point reachable through that tag. Tags are immutable, can't be changed afterwards.   
    git tag -a <tagname> <commit-hash> -m "Tag message" - gives a tag to a specific earlier created commit.  
    git tag <tagname> - creates a lightweight tag, without message, email, date or the useres name
    