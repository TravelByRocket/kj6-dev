---
title: "2: September 9"
draft: true
weight: 20
---


## Text

https://developer.apple.com/documentation/swiftui/text

This is, of course, a very common component, but it can behave a little strangely in some contexts. 

Basically not more complicated than `Text("My Text")`

Except it's not.

What if it only takes one line?
What if two or more lines?

### Straightforward Formatting

Let's cover the things that do totally work the way you expect and want them to.

* `.italic()` or `.italic(myBool)`
* `.bold()` or `.bold(myBool)`
* `.underline()` or `.underline(myBool)`
* `.strikethrough()` or `.strikethrough(myBool)` and other options for pattern and color (why though?)
* `.monospaced()` or `.monospaced(myBool)`
* `.monospacedDigit()` (no Bool argument) for when numbers change but not needing mono overall

This is about as complicated as HTML if you ask me.

#### Multiple Formats

What if you have more than one format that you want to put together? Don't use a stack because it will mangle your work. You can concatenate with `+`, which will return another Text view. There is also `AttributedString` but if you need it, good luck and have fun. 

### Multiline Text Alignment

Here are some more that are less obvious but still straightforward

`.multilineTextAlignment(.center)` or `.leading` or `.trailing` this does not matter when there is only one line (it will center) but when more then that you will suddenly get different behavior. You should frequently account for it being longer because of localization with languages that have longer words. 

Beware that when multiple lines it will still stay as narrow as possible to match where words break so that can mean that you get jumps or wierd borders when you would expect something to be full-width. 

### Line Limit

`.lineLimit(myLineCount)` will do exactly what you'd expect when you pass an `Int` argument. If you pass `nil` then it will take as many lines as it needs. If you do not pass `nil` then a large `Text` view could still truncate. 

There is an init that takes a range but I have not figured out why. Let me know if you figure it out! Maybe you're giving it the option to truncate when in between the range limits? 

It looks like `0` acts like `1`. Can you find otherwise?

There is an optional `reservesSpace` parameter that I am happy to see but haven't had a use for yet.

### Font

HIG https://developer.apple.com/design/human-interface-guidelines/typography#Specifications

.font

font weights

SF font and variants by Apple
Font.Design: default, monospaced, rounded, serif
Custom font can be really fun but can also be the fastest way to trouble
Heard of indie devs eventually giving up and finding other ways to be fun
Tools in SwiftUI might be better now to make it work but I think Apple has it figured out


### Dynamic Type

`.large` is default (this is noted in HIG). Can change this in Preview and can have Preview that shows all options. There is a modifier for setting the dynamic type size and one for limiting the range.

#### Accessibility Sizes

AX_ sizes

Consider ViewThatFits, maybe also with a ScrollView

acting through the environment

### Baselines and String Considerations

string interpolations with Images

firstTextBaseline and lastTextBaseline

format
formatter
timeinterval

issues with animations adding/removing text

## Image

Assets
Async
SF Symbols
SF Symbols app
resizable
scale to fill
scale to fit
frame
rendering modes
asset enums
template
SVG
PDF
aspect ratio
decorative to ignore a11y
use label for a11y
symbol animation
blend modes
corner radius
mask
from uiimage


## Button



---




Basic Views and Modifiers, Interactive Views (part 1)

Finish basic views and modifiers
Interactive views part 1

SF Symbols

Only Very Briefly Covered in Class 1
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