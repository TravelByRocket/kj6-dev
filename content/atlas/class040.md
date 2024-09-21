---
title: "4: September 23"
draft: false
weight: 40
---

### ZStack

* Will the the size of its largest view
* First view in the stack is at the bottom and successive views go over
* Nine typical alignments but even more exist https://developer.apple.com/documentation/swiftui/alignment

### ScrollView

* Beware adding padding to ScrollView itself, will cause scroll indicator to be strangely inset
* ScrollView will only be the width of its widest child view unless you expand it
* See in the API that you can hide the scroll indicators
* Try making a large HStack and place it in a ScrollView that scrolls horizontally

{{< liteyoutube "nblHm0sBvoo" >}}

### List and Form

* https://developer.apple.com/documentation/swiftui/list
* Try out `listStyle`
* https://developer.apple.com/documentation/swiftui/form

### NavigationStack and NavigationLink

https://developer.apple.com/documentation/swiftui/navigationstack
https://developer.apple.com/documentation/swiftui/navigationlink

can ignore `.navigationDestination` for now

{{< liteyoutube "B54LLIOgoTA" >}}

### TabView

https://developer.apple.com/documentation/swiftui/tabview
https://developer.apple.com/documentation/swiftui/tabviewstyle

### Presenting a Sheet

Activate with a Button or Toggle (See below)

https://developer.apple.com/documentation/swiftui/view/sheet(ispresented:ondismiss:content:)

## Interactive Views


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



## Using Gitignore



## Presenting a Sheet



## ZStack



## ScrollView



## List and Form


---

UNDER CONSTRUCTION BELOW

---




Container Views, Shapes and Styling

# Container Views

  

- List

- Section

- ScrollView

- ForEach

- Grid

# Shapes and Styling

## Shapes

standard ones: rectangle, circle, rounder rectangle...
mask
how to make custom ones (maybe a later class?)

  

- Shapes (Rectangle, Circle, etc.)

- Gradient

More Text:
format
formatter
timeinterval

issues with animations adding/removing text

SF Symbols in depth



# Basic Views

- Light/Dark Mode

- AccentColor

- Tint

# Styling Modifiers

- cornerRadius


## Shadow

It exists, don't use it IMO, can make overlaps strange, why use skeuomorphism? 

### GeometryReader


- Slider

- Stepper

- TextField

- SecureField

Some modifiers only work on text, some modifiers return Text while some review `some View`

corner radius


## Frame

CGFloat.infinity


much more complex stuff perhaps in a later class or look it up yourself

---



# TBD

constants enum

- ForEach



- Data
	- State, Binding, SwiftData, 
	- TextField, Toggle, Picker


custom button styles (but why?)
	pressed state


buttons details left out 


passing functions as arguments
passing view producing closures
views blocking hits
disable hit testing
buttons in buttons
vs onTapGesture vs onLongTapGesture
Common to have strange non-system behavior with custom gestures
min tap target
considering contentshape with custom shape that has minimum sizes

@Binding