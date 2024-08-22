---
title: "Git Workflows"
draft: true
weight: 500
---


My workflow for personal projects

- Do some small initial work locally

- `git init` my project and `git commit --all -m "initial commit"`

- Create a repo (repository) on Github

- Copy directions from Github to link an existing repo (sets important settings that are so rare I don't have them memorized)

- `git push`

- Do work, create branches, commit often, push often

- Create issues in my repo for automatic branch creation and issue tracking

- when I merge and get conflicts I open Github Desktop and then use links in the app to open my text editor and manually resolved the merge conflicts. This won't be so bad for you but it's a nightmare in big projects.

- Create a PR, self-review, squash merge, pull locally, merge to others

  

**1. Basic Workflow**

1. Initialize a repository:

• git init

2. Add files to the staging area:

• git add .

3. Commit changes:

• git commit -m "Initial commit"

4. Push changes to a remote repository:

• git push origin main

  

```bash

git init

git add .

git commit -m "Initial commit"

git push

```

  

**2. Cloning a Repository and Making Changes**

  


1. Clone a repository:

  

• git clone https://github.com/user/repo.git

  

2. Navigate into the repository directory:

  

• cd repo

  

3. Create a new branch:

  

• git branch feature-branch

  

4. Switch to the new branch:

  

• git checkout feature-branch

  

5. Make changes and add them to staging:

  

• git add .

  

6. Commit the changes:

  

• git commit -m "Added new feature"

  

7. Push the changes to the remote repository:

  

• git push origin feature-branch

  

  

**3. Branching and Merging**

  

  

1. Create and switch to a new branch:

  

• git checkout -b new-feature

  

2. Make changes and commit them:

  

• git add .

  

• git commit -m "Develop new feature"

  

3. Switch back to the main branch:

  

• git checkout main

  

4. Merge the new branch into the main branch:

  

• git merge new-feature

  

5. Push the changes to the remote repository:

  

• git push origin main

  

  

**4. Handling Merge Conflicts**

  

  

1. Fetch and merge changes from the remote repository:

  

• git fetch origin

  

• git merge origin/main

  

2. If there are conflicts, open conflicting files and resolve them.

  

3. After resolving conflicts, add the resolved files:

  

• git add .

  

4. Commit the resolved changes:

  

• git commit -m "Resolved merge conflicts"

  

5. Push the changes to the remote repository:

  

• git push origin main

  

  

**5. Using Stash to Save Work Temporarily**

  

  

1. Stash the current changes:

  

• git stash

  

2. Apply the stashed changes later:

  

• git stash apply

  

3. List all stashes:

  

• git stash list

  

4. Drop a stash:

  

• git stash drop

  

  

**6. Reverting Changes**

  

1. Revert a specific commit:

  

• git revert <commit-hash>

  

2. Reset to a previous commit (destructive):

  

• git reset --hard <commit-hash>

  
  

my list of commands

  

`init`

`switch`

`branch`

`merge`

`checkout`

`diff`

`log`

PRs

`commit`

`revert`

