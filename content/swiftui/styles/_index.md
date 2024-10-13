---
title: "View Styles"
draft: false
weight: 50
appledoc_url: https://developer.apple.com/documentation/swiftui/view-styles
xcode_version: "16.1 beta 3"
tags:
 - "Xcode 16.1 beta 3"
---

* Certain views can be changed by applying a style
* Automatic based on context unless specified
* Applied through the environment (i.e., to all subviews)
* Can create custom styles if style protocol defines `makeBody`

## Discussion

* When to use a style vs. just a custom view?

### Additional Style Properties

If you also need to pass arguments to your style, you can add them like any other struct and pass the arguments through the extension. Here is an example using a style conforming to `ButtonStyle`

Add the property to the struct.

```swift
struct MyButtonStyle: ButtonStyle {
    let myToggleProperty: Bool

    func makeBody(configuration: Configuration) -> some View {
        //
    }
}
```

Change the `var` to a `func` with a parameter that is passed to the struct.

```swift
extension ButtonStyle where Self == MyButtonStyle {
    static func myButton(myToggle: Bool): Self { 
        .init(myToggleProperty: myToggle) 
    }
}
```

Pass your value as an argument where you use the button style.

```swift
Button("My Button Style") {
    // no-op
}
.buttonStyle(.myButton(myToggle: true))
```

### Environment Variables

You will likely want to change the appearance and interactivity of your styles when a view has been set as disabled. This is done with the `.disabled` view modifier and can be retrieved with the `@Environment(\.isEnabled)`. Why are the inverse of each other? I do not know. 

The following environment variables don't seem widely used but could be interesting to consider in your custom styles.

```swift
\.controlSize
\.labelsVisibility
\.toolbarLabelStyle
```

### Other Customizable Styles

https://developer.apple.com/documentation/swiftui/datepickerstyle
https://developer.apple.com/documentation/swiftui/menustyle
https://developer.apple.com/documentation/swiftui/gaugestyle
https://developer.apple.com/documentation/swiftui/progressviewstyle
https://developer.apple.com/documentation/swiftui/texteditorstyle
https://developer.apple.com/documentation/swiftui/tablestyle
https://developer.apple.com/documentation/swiftui/disclosuregroupstyle
https://developer.apple.com/documentation/swiftui/navigationsplitviewstyle
https://developer.apple.com/documentation/swiftui/controlgroupstyle
https://developer.apple.com/documentation/swiftui/formstyle
https://developer.apple.com/documentation/swiftui/groupboxstyle
https://developer.apple.com/documentation/swiftui/labeledcontentstyle

## Style Not Customizable

https://developer.apple.com/documentation/swiftui/pickerstyle
https://developer.apple.com/documentation/swiftui/textfieldstyle
https://developer.apple.com/documentation/swiftui/liststyle
https://developer.apple.com/documentation/swiftui/tabviewstyle
https://developer.apple.com/documentation/swiftui/indexviewstyle
