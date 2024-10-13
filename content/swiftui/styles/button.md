---
title: "Button"
draft: false
weight: 20
appledoc_url: https://developer.apple.com/documentation/swiftui/view-styles#Styling-buttons
xcode_version: "16.1 beta 3"
tags:
 - "Xcode 16.1 beta 3"
---

One of the most ubiquitous views, using custom styling for a button can greatly affect the look and feel of your app. 

{{< liteyoutube "UIlRTLcZ3VU" >}}

## Discussion

* Must use a style if you want an `isPressed` appearance
* Inherit from `ButtonStyle` in almost all cases
* Only inherit from `PrimitiveButtonStyle` to define your own interactions
* Applies to `NavigationLink` unless it is in a `List` or `Form`
* `Link` looks like a `Button` but you cannot change the style

## System Styles

* Use the snippet below to see all of the built-in button styles

```swift
Button("Auto Button Style") { }
    .buttonStyle(.automatic)

Button("Plain Button Style") { }
    .buttonStyle(.plain)

Button("Bordered Button Style") { }
    .buttonStyle(.bordered)

Button("Bordered Button Style Prominent") { }
    .buttonStyle(.borderedProminent)

Button("Borderless Button Style") { }
    .buttonStyle(.borderless)
```

## ButtonStyle

* You should prefer `ButtonStyle` over `PrimitiveButtonStyle` with few exceptions
* No need to add gestures to work, everything is included

Create your style struct and have it conform to `ButtonStyle`. It is customary for all button styles to be named `...ButtonStyle`. The `Configuration` type contains `.label`, `.isPressed`, and `.role` for you to use as you wish to style the button.

Here is a simple example of a custom button style.

```swift
struct MyButtonStyle: ButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        HStack(alignment: .firstTextBaseline) {
            image(for: configuration.role)

            configuration.label
        }
        .overlay {
            if configuration.isPressed {
                border
            }
        }
    }

    var border: some View {
        RoundedRectangle(cornerRadius: 5)
            .stroke(lineWidth: 3)
    }

    func image(for role: ButtonRole?) -> Image {
        let systemName = switch role {
            case .cancel: "xmark.circle"
            case .destructive: "trash"
            default: "face.smiling"
        }

        return Image(systemName: systemName)
    }
}
```

In order to use the nice `.buttonStyle(.myButton)` syntax, we must extend the `ButtonStyle` protocol. Without this, we would have to use `.buttonStyle(MyButtonStyle())`, which is now considered an old way of using styles.

```swift
extension ButtonStyle where Self == MyButtonStyle {
    static var myButton: Self { .init() }
}
```

See the button style in action by using the following code in your view. 

```swift
Button("My Button Style") { }
    .buttonStyle(.myButton)

Button("My Button Style", role: .cancel) { }
    .buttonStyle(.myButton)

Button("My Button Style", role: .destructive) { }
    .buttonStyle(.myButton)
```

## PrimitiveButtonStyle

* Only inherit from `PrimitiveButtonStyle` when `ButtonStyle` is not sufficient
* You must add a gesture to run the button's action

The Configuration type contains `.label`, `.trigger`, and `.role` for you to use as you wish to style the button.

Here is the setup. 

```swift
struct MyPrimitiveButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .foregroundStyle(color(for: configuration.role))
            .onTapGesture(perform: configuration.trigger)
    }

    func color(for role: ButtonRole?) -> Color {
        switch role {
            case .cancel: .orange
            case .destructive: .purple
            default: .green
        }
    }
}

extension PrimitiveButtonStyle where Self == MyPrimitiveButtonStyle {
    static var myPrimitiveButton: Self { .init() }
}
```

Here is an example usage.

```swift
Button("My Primitive Button Style") { }
    .buttonStyle(.myPrimitiveButton)

Button("My Primitive Button Style", role: .cancel) { }
    .buttonStyle(.myPrimitiveButton)

Button("My Primitive Button Style", role: .destructive) { }
    .buttonStyle(.myPrimitiveButton)
```

Note that this button does not have any kind of pressed appearance. If you want that, you will need to use a gesture that can run a closure when a gesture starts and when it ends in order to change a `@State` that affects the appearance. Have fun!

## Design Considerations

Keep in mind that the default button styling applies a transparency and saturation effect to a button while it is being pressed. If you exclude something like this then your custom button style may not "feel" right to your users. Also, there is an effect applied when a button when it is disabled and you would likely want to make it visually apparent that the button cannot be pressed. `ButtonStyle` will already disable hit testing on your button if the environment's `isEnabled` variable is `false`. 

## Explore

* Under what contexts does the automatic style change?

{{< xcode-version >}}
{{< apple-doc-url >}}