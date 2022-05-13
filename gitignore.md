### I reserve this space to write somethings about how to use **.gitignore**

---

## How to delete files that should be in '.gitignore' but:

#### **We added to the stage area, and not did the commit yet**

To delete fiels
> git reset HEAD nombre_de_archivo

To delete folders
> git reset HEAD .

 (*Remember that with "git status" we can check if the files are no longer in progress. "Untracked files: …".*)


#### **Or we already did the commit and add the file in the repository**

To delete fiels
> git rm --cached nombre_archivo

To delete folders
> git rm -r --cached nombre_directorio

(*The parameter "--cached" is the one that allows us to keep files in our working directory.*

*Note that even if you delete files from your repository, they will still be in the repository history and therefore can be seen in previous commits, if someone is looking for them. This is because, when the changes were first committed, they were already indexed by Git and will be recorded in the old commits.*)


#### **Then make sure that our files are correctly ignored.**

Commit the changes
> git commit -am 'Deleted unwanted files'

Submit those changes to the remote repository
> git push

In case you have to specify the remote repository and the branch, it would be something like
> git push origin master
