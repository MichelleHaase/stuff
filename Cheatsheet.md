# Basic Git commands 

## git add file

adds file from WDir to staging area
## git status

shows if there're untracked changes
## git commit -m "Informative Text"

commits the changes to local Repository
## git push

syncs the local with the remote repository(uploads changes)
## git mv oldFilename newFilename

renames the file, on the lvl of the operating system there is no renaming, files locations get deleted and the new name inserted at the same place. if no new name is inserted (actual deletion) the data stays and gets overwritten when new data is created in the memory space it is. Git cant discern between deleting an d renaming if its done outside of the git command because it just gets a new Address (name) for the Data, which would lead to the creation of new file in the repository with the same data but a new name. This can cost a lot of space and more important does not connect the old file to new named one. with git mv instead of just mv this is avoided,