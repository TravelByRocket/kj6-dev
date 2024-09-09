---
title: "2: September 9"
draft: true
weight: 20
---

## Text

Doc: https://developer.apple.com/documentation/swiftui/text

This is, of course, a very common component but it can be tricky in some situations. To get started it doesn't have to be more complicated than `Text("Your Message Here")` and it will do what you expect … until it doesn't behave like you would expect. It will have one behavior for one line, another for two lines, and yet another when it is given less space than it wants. There are many aspects to unpack and we we will start with the most predictable ones.

### Straightforward Formatting

Let's cover the things that work just a you would expect.

* `.italic()` or `.italic(myBool)`
* `.bold()` or `.bold(myBool)`
* `.underline()` or `.underline(myBool)`
	* Can change the color of the underline
* `.strikethrough()` or `.strikethrough(myBool)`
	* Options for color and stroke for the strikethrough too
* `.monospaced()` or `.monospaced(myBool)`
* `.monospacedDigit()` (no Bool argument) for when numbers change but not needing mono overall

These are all the ones I might typically use but there are some others I didn't list here. Can you find them? Could you have expected those?

This is about as simple as HTML if you ask me, which is good. 

Most text modifiers "act through the environment," which we will cover another day, but for now it is sufficient to know that the view you apply it to and every child of that view will adopt the value you set. For example, if you apply a font modifier to a VStack that has (children) text views then all of those Text views will get that font modification too. If you have conflicting values set, the one closest in the hierarchy will supersede anything set at a higher level.

#### Multiple Formats

What if you have more than one format that you want to put together? Don't use a stack because it will mangle your work. You can concatenate with `+`, which will return another `Text` view. There is also `AttributedString` but if you need it when you have more dynamic or complex use cases, but good luck and have fun in that case 🙃.

### Multiline Text Alignment

If you have text that takes up only one line then the `Text` view will only be as big as it needs to be to fit that text. When you go to two or more lines you will need to consider how the extra space within the `Text` view gets distributed, akin to a paragraph alignment. The modifier to set this behavior is `.multilineTextAlignment(myTextAlignment)`, where you can use `.leading`, `.center` or `.trailing`. You should almost always account for text not fitting in the original frame (or line count) that you originally planned because when you go through localization (translation into other languages) it is common to have some words in other languages be much longer than in English.

Beware that when the string is across multiple lines then the `Text` view will always still stay as narrow as possible to match where the longest line in that view breaks. That means that two multiline text views can each have a different width because their longest lines probably didn't both break at the exact same length. If you just have them in a `VStack` then the exact with of each `Text` will probably not make any difference and you won't have to account for it, but if you have other visual aspects to the Text like a border or background then these differences in widths will be readily apparent and you will need to account for it with the `.frame` modifier.

### Line Limit

`.lineLimit(myLineCount)` will do exactly what you'd expect when you pass an `Int` argument. If you pass `nil` then it will take as many lines as it needs. There could be cases where long `Text` views will truncate even if they seem to have enough room and you can prevent that by passing `nil`.

Note that passing `0` would be a nonsense value but it will act like `1`. Let me know if you are able to find some other behavior with this. 

There is an optional `reservesSpace` parameter that I am happy to see but haven't had a use for yet.

There is a version of `lineLimit` that takes a range of values, such as `3 ... 5`, `3...`, or `...5`. This is an even more flexible way (when needed) of reserving space and/or limiting the lines. I've never used this or can think of a time when I would have, but here it is!

### Font

Doc: https://developer.apple.com/documentation/swiftui/font

HIG: https://developer.apple.com/design/human-interface-guidelines/typography#Specifications

* `.font` body, caption, and title, for example
	* see `Font` documentation, above
* `.fontWeight` from ultralight to black
	* https://developer.apple.com/documentation/swiftui/font/weight
* `.fontDesign` default, rounded, serif, monospaced
	* https://developer.apple.com/documentation/swiftui/font/design
* `.fontWidth` condensed or expanded, for example
	* https://developer.apple.com/documentation/swiftui/font/width

All of this is done by Apple and it is remarkably responsive in ways that we could not reasonably perceive and might not be able to replicate with custom fonts. Using custom fonts can definitely be a fun way to enhance the look of your app but they can be a pitfall too. I would recommend not using a custom font in almost any situation. I think if you want to use a custom font in limited situations, like titles, then that seems like a safe and rather uncomplicated direction you could go. Even though I can't find the source, I believe that  [Marco Arment](https://marco.org) used to have a custom font for [Overcast](https://overcast.fm) but eventually let it go in favor of how robust Apple's fonts are. Tools in SwiftUI might be better now to make it work but I know Apple has it figured out and I don't know if I could, so I'll leave it to them.

### Dynamic Type

Doc: https://developer.apple.com/documentation/SwiftUI/DynamicTypeSize

Field Guide: https://www.swiftuifieldguide.com/layout/dynamic-type/

Sizes run from `.xSmall` through `.xxxLarge` and the default is `.large` (this is noted in HIG). Can change this in Preview and can have Preview that shows all options. There is a modifier for setting the dynamic type size and one for limiting the range. I can only discourage you from limiting the maximum size of the dynamic type, otherwise it can't be utilized for what it was intended. 

In addition to all of the typical dynamic type sizes, there five additional sizes that are considered accessibility sizes `accessibility1` through `accessibility5`.

Show how to change this in Settings or with Control Center. 

In order to accommodate a wide range of sizes, consider using `ScrollView` and/or `ViewThatFits`. 

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
SF Symbols (make own section?)
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
aspect ratio (definitely on Image, check if on View, show students how)
decorative to ignore a11y
use label for a11y
symbol animation
blend modes
corner radius
mask
from uiimage


## Label

system label styles
style behavior across platforms
switches for RTL languages
custom label style

it gets used in Button a lot



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

## Padding

## Colors

opacity (works everywhere but usually mods Color)
primary, secondary

## Background and Overlay



## Foreground Style



## Shapes

standard ones: rectangle, circle, rounder rectangle...

how to make custom ones (maybe a later class?)

## Frame

CGFloat.infinity



## Border

strokeBorder
stroke style


## Stacks

They can all be used within each other but try to keep it to a minimum or be intentional about splitting things up.

### VStack and HStack

alignment
spacing

### Spacer

I prefer not to use when there is just one other view in a stack because then a spacer has a min length and then a padding got added by the stack and you have to take more steps to avoid that then you do to just use the frame modifier




### ZStack

has 8 alignment options
does each view get its own bounds or do they all just get the greater of the width and the greater of the height
front to back or back to font?
almost always better to use an overlay or a background because it's at least more direct semantically (i.e. a time where you want the frames the same size) or it is a smell of trying to do something in a hacky way where there is either a better alternative or a good reason to not do it at all. 


## ScrollView

use horizontal axis with HStack
new scroll/bounce behaviors
show/hide indicators
beware padding outside of ScrollView

Some say there should always be a ScrollView or an options for ScrollView for a11y

much more complex stuff perhaps in a later class or look it up yourself

---


Basic Views and Modifiers, Interactive Views (part 1)

Finish basic views and modifiers
Interactive views part 1



- Get an explanation of how the layout system works at a high level
- Stack views and similar
	- ScrollView
	- List/Form
	- ForEach
- NavigationStack, TabView, sheet

- Data
	- State, Binding, SwiftData, 
	- TextField, Toggle, Picker


# Basic Views

- Light/Dark Mode

- AccentColor

- Tint

# Styling Modifiers

- cornerRadius


## Shadow

It exists, don't use it IMO, can make overlaps strange, why use skeuomorphism? 

# Interactive Views

- Toggle

- Slider

- Stepper

- TextField

- SecureField

Some modifiers only work on text, some modifiers return Text while some review `some View`