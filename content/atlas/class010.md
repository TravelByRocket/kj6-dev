---
title: "1: August 26"
draft: true
weight: 10
---
Environment Setup, Git Basics, Basic Views (part 1)

## Introduction

- Instructor Introduction
	- Background
	- ATLAS
	- Current Role
		- Swift+SwiftUI
		- `git`
		- Figma
		- Designers
		- QA
		- I18n
		- A11y
		- CI/CD
	- Side Apps
- Goals
	- Quickly Make First App(s)
	- Creative+Industry Practices
- Questions
	- Experience?
	- Motivation?
	- Hopes?

"Set up the environment"
## Swift

[Swift.org](https://www.swift.org)
[The Basics](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics/)
The even have a nice little tutorial for [Build an iOS app with SwiftUI](https://www.swift.org/getting-started/swiftui/)

- Open source language
- Community
- [Kodeco Style Guide](https://github.com/kodecocodes/swift-style-guide)
- Basic types
- Make a struct
- Value Types
- Reference Types
- Protocols

## Swift and SwiftUI
- SwiftUI
	- [WWDC20 Introduction to SwiftUI](https://developer.apple.com/videos/play/wwdc2020/10119)
	- [WWDC24 SwiftUI Essentials](https://developer.apple.com/videos/play/wwdc2024/10150/)
	- Closed source from Apple
	- Framework
	- Show Example
		- Text
		- Image
		- Button
		- padding
		- background
		- overlay
		- foreground style
		- shapes

[WWDC19 Introducing SF Symbols](https://developer.apple.com/videos/play/wwdc2019/206/)
[WWDC21 SF Symbols in SwiftUI](https://developer.apple.com/videos/play/wwdc2021/10349/)
## Xcode

- [WWCD24 XCode Essentials](https://developer.apple.com/videos/play/wwdc2024/10181/)
- [Xcode Developer Documentation](https://developer.apple.com/documentation/xcode)
- I will have Beta so you can use anything
- The min is the current latest
	- 15.4 as of July 23, 2024
- Installation
	- App Store
	- Xcodes
- New Project
	- The famous Shift-Cmd-N
	- iOS App
	- Identifier
- Branch Dropdown
- Simulator
	- Differences from physical device
	- Not 100% necessary for iOS dev
- Preview
- Navigator
- Source Control
- Console Output
- Settings
	- Login
	- Text Editing
		- Trim trailing whitespace
		- Including white-space only lines
		- Re-indent on paste
	- Ctrl-I to indent
- Documentation
- Component Library
- Developer Account

## Apple Developer Account

## Github

consider GH classroom
issues workflow

## git
Xcode, CLI, website

Can sufficiently use version control from Xcode https://developer.apple.com/documentation/xcode/source-control-management

But that does not appear to be the norm

My coworkers are surprised to see me just switching branches in Xcode

gitignore

suggest SSH but that's left to reader https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui

branch naming conventions (note about noninclusive language) https://itconnect.uw.edu/guides-by-topic/identity-diversity-inclusion//inclusive-language-guide/

  

https://git-scm.com

  

I've read that git comes with the mac developer tools download but I'd suggest just using the homebrew version

https://learngitbranching.js.org

https://brew.sh

https://formulae.brew.sh/formula/git

https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git

https://training.github.com/downloads/github-git-cheat-sheet.pdf

https://www.codecademy.com/learn/learn-git

https://www.pluralsight.com/courses/code-school-git-real

  

https://gist.github.com/subfuzion/db7f57fff2fb6998a16c

  

https://www.toptal.com/developers/gitignore

https://www.toptal.com/developers/gitignore/api/xcode,macos,visualstudiocode

https://www.toptal.com/developers/gitignore?templates=xcode,swift,macos,visualstudiocode,python,carthage,swiftpackagemanager,cocoapods

initial git setup (username, password/auth, )

ignore case false

global gitignore

check with `which git`

success if you can pull and push

  
  
  

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

  

Recommended Tools

- Visual Studio Code

- Github Desktop

  

**Basic Git Commands**

  

• git init

• git clone

• git add

• git commit

• git status

• git push

• git pull

• git fetch

• git merge

• git branch

• git checkout (esp. for getting a file from another branch)

  

**Advanced Git Commands**

  

• git log

• git diff

• git reset

• git revert

• git stash

• git remote

• git tag

• git rm

  
  

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

## Other Tools
- [Xcodes](https://www.xcodes.app)
- [Obsidian](https://obsidian.md)
- [Homebrew](https://brew.sh)
- Copilot
	- Autocomplete
	- Language questions
	- Bash scripts
- Visual Studio Code
- Sublime Text
- Swiftformat
- Swiftlint
- SF Symbols

Send in your github account for an invite to the classroom

join link https://classroom.github.com/classrooms/176847629-atls-4120-fall-2024



Basic views start on the page for the next class