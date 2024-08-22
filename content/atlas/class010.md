---
title: "1: August 26"
draft: false
weight: 10
---

## Outline

* Personal Introductions and Syllabus
* Intro Apple, Xcode, Swift, SwiftUI
* Environment Setup
* `git` and Github
* Announce Assignments

## Personal Introductions & Syllabus

### Instructor

I began my journey in Aerospace Engineering, which gave me a foundation of problem-solving and technical skills. I’ve ventured into several different industries since then, each adding to my experience and perspective. Although I’m a self-taught developer, my design and engineering background has been greatly shaped my approach to software development.

I continue to work on developing my own apps—a process that, while sometimes slow, is fascinating and rewarding. Every step of the way, I’m constantly learning and applying new ideas, which I’m excited to share with you in this course.

#### Background 

* B.S. in Aerospace Engineering at Cal Poly, San Luis Obispo
	* Minor in Psychology
	* Focus on Propulsion Systems
* M.S. in Creative Technologies & Design at CU Boulder
	* Interactive Art Installations 
		* see esp. Permutate and The Intervening Substance by Nicole Banowetz
	* Generative Art
	* Unity 3D (turns out to be like aerospace)
	* iOS App for Haunted House
* Self-taught Software Developer

#### Experience

* Aerospace Systems Engineer at Aerojet
* Middle & High School Science Teacher in Italy
* Informal Science Educator
* UAV Sales Engineer
* Pharmaceutical Data Analyst
* Education & Outreach at LASP
* H/W & S/W Engineer, Science Instruments and Museum Exhibits
* **iOS Developer** at Woodridge
* **iOS Developer** at Workday

#### Current Role

* UI Components based on Workday's Canvas Design System
* Extensive Accessibility and Internationalization
* Work most closely with UX Designers via Figma
* Utilize Continuous Integrations/Development
* Set the standard for using modern SwiftUI
* Support QA teams for ensuring stable releases

### Learn About Students

* Coding experience (share more in upcoming project)
* App dev goals and interests
* Thoughts on App Store submission and TestFlight ($)

### Syllabus

See the Syllabus page.

## Introduction Apple, Xcode, Swift, SwiftUI

Apple is the creator of Xcode, the essential tool for developing apps across all Apple platforms. Swift, an open-source programming language initially developed by Apple, has become the standard for building modern apps. SwiftUI, a closed-source UI framework also developed by Apple, is the future of app development, gradually replacing the older UIKit framework. Be thankful that you’re entering this space now that it is a much more approachable space to be in than just a few years ago!

Swift and SwiftUI have evolved rapidly, but we’re reaching a point where things are starting to stabilize—especially with Swift. The language continues to introduce new features, but the pace of change is slowing down. We’re currently in a transition from Swift 5 to Swift 6, with strict concurrency being the most significant update. This change is likely to be the last major shift for a while, but it will also break a lot of existing code. As a result, some projects may remain in Swift 5 mode until the heat death of the universe.

While some developers argue that SwiftUI isn’t fully ready for widespread adoption, I strongly disagree—with almost no exceptions. Yes, there are still a few things that UIKit can do that SwiftUI can’t, but that gap is closing fast. Eventually (perhaps a decade from now), UIKit may no longer be the preferred tool for anything. The complaints about SwiftUI often come from developers who learned the “old way” and haven’t fully embraced the SwiftUI mindset. Other frustrations arise from trying to force SwiftUI to do things it wasn’t designed for, rather than following the natural, native patterns.

Personally, I know very little about UIKit, and Objective-C still looks completely foreign to me. From my perspective, anyone complaining about SwiftUI is either not fully understanding it, trying to do things the hard way, or both.

In short: Embrace SwiftUI. It’s the future, and with the right approach, it’s an incredibly powerful tool for building modern apps.

### Xcode

* New Project
	* The famous `Shift-Cmd-N`
		* A new file is merely `Cmd-N` 😅
	* Or from the menu
	* Select iOS App
	* Bundle Identifier as reverse URL
* Main files and structure
	* App
	* ContentView
	* Project File
* Navigator
	* Does not necessarily match file structure, but usually does
* Preview
	* Can be turned on and off
	* Error messages almost helpful (beware!)
	* Preview macro
* Simulator
	* Differences from physical device
	* No VoiceOver but can get close
	* Not 100% necessary for iOS dev
	* Select the OS (also affects Preview)
* Console Output
	* `print` of course
	* Common to get lots of useless messages
		* Worry more about IDE warnings and errors
* Settings
	* Accounts
	* Locations
	* Derived Data
* Help Menu
	* Documentation
	* Human Interface Guidelines
* Component Library
	* Configure views from side menu
* Show some main views
	* Text
	* Image
	* Button
	* padding
	* background
	* overlay
	* foreground style
	* shapes

## Environment Setup

Accomplish these for the rest of the class. Feel free to help each other and ask questions. 

### Install These in Any Order

Sub-tasks go after their parent task

* Install [Xcodes](https://www.xcodes.app) App
	* Install Xcode 15.4 (15F31d)
	* or latest Beta via Xcodes
* Install [Github Desktop](https://desktop.github.com/download/)
* Install [SF Symbols](https://developer.apple.com/sf-symbols/)
* Install [Homebrew](https://brew.sh)
	* Install `git` with `brew install git`

### Create Accounts in Any Order
* Create [Apple Developer](https://developer.apple.com) Account (free version)
* Create [GitHub](https://github.com) account 
	* Join Github Classroom for [ATLS-4120 Fall 2024](https://classroom.github.com/classrooms/176847629-atls-4120-fall-2024)
		* Might need to join [ATLS421 ](https://github.com/ATLS4120) Organization first 
		* Might need invite to organization (Slack me your username)

### After Creating GitHub Account

* Follow the directions in "Try It Out!" in [Codecademy Git Setup](https://www.codecademy.com/article/git-setup) to make your first `commit` and `push`!

## Assignments

### Canvas Submission Tuesday, Sept 3 at 5pm

Submit a screenshot of your new test repo (from "Try It Out!" above) to Canvas for the assignment Git First Push

### Quiz Monday, Sept 9 at start of class

Quiz on Swift basics based on the content from days 1-12 of the [100 Days of Swift](https://www.hackingwithswift.com/100) by Paul Hudson at Hacking with Swift. These are the topics (the day number is not important):
  * Day 1 – variables, simple data types, and string interpolation
  * Day 2 – arrays, dictionaries, sets, and enums
  * Day 3 – operators and conditions
  * Day 4 – loops, loops, and more loops
  * Day 5 – functions, parameters, and errors
  * Day 6 – closures part one
  * Day 7 – closures part two
  * Day 8 – structs, properties, and methods
  * Day 9 – access control, static properties, and laziness
  * Day 10 – classes and inheritance
  * Day 11 – protocols, extensions, and protocol extensions
  * Day 12 – optionals, unwrapping, and typecasting

## Swift

[Swift.org](https://www.swift.org)
[The Basics](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics/)
The even have a nice little tutorial for [Build an iOS app with SwiftUI](https://www.swift.org/getting-started/swiftui/)
- Community
- [Kodeco Style Guide](https://github.com/kodecocodes/swift-style-guide)

## Swift and SwiftUI
- SwiftUI
	- [WWDC20 Introduction to SwiftUI](https://developer.apple.com/videos/play/wwdc2020/10119)
	- [WWDC24 SwiftUI Essentials](https://developer.apple.com/videos/play/wwdc2024/10150/)
	- Closed source from Apple
	- Framework
	- Show Example


[WWDC19 Introducing SF Symbols](https://developer.apple.com/videos/play/wwdc2019/206/)
[WWDC21 SF Symbols in SwiftUI](https://developer.apple.com/videos/play/wwdc2021/10349/)
## Xcode

- [WWCD24 XCode Essentials](https://developer.apple.com/videos/play/wwdc2024/10181/)
- [Xcode Developer Documentation](https://developer.apple.com/documentation/xcode)


- Settings
	- Login
	- Text Editing
		- Trim trailing whitespace
		- Including white-space only lines
		- Re-indent on paste
	- Ctrl-I to indent


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


Basic views start on the page for the next class