---
title: "C2W3 Sep 9"
draft: false
weight: 20
---

## Announcements

* Paper quiz on Swift syntax at end of class
* "Tell Your Dev Story" due date moved back by one week to C4W5 Sep 30. See [Project 1](project010).

## Text

* Doc: https://developer.apple.com/documentation/swiftui/text

This is, of course, a very common component but it can be tricky in some situations. To get started it doesn't have to be more complicated than `Text("Your Message Here")` and it will do what you expect … until it doesn't behave like you would expect. It will have one behavior for one line, another for two lines, and yet another when it runs out of space. There are many aspects to unpack and we we will start with the most predictable ones.

### Straightforward Formatting

Let's cover the things that work just a you would expect.

> Example: `TextModifiersPage.swift`

* `.italic()` or `.italic(myBool)`
* `.bold()` or `.bold(myBool)`
* `.underline()` or `.underline(myBool)`
	* Can change the color of the underline
* `.strikethrough()` or `.strikethrough(myBool)`
	* Options for color and stroke for the strikethrough too
* `.monospaced()` or `.monospaced(myBool)`
* `.monospacedDigit()` (no Bool argument) for when numbers change but not needing mono overall

> Example: `MonospacedFontPage.swift`

These are all the ones I would typically use or expect to use but there are some others I didn't cover. Where would you go to look for them? What did you find? Could you have expected those?

This is all about as simple as HTML if you ask me, which is good. 

Most text modifiers "act through the environment," which we will cover another day, but for now it is sufficient to know that the view you apply it to and every child of that view will adopt the value you set. For example, if you apply a font modifier to a `VStack` that has (children) `Text` views then all of those `Text` views will get that font modification too. If you have conflicting values set, the one closest in the hierarchy will supersede anything set at a higher level.

#### Multiple Formats

What if you have more than one format that you want to put together? Don't use a stack because it will mangle your work. You can concatenate with `+`, which will return another `Text` view. 

There is also `AttributedString` but if you need it when you have more dynamic or complex use cases, but good luck and have fun in that case 🙃.

### Multiline Text Alignment

> Example: `TextPage.swift`

If you have text that takes up only one line then the `Text` view will only be as big as it needs to be to fit that text. When you go to two or more lines you will need to consider how the extra space within the `Text` view gets distributed, akin to a paragraph alignment. The modifier to set this behavior is `.multilineTextAlignment(myTextAlignment)`, where you can use `.leading`, `.center` or `.trailing`. You should almost always account for text not fitting in the original frame (or line count) that you originally planned because when you go through localization (translation into other languages) it is common to have some words in other languages be much longer than in English.

Beware that when the string is across multiple lines then the `Text` view will still stay as narrow as possible to match where the longest line in that view breaks. That means that two multiline text views can each have a different width because their longest lines probably didn't both break at the exact same length. If you just have them in a `VStack` then the exact width of each `Text` will probably not make any difference and you won't have to account for it, but if you have other visual aspects to the Text like a border or background then these differences in widths will be readily apparent and you will need to account for it with the `.frame` modifier.

### Line Limit

> Example: `LineLimit.swift`

`.lineLimit(myLineCount)` will do exactly what you'd expect when you pass an `Int` argument. If you pass `nil` then it will take as many lines as it needs. There could be cases where long `Text` views will truncate even if they seem to have enough room and you can prevent that by passing `nil`.

Note that passing `0` would be a nonsense value but it will act like `1`. Let me know if you are able to find some other behavior with this.

There is an optional `reservesSpace` parameter that I am happy to see but haven't had a use for yet.

There is a version of `lineLimit` that takes a range of values, such as `3 ... 5`, `3...`, or `...5`. This is an even more flexible way (when needed) of reserving space and/or limiting the lines. I've never used this or can think of a time when I would have, but here it is!

{{< liteyoutube "ZZMAksiJQHo" >}}

### Font

> Doc: https://developer.apple.com/documentation/swiftui/font
>
> HIG: https://developer.apple.com/design/human-interface-guidelines/typography#Specifications
>
> Example: `FontPage.swift`

* `.font` body, caption, and title, for example
	* see `Font` documentation, above
* `.fontWeight` from ultralight to black
	* https://developer.apple.com/documentation/swiftui/font/weight
* `.fontDesign` default, rounded, serif, monospaced
	* https://developer.apple.com/documentation/swiftui/font/design
* `.fontWidth` condensed or expanded, for example
	* https://developer.apple.com/documentation/swiftui/font/width

All of this is done by Apple and it is remarkably responsive in ways that we could not reasonably perceive and might not be able to replicate with custom fonts. Using custom fonts can definitely be a fun way to enhance the look of your app but they can be a pitfall too. I would recommend not using a custom font in almost any situation. I think if you want to use a custom font in limited situations, like titles, then that seems like a safe and rather uncomplicated direction you could go. Even though I can't find the source, I believe that  [Marco Arment](https://marco.org) used to have a custom font for [Overcast](https://overcast.fm) but eventually let it go in favor of how robust Apple's fonts are. Tools in SwiftUI might be better now to make it work but I know Apple has it figured out and I don't know if I could, so I'll leave it to them.

{{< liteyoutube "UkS2C1FP73M" >}}

### Dynamic Type

> Doc: https://developer.apple.com/documentation/SwiftUI/DynamicTypeSize
>
> Field Guide: https://www.swiftuifieldguide.com/layout/dynamic-type/
>
> Example: `DynamicType.swift`

Sizes run from `.xSmall` through `.xxxLarge` and the default is `.large` (this is noted in HIG). Can change this in Preview and can have Preview that shows all options. There is a modifier for setting the dynamic type size and one for limiting the range. I can only discourage you from limiting the maximum size of the dynamic type, otherwise it can't be utilized for what it was intended. 

`.dynamicTypeSize(.xLarge)`

`.dynamicTypeSize(.medium...)`

`.dynamicTypeSize(...DynamicTypeSize.accessibility3)`

`.dynamicTypeSize(.xLarge ... .xxxLarge)`

In addition to all of the typical dynamic type sizes, there five additional sizes that are considered accessibility sizes, `accessibility1` through `accessibility5`.

Show how to change this in Settings (device and Simulator) or with Control Center (device only).

In order to accommodate a wide range of sizes, consider using Text with `ScrollView` and/or `ViewThatFits` (covered later in the course).

{{< liteyoutube "jTNEOVkmsdU" >}}

## Text Baseline

> Example: `StringInterpolation.swift`

Text has a baseline that is at the bottom of where most letters sit. This can be used with SF Symbols to perfectly align images because they contain a baseline as well. In an `HStack` you can utilize this super convenient feature by using `HStack(alignment: .firstTextBaseline)` or `.lastTextBaseline`

## String Interpolation

It is possible to mix other data types into a `String` by using string interpolation. This is done by placing the values you want to "interpolate" inside of a `\()`, such as `"Variable Value: \(myVar)"`. For example `"\(3)"` and `String(3)` (even `3.description`) will produce the same value. You can put an `Image` in the string interpolation but you should do that interpolation inside of `Text` view only.

{{< liteyoutube "CHpAAPtT38I" >}}

## Image

> Example: `ImagePage.swift`

At its simplest, you can create an `Image` view with `Image(systemName: "swift")`. There are also many modifiers you will likely use with `Image` to get it to do what you had in mind. Remember, you can use the SF Symbols app to find all of the symbol names that you can use.

If you add the `.resizable` modifier on its own then the image will scale independently on both axes to fill the space it is given. It is exceptionally common to also add `.scaledToFit()` (stays completely within frame bounds) or sometimes `.scaledToFill()` (scales until all sides are at least equal to the container size). You will typically control the size of images by using the `.frame` modifier. Occasionally you will want to specify a type of scaling along with an aspect ratio instead of specific dimensions and in that case you can use `.aspectRatio`.

{{< liteyoutube "nrZzq5NTZ0c" >}}

### For Future Reference

Later in the course: `ASyncImage`, Assets, other file formats (PDF, SVG, PNG, etc.), blend modes, from `UIImage`, symbol animation, rendering mode, Asset `enum` synthesis, a11y label, decorative attribute

## Label

> Example: `ButtonPage.swift`

A `Label` pairs an icon and text together in one view and it is often with with `Button` views but also on its own. SwiftUI is very adaptive with this and can adjust for Right-to-Left languages, device used, and manually specifying styles. Using it can be as easy as `Label("Easy Button", systemImage: "button.programmable.square")`. You can use the `.labelStyle` modifier if you have a particular look in mind, otherwise SwiftUI will pick one automatically based on the context. You also have the ability to create your own custom button styles but that will be covered later in the course. 

{{< liteyoutube "cHB9VMde3uY" >}}

## Padding

Add space around your views with the `.padding` modifier. 

Beware: using negative values in a padding modifier is almost always a mistake. 

{{< liteyoutube "8MLP095KhMM" >}}

## Colors

There are many system-provided colors, like you have seen already in the example code. There is also `.primary` (black in light mode, white in dark mode). Similarly, there is a `.secondary` the will be a gray near to the `.primary` color, which is a common way to show hierarchy in your UI.

You will frequently use `.opacity` with a `Color` but you can apply it to all views. 

If you want to color a view, use the `.foregroundStyle` modifier. 

{{< liteyoutube "2pufjNEXLmQ" >}}

## Background and Overlay

This creates another "space" to put views in front of or behind of a view that has the same dimensions as its parent. Try out `.overlay` and `.background` on your own!

## Border

Try it out! For example, `.border(.mint, width: 2)`.

There is also a `.strokeBorder` and `.buttonBorderShape` that you can look into.

## Intro to Layout Views (More in Class 3)

### Stacks

They can all be used within each other but try to keep it to a minimum or be intentional about splitting things up.

### VStack and HStack

`VStack(alignment: .trailing, spacing: 20) { ... }` where alignment can also be `.center` (the default) or `.trailing`. And `HStack` takes `.top`, `.center`, or `.bottom`. 

### Spacer

```swift
HStack {
	Text("Leading Side")

	Spacer()
}

```

Spacer can sometimes be tricky because it can have a minimum length and then the stack can have a default spacing, but we can get into all of those details another time. 

### ZStack

Use this if you want each view to have its own dimension but otherwise you probably want to use an overlay or a background because they take the frame size of their parent. 

`ZStack` has 8 options for alignment, one for each corner and one for each side.

Beware: `ZStack` is sometimes used in a really hacky way where either something is bring done that shouldn't be (e.g., not a native sort of behavior) or it could be done in straightforward that you may not know about.

It's almost always better to use an overlay or a background because it's at least more direct semantically or it is a smell of trying to do something in a hacky way where there is either a better alternative or a good reason to not do it at all. 

## ScrollView

* Horizontal axis with `HStack`
* New scroll/bounce behaviors
* Show/hide indicators
* Beware padding on outside of `ScrollView`
* Some say there should always be a `ScrollView` or an options for `ScrollView` for accessibility

---

Polish Notes

* Got down to only "Multiline Text Alignment" about halfway through
* Students and trouble with HwS assignment, especially 2nd half because concepts were new
* Despite great challenges, I received no messages indicating this was the case
* The quiz I came up with was much too challenging 
* Having the examples already written up in Xcode made the pace good
* Student pointed out that `Group` is like `<div>`
* Found that strings saved in variable do not accept markdown
* Needed to go through new project creation steps again
* Needed to explain organization identifier again, it has been quite confusing
* Glossed too quickly over creating new files and missed naming convention
* A list of common troubleshooting steps could be good, like Clean Build Folder
* Students seem OK with lecture length of 90+ minutes but we agree 2x/week would help for troubleshooting
* I did explain autocomplete and a preview of going to definition but should make notes for this
* Showed a `private enum Constants` with `static var myString: String {...}` and should add one for text too
* Showed an extension on String/Text to contain just a space
* In line limit video fix the example of `.lineLimit(nil)`