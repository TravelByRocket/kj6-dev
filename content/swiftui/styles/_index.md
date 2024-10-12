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

```swift
@Environment(\.isEnabled)
@Environment(\.controlSize)
@Environment(\.labelsVisibility)
@Environment(\.toolbarLabelStyle)
```

### More Customizable Styles

Gauge, Table, other obscure views...

## Only System Defined

Not available AFAIK: TextField, List, Picker
