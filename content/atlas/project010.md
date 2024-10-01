---
title: "P1: Tell Your Dev Story"
draft: false
weight: 210
---

* C3W4 Sep 16 (5 Points):
    * 10+ Pages (each of your `struct MyInfoPage: View`),
    * 20+ Views (SwiftUI views, like `Text` or `Image`, not including stack views or scroll views)
    * 20+ Modifiers (like `.padding` or `.underline`, but not arguments like `.leading`)
    * 6+ Layouts Views (3+ `VStack`, 2+ `HStack` and 1+ `ZStack`)
    * Long strings stored in `enum Constants` (never source code lines over 120 characters)
* C4W5 Sep 25 (15 Points): Interactive Views and Navigation
    * SEE CANVAS RUBRIC FOR EXACT DETAILS
    * Must submit through GitHub Classroom assignment
    * Every page in its own file with a preview
    * Every page with a descriptive name
    * Every type named with PascalCase (i.e., all views and pages, anytime you have `struct MyView: View`)
    * Refactor all repetitive code (see video in Class 4 notes) that you can; if you find a part that you tried but couldn't then explain that in comments in your code
    * Every page should be something something new to look at, not just different words and different image; a new layout, color scheme, styling, interaction, etc.
    * I will mark you down substantially if your app looks like someone else's; the best way to ensure this is get creative and curious
    * Use a wide variety of views and modifiers that we have used in class
    * You must use at least a few `@State` variables and change them to update your UI
    * I will not be checking for use of any particular data structures
    * It is very rare that you should use `\n` for spacing, and never `""` to space views out; see padding or stacks instead
* C5W6 Oct 4 (updates the 15 points from check-in #2): Due on GitHub
    * See the rubric on Canvas and feedback on your PR
    * Your work will be re-evaluated with the same rubric and the same Canvas assignment (your score gets updated)

## Checkpoint 1 Feedback Notes for General Discussion

This is not a grading checklist

* Each page needs to be in its own file so each one has its own preview
* Create projects with NO testing and NO storage
* PamelCaseNameApp no punctuation or spaces, same with views
* Every page and view should be descriptively named
* Show how to add files without making references that won't commit. Before submitting, try moving your project folder and see if it still works
* I want to see a commit history
* We need to use gitignore
* Show how to Nuke the project and bring over files
* We need to do some refactoring where we reuse our code
* If your content doesn't fit, use a ScrollView, please
* Future comments will come in a commit on a branch in the project
* Do not use ZIP file. Need to show proper structure.
* Use padding or spacing instead of `\n` or `""`
* Think about usability. When someone get to the end of your app, what about all those stacked views?
* Best ot make each modifier on a new line; and spaces between views
* Visual design wasn't part of the requirements but many phone it in on this
* Organize with App file first and ContentView second
* Let's clean up blatant UI issues
* for check 2 the app should run in simulator
* Make each page end with "Page"
* Let's make some reusable views with name ending "View"
* 750 words requirement
* Do not leave commented code in most cases