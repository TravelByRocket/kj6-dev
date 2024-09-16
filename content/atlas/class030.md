---
title: "C3W4 Sep 16"
draft: false
weight: 30
---

* [iOS Dev Happy Hour](https://www.iosdevhappyhour.com) this Saturday 
* Videos are up for 2nd half of last week's notes (the parts I planned to cover but did not get to). Consider them part of this week's material. 
* [Join the GH Classroom](https://classroom.github.com/classrooms/176847629-atls-4120-fall-2024)
* [Accept the first project assignment](https://classroom.github.com/a/3eDWASO_)
* Today will focus on project time and ad-hoc code review
* Nice work finding and using NavigationStack, NavigationLink, `@State`, and more 👏

## Layout Views

### Stack Basics

- VStack
- HStack
- Spacer
- Divider

{{< liteyoutube "5FH80M6ljHU" >}}

### Background and Overlay

{{< liteyoutube "zWAY6Xe4ckI" >}}

### ZStack

* Will the the size of its largest view
* First view in the stack is at the bottom and successive views go over
* Nine typical alignments but even more exists https://developer.apple.com/documentation/swiftui/alignment

### ScrollView

* Beware adding padding to ScrollView itself, will cause scroll indicator to be strangely inset
* ScrollView will only be the width of its widest child view unless you expand it
* See in the API that you can hide the scroll indicators
* Try making a large HStack and place it in a ScrollView that scrolls horizontally

### List and Form

* https://developer.apple.com/documentation/swiftui/list
* Try out `listStyle`
* https://developer.apple.com/documentation/swiftui/form

### NavigationStack and NavigationLink

https://developer.apple.com/documentation/swiftui/navigationstack
https://developer.apple.com/documentation/swiftui/navigationlink

can ignore `.navigationDestination` for now

### TabView

https://developer.apple.com/documentation/swiftui/tabview
https://developer.apple.com/documentation/swiftui/tabviewstyle

### Presenting a Sheet

Activate with a Button or Toggle (See below)

https://developer.apple.com/documentation/swiftui/view/sheet(ispresented:ondismiss:content:)

## Interactive Views

### Toggle

https://developer.apple.com/documentation/swiftui/toggle

### Button

We've used this a bit in examples already. Make your own that changes a property of your view. Use the `@State` property wrapper for the thing you are going to change. There are a few built-in button styles to try too. The action can use trailing closure syntax.

https://developer.apple.com/documentation/swiftui/state
https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-state-property-wrapper
