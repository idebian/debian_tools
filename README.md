debian_tools
========
It includes some debian tools for debian user


## 1.sync_git.sh
----------------
This script can sync all the folder git project.
```
Usage:
    1. Edit sync_git.sh
    2. Replace or add more array for git_proj_folder, git_folder_branch, git_remote_project
       variables.
    3. `git_proj_folder`:  Git project folder name(sometimes equals project name).
    4. `git_folder_branch`: Git project branch name
    5. `git_remote_project`: Git project repository alias name, usually called "origin" or "upstream"
    6. sh ./sync_git.sh {folder_path}
```

## Example
----------------
If you have three project named "project1, project2, project3" in /home/www/git/,
1. Modify sync_git.sh
2. Change the git_proj_folder, git_folder_branch, git_remote_project like the below:
```
git_proj_folders[1]='project1'
git_proj_folders[2]='project2'
git_proj_folders[3]='project3'
```
3. The git_folder_branch will match the branch you wish to update, if you want to update
project1->branch:master, project2->branch:develop, project3->branch:test, just change the variables.
```
git_folder_branch[1]='master'
git_folder_branch[2]='develop'
git_folder_branch[3]='test'
```
4. The git_remote_project will match the repository address, if you add others repository coming
   from co-worker and named as user1, user2, user3, You should change this part, otherwise you 
   should use the default repository name and use "origin".
```
a. Project1 is coming from Tom and wo use `git remote add tom git@github.com:xxx/project1.git` to mark as tom project1.
b. Project2 is coming from our company project2 and have only one repository, no fork repository.  So the project2 value in here should be "origin"
c. Project3 is coming from our fork repository and we named as "origin", but we add our company code repository as "upstream" using `git remote add upstream git@github.com:company/project3.git`
```
E.g.: 
```
git_remote_project[1]='tom'
git_remote_project[2]='origin'
git_remote_project[3]='upstream'
```
