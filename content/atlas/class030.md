---
title: "C3W4 Sep 16"
draft: true
weight: 30
---
Interactive Views (part 2), Layout Views

interactive views part 2
layout views

# Layout Views

  

- VStack

- HStack

- ZStack

- Spacer

- Divider

- GeometryReader

- Group



# Basic Views

- Light/Dark Mode

- AccentColor

- Tint

# Styling Modifiers

- cornerRadius


## Shadow

It exists, don't use it IMO, can make overlaps strange, why use skeuomorphism? 

- Get an explanation of how the layout system works at a high level
- Stack views and similar
	- ScrollView
	- List/Form
	- ForEach
- NavigationStack, TabView, sheet

- Data
	- State, Binding, SwiftData, 
	- TextField, Toggle, Picker


## Frame

CGFloat.infinity


much more complex stuff perhaps in a later class or look it up yourself

---



# TBD

constants enum

# Interactive Views


## Button

button styles
custom button styles (but why?)
	pressed state

@State variables (more on this later)
@Binding
trailing closure syntax
passing functions as arguments
passing view producing closures
views blocking hits
disable hit testing
buttons in buttons
vs onTapGesture vs onLongTapGesture
Common to have strange non-system behavior with custom gestures
min tap target
considering contentshape with custom shape that has minimum sizes


- Toggle

- Slider

- Stepper

- TextField

- SecureField

Some modifiers only work on text, some modifiers return Text while some review `some View`

corner radius