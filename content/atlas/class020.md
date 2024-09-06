---
title: "2: September 9"
draft: true
weight: 20
---


## Text

https://developer.apple.com/documentation/swiftui/text

Basically not more complicated than `Text("My Text")`

Except it's not.

What if it only takes one line?
What if two or more lines?

Let's cover the things that do totally work the way you expect and want them to.

* `.italic()` or `.italic(myBool)`
* `.bold()` or `.bold(myBool)`
* `.underline()` or `.underline(myBool)`
* `.strikethrough()` or `.strikethrough(myBool)` and other options for pattern and color (why though?)
* `.monospaced()` or `.monospaced(myBool)`
* `.monospacedDigit()` (no Bool argument)

This is about as complicated as HTML if you ask me.

Here are some more that are less obvious but still straightforward

`.multilineTextAlignment(.center)` or `.leading` or `.trailing` this does not matter when there is only one line (it will center) but when more then that you will suddenly get different behavior. You should frequently account for it being longer because of localization with languages that have longer words. 

Beware that when multiple lines it will still stay as narrow as possible to match where words break so that can mean that you get jumps or wierd borders when you would expect something to be full-width. 

What if you have more than one format that you want to put together? Don't use a stack because it will mangle your work. You can concatenate with `+`, which will return another Text view. There is also `AttributedString` but if you need it, good luck and have fun. 


line limit
0 acts like 1
I don't know what the range does
nil sets no limit (it might stop otherwise)
reservesSpace: Bool

.font

acting through the environment



baseline
string interpolation
font weights
HIG https://developer.apple.com/design/human-interface-guidelines/typography#Specifications
dyanmic type
accessibility sizes
large is default (this is noted in HIG)
how to set or limit dynamic type size
SF font and variants by Apple
Font.Design: default, monospaced, rounded, serif
Custom font can be really fun but can also be the fastest way to trouble
Heard of indie devs eventually giving up and finding other ways to be fun
Tools in SwiftUI might be better now to make it work but I think Apple has it figured out

format
formatter
timeinterval


Basic Views and Modifiers, Interactive Views (part 1)

Finish basic views and modifiers
Interactive views part 1

SF Symbols

Only Very Briefly Covered in Class 1
	* Text
	* Image
	* Button
	* padding
	* background
	* overlay
	* foreground style
	* shapes

# Basic Modifiers

- padding
- background
- font
- foregroundStyle
- opacity

- Get an explanation of how the layout system works at a high level
- Stack views and similar
	- V/H/ZStack, alignment, frame
	- Scrollview
	- List/Form
	- ForEach
- NavigationStack, TabView, sheet

- Data
	- State, Binding, SwiftData, 
	- TextField, Toggle, Picker

# Basic Views

  

- Text

- Image

- Button

- Label

- Color

- Light/Dark Mode

- AccentColor

- Tint


# Styling Modifiers

  

- overlay

- frame

- border

- cornerRadius

- shadow

- Color
# Interactive Views

  

- Toggle

- Slider

- Stepper

- TextField

- SecureField