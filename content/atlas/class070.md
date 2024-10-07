---
title: "7: October 14"
draft: true
weight: 70
---
User Defaults, JSON Parsing, SwiftData





Property Wrappers, Environment Variables, Protocols

Navigation and Presentation Views




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