---
title: "5: September 30"
draft: true
weight: 50
---
Navigation and Presentation Views

Content/Clarifications to make:
* Use SwiftFormat
* No Xcode tokens
* When to put stuff below body var and when to break out to new thing
* naming conventions
* private State
* space between views
* short body properties
* Tab is iOS 18
* use only one navigation stack
* reminder about AI use and notes
* navigation must work
* preview provider is old
* the lame comments are a dead giveaway and employers will know that too
* use README to keep track of things instead of comments
* Modifiers on new lines
* Overlay as example of using trailing closure syntax, and TCS is always preferred
* granularity as example of how to not chatgpt
* next project will grade for formatting
* maybe have design reviews next week on the calculation app, maybe extra credit for presenting in one week, everyone else the next week
* screen safe areas
* We need to talk about how I can spend less time grading and more time teaching/helping


# Navigation and Presentation


- Full Screen Cover

- Menu

- Alert

## Interactive Views

Container Views, Shapes and Styling

- ForEach
- Grid
- Slider
- Stepper
- TextField

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