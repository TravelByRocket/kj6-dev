---
title: "4: September 23"
draft: false
weight: 40
---

### ZStack

* Will the the size of its largest view
* First view in the stack is at the bottom and successive views go over
* Nine typical alignments but even more exist https://developer.apple.com/documentation/swiftui/alignment

{{< liteyoutube "3nQPe-eSi_k" >}}

### ScrollView

* Beware adding padding to ScrollView itself, will cause scroll indicator to be strangely inset
* ScrollView will only be the width of its widest child view unless you expand it
* See in the API that you can hide the scroll indicators
* Try making a large HStack and place it in a ScrollView that scrolls horizontally
* Use Safe Area Insets if you need to place content around a scroll view but still want content to scroll behind

{{< liteyoutube "nblHm0sBvoo" >}}

### List and Form

* https://developer.apple.com/documentation/swiftui/list
* https://developer.apple.com/documentation/swiftui/form
* Try out `listStyle`

{{< liteyoutube "7IF8FXg4WP0" >}}

### NavigationStack and NavigationLink

https://developer.apple.com/documentation/swiftui/navigationstack
https://developer.apple.com/documentation/swiftui/navigationlink

can ignore `.navigationDestination` for now

{{< liteyoutube "B54LLIOgoTA" >}}

### TabView

> Warning: `Tab` is for iOS 18 so you should pay more attention to the tab modifiers you see in the comments at the beginning of the video. I'll update the demo app when I can.

https://developer.apple.com/documentation/swiftui/tabview
https://developer.apple.com/documentation/swiftui/tabviewstyle

{{< liteyoutube "eC7ZhvsXvZ8" >}}

### Presenting a Sheet

Activate with a Button or Toggle (See below)

https://developer.apple.com/documentation/swiftui/view/sheet(ispresented:ondismiss:content:)

{{< liteyoutube "7pE6qGgTM1U" >}}

## Button, Toggle, State, Binding

{{< liteyoutube "CUKYs9d-SRc" >}}

### Toggle

https://developer.apple.com/documentation/swiftui/toggle

### Button

We've used this a bit in examples already. Make your own that changes a property of your view. Use the `@State` property wrapper for the thing you are going to change. There are a few built-in button styles to try too. The action can use trailing closure syntax.

https://developer.apple.com/documentation/swiftui/state
https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-state-property-wrapper

## Refactoring Repetitive Code

{{< liteyoutube "aeadBRIEMGA" >}}

## Creating New Project from Assignment Repo

{{< liteyoutube "hLY8UdPaiJI" >}}

NB: You will see a student's name in my text editor because I was taking grading notes there earlier in the week.

## Using Gitignore

Instructions are in the video above and here is a link for the gitignore I suggest that you use

Use this one https://www.toptal.com/developers/gitignore/api/xcode,macos,visualstudiocode
 
---

Polish Notes

* `Tab` is for iOS 18, need to show `.tab` modifier
* iOS 17 runtime not on all devices
* Computers clear all their data every time and makes it hard ot get started again, especially for token creation
* Simulator wouldn't show up even after downloading three times
* NavStack use only one 
* Video to make extensions for colors, fonts, etc.
* Video for making a common view with default parameters, talk about member-wise inits