# This is an example for git cherry pick knowledge recall

### 🏳  Step 1: created a codebase and make initial commit


### 🏳  Step 2: created a develop branch


### 🏳  Step 3: created a new branch branchA and made a commit


### 🏳  Step 4.1: after branchA's WIP code changes saved/committed in branch C, we come back to branchA and cherry pick the branchC's branchA's code changes
 
### 🏳  Step 4.2: create a new branch and saved the current work progress code changes and create a commit for it 

### 🏳  Step 4.3: after resolved conflicts, branch A got branchC's branchA's temporary commit code changes. Now we can merge it to continually create the PR.


### 🏳  Step 5: created a branch D and add some code changes, so later branchD 's commit will be needed to be merged into branchB



### The whole story between branchA and branchC 📝

created `master` -> created `develop`

created `branchA` which branched out from `develop` -> make changes and commit it -> create a PR

created `branchC` which branched out from `branchA` -> create some changes for branchA only

come back to `branchA` -> make some changes in `branchA` and `stash` the changes

come back to `branchC` and find the WIP (Working In Progress) commit hash and copy the hash

come back to `branchA` and `git stash popup` -> `git cherry-pick #branchC-commit-hash`

If there are some conflicts between `branchC commit` and `branchA current stash changes`, which needs to be resolved first and then commit

optional: squash the changes before merge PR



### The whole story between branchB and branchD 📝

created `branchB` branched out from `develop`

come back to `develop` and `git pull` branchA's PR changes -> go back to branchB

in branch B, `git pull origin develop` to get latest develop code changes -> create a new file called `newTxtFile.txt` and commit it

go back to `develop` -> create a new `branchD`

go to `branchD` -> add some new changes which is later for `branchB` usage -> commit the changes -> use `git log --oneline` to get the `commit-hash` for current changes

go back to `branchB` and `git cherry-pick branchD-commit-hash`

now `branchB` got branchD's commit code changes -> create a PR and merge it into `develop`


End of story: Thanks for recall the `git cherry-pick` command, cheers ~
