---
title: Syllabus
draft: true
weight: 5
---

## Contact

### Slack

* Course Slack Channel: `atls-4120-fall-2024`
* My Slack Profile: `@Bryan Costanza`

I prefer Slack for communication with the class. Use the course channel for general topics, anything that might be relevant to the class, or might be answered by your peers.

You can send me a direct message for anything that is not applicable for others in the class or that should otherwise be private, like grades or other concerns.

### Email

See my profile on Slack for my email address. 

Non-general questions and communuciation that is not relevant to others in the class can be sent to me through a direct message on Slack or by email. 

### Canvas

Official announcement will come through Canvas, so make sure you have notifications turned on. 

## Office Hours

* Wednesdays 1:30-2:00
* Fridays 1:30-2:00
* Zoom link in Slack channel description

I'm open to finding other days or times if these conflict with your schedule.

This is also an open time for you to bring disucssion ideas, career questions, or get general feedback. You are never obligated to attend, but I would think that if you don't attend at least a couple of times in the semester then you will have passed up an opportunity for advancing your knowledge, perspective, and career. 

## System Requirements

### macOS

You MUST have access to a computer running macOS Ventura 13.5 (July 2023) or later. The OS names after Ventura are Sonoma (September 2023) and Sequioa (currently Beta, full release expected in September 2024).

I have heard mixed responses about whether there may be loaner laptops through ATLAS, so that will be up to you to find out. It might also work to use a mac in the computer lab.

### Xcode

Additionally, you MUST be able to install Xcode 15 or 16 on the computer that you will use. Xcode 15.4 was released in May 2025 and it is the latest release as of 11 August 2024. Xcode 16 is currently on its 5th beta release, with its expected final release in September 2024. 

There are a few different ways to get Xcode, and we will cover that in class, but if you have a macOS version listed above and you have permision to install apps on your device, then you should have everything you need. I would generally recommend that you use the latest stable release (15.4 right now) but I am always running the latest beta on my machine so you may choose yourself between 15.4 or 16.0. 

## Original Work

Expectations:

* The work is overall your own.
* Up to 10% of your code can be from elsewhere, if you cite it. 
    * A comment in your code with a link to the source and a note about how much code you used is required.
* You must be able to explain ALL of your code.
    * If you are using code you don't understand then you need to flag it for discussion by making a clear comment in your code and/or writing to me.

## Use of AI

This is an evolving topic, of course. I have a license for GitHub Copilot at work and I have a personal subscription for home as well. I think it is a powerful tool, especially when I am working on the early phases of a project in an area that I am not very familiar with.

Expectations:
* You may use AI, and you may use it extensively
* You must be able to fully explain the code it generates
* You must be able to develop app code from scratch without assistance

Suggestions:
* Do not rely on it being available
* Focus on figuring out code, not figuring out the AI
* Use it to learn, ask questions, develop faster, generate ideas

Consider:
* AI only knows SwiftUI at an OK level, it's going to be wrong at times
* Swift Intelligence (similar to Copilot) will soon be generally available to all Apple developers and it wil be trained on proprietary information from Appl's framework code.
* Future success as a developer probably means working well with AI
    * Cal Newport's book *Deep Work*: "In this new economy, three groups will have a particular advantage: (1) those who can **work well and creatively with intelligent machines**, (2) those who are the best at what they do, and (3) those with access to capital. (p. 28)

## Cheating

If you follow the guidance above while proactively communicating your sources, process, and uncertainties, you will not find yourself unexpectedly facing penalties or other administrative action. 

If you conceal dishonest intentions behind your work then I will reduce or zero out scores for relevant assignments and report my findings to the ATLAS Institute.

You would be much better off doing something simple that to cheat.

Do not not use outside coding tutorials as your assignment submissions.
 
## Grading

This is the tentative list of assignments and points for each. Weighting is determined only by the points available for each assignment. There is no category weighting. 

You can expect about one assignment per week. For now there are 12 scored assignments over our 14 weeks of class.

### Assignments

Homework and projects will be submitted through GitHub Classroom. 

Quizzes could be on specific knowledge knowledge or writing pseudocode to show your understanding without using a computer. 

You should expect to spend twice as much time working outside of class as you spend in class. 

| Assignment              | Points | Description                           | Due Date        |
| ----------------------- | ------ | ------------------------------------- | --------------- |
| Quizzes (2)             | 20     | Two quizzes, 10 points each           | Various, TBD             |
| Homeworks (6)           | 60     | Six homework assignments, 10 points each | Various, TBD |
| Project 1               | 20     | Your Dev Story App                    | Week 3          |
| Project 2               | 30     | Calculation App                       | Week 6          |
| Project 3               | 40     | API-Based App                         | Week 10         |
| Project 4               | 50     | Framework-Based App                   | Week 14         |
| **Under Consideration** |        |                                       |                 |
| Project A               | ??     | UI Exploration (Behance)              | Week ??         |
| Project B               | ??     | Git and Xcode Intro                   | Week ??         |

### Late Policy

I can be fairly flexible on due dates in advance but I will be very inflexible with due dates on short notice. Let me know as soon as possible if you think you should have a due date adjusted. 

* Up to 24 hours late: reduction of 20% of the possible points
* Up to 48 hours late: reduction of 40% of the possible points
* After 48 hours: assignment will not be accepted

```
Example: Rubric score of 85/100 point turned in 1 hour late. 

Starting score: 85
Possible score: 100
Penalty: 20% of Possible score (20 points)

StartingScore - PenaltyPoints = FinalScore
85 - 20 = 65

Final score 65/100
```


## Schedule/Outline

We have 14 class sessions this semester. My goal for the first half of the semester is to get through all of the most important views, modifiers, and basic data management concepts. In the second half of the semester we will cover more advanced topics and frameworks to round out your app development knowledge. The second half of the class will also have you exploring some material on your own, based on your interests and personal app goals. 

| Class Week              | Topics                                                         |
| ----------------------- | -------------------------------------------------------------- |
| **Section 1**           | **Getting Started**                                            |
| [Class 1](class010.md)  | Environment Setup, Git Basics, Basic Views (part 1)            |
| **Section 2**           | **SwiftUI Views and Modifiers**                                |
| [Class 2](class020.md)  | Basic Views and Modifiers (part 2), Interactive Views (part 1) |
| [Class 3](class030.md)  | Interactive Views (part 2), Layout Views                       |
| [Class 4](class040.md)  | Container Views, Shapes and Styling                            |
| [Class 5](class050.md)  | Navigation and Presentation Views                              |
| **Section 3**           | **Data Flow and Management**                                   |
| [Class 6](class060.md)  | Property Wrappers, Environment Variables, Protocols            |
| [Class 7](class070.md)  | User Defaults, JSON Parsing, SwiftData                         |
| **Section 4**           | **Advanced SwiftUI**                                           |
| [Class 8](class080.md)  | Animations, Transitions, Gestures, Searchable                  |
| [Class 9](class090.md)  | Accessibility, Internationalization                            |
| **Section 5**           | **Frameworks, Networking, Deployment**                         |
| [Class 10](class100.md) | Testing, Widgets,                                              |
| [Class 11](class110.md) | App Intents                                                    |
| [Class 12](class120.md) | Networking, Syncing, Login                                     |
| [Class 13](class130.md) | Cross-Platform Development, Deployment                         |
| [Class 14](class140.md) | Final Presentations, Course Review, Next Steps                 |


---

**Pitching Your Poject**

Try this prompt:
> For [target audience], [app name]  [solves a specific problem or meets a specific need] by [key feature or unique selling point].

---

**Work In Progress**
Add to schedule
* App review guidelines
* App submission process
* Human Interface Guidelines